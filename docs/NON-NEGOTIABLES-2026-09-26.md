# The three non-negotiables, checked against Meta — 26 Sep 2026

The owner set three conditions the Wati replacement must meet whichever route it takes
(Wati number kept, coexistence on the app number, or both under the account model). This
document records what was checked, against what, and the verdict. "Verified" means read on a
Meta page (a snapshot lives in `docs/platform/whatsapp-cloud-api/`). "BSP-reported" means a
partner's documentation, which describes Meta's platform as the partner experiences it and can
be wrong. "Not found" means Meta says nothing either way; that is a risk, not a no.

| # | Requirement | Verdict | Confidence |
|---|---|---|---|
| 1 | Carousel template messages | **Yes, on every route.** API marketing template; ours to create on our Messaging account. No number-type or coexistence restriction exists in Meta's docs. | Verified (Meta) + BSP-reported |
| 2 | Meta Verified badge | **Yes, with a sequencing rule.** Paid badge is available to API numbers and is the *only* badge route for an app number. Partners say it survives coexistence; Wati says the opposite of its own integration; Meta is silent. Onboard first, subscribe after. | BSP-reported; Meta silent on the interaction |
| 3 | Rapid response, all metrics, all chats to AI, identity across platforms | **Yes, by design of the API**; two parts need a decision at build time (inbound fan-out under the account model; media retention). | Verified (Meta) |

The rest of this document is the evidence behind each row.

## 1. Carousel template messages

**What Meta says** (`templates-carousel.md`, `message-template-api.md`):

- A media card carousel is "a single **marketing template** message accompanied by a set of up
  to 10 product media cards in a horizontally scrollable view". Minimum 2 cards. Each card has
  a media header (image or video, all cards the same type), a body, and up to two buttons
  (quick reply, URL, or phone). "Carousel cards are only available for marketing template
  messages." A product-card variant exists that keeps the customer inside WhatsApp, but it
  needs a Meta catalog.
- It is created like any template, through the Message Templates API on the business account
  (`CAROUSEL` is a listed component type alongside `BODY`, `BUTTONS`, `HEADER`,
  `LIMITED_TIME_OFFER`). Same review, same categorisation, same quality scoring and pausing as
  any other marketing template.
- It is sent with the ordinary `/messages` call with `type: template`, so it goes through
  whatever number and Messaging account the template belongs to.

**Restrictions looked for and not found:** nothing on the carousel page, the template
management page, the coexistence onboarding page or the throughput page limits carousels by
number type, onboarding path or partner. The coexistence feature-comparison table lists what
the *app* loses (broadcast lists, disappearing messages, view-once, live location) and what the
API does not mirror (groups, calls, catalog/orders, app-side marketing messages); templates
are not in that table at all, because they are an API feature that the app never had.

**BSP-reported, agreeing:** 360dialog's coexistence page — "both the WhatsApp Business App and
Cloud API support the same types of messages, including Marketing, Utility, Service, and
Authentication." Wati's 10 Aug 2026 coexistence FAQ does not list carousels as a limitation.

**What this means for the build:**

- Wati's carousel templates are Wati's. Under the account model, templates are per Messaging
  account and are not shared, so every carousel gets rebuilt on ours. That is a data-entry job,
  not a migration risk: the schema is documented, and the tool should own template creation
  from day one so a rebuild is a form, not a chore.
- The 20 mps fixed throughput on a coexistence number (`throughput.md`) does not affect a
  carousel; it caps how fast a broadcast fans out. 20 per second is 1,200 a minute — larger than
  any list this store has.
- One thing that *can* break it, and Meta has done it before: template categorisation.
  Carousels are marketing-only, so they are the first thing to be priced as marketing and the
  first to be paused for low read-rates (`templates-pausing.md`, `templates-quality.md`). The
  tool watches `template_status_update` and `template_quality_update` webhooks and reports a
  pause before the owner finds out from a failed send.

**Verdict:** met on any route. Unaffected by coexistence or the account model, as far as
Meta's documentation goes.

## 2. Meta Verified status

There are three different "verified" things, and the owner's requirement is the badge:

| Thing | What it is | Who gets it |
|---|---|---|
| **Business verification** | Free, documents-based; unlocks messaging-limit tiers and the display name. Not a badge. (`business-verification-help.md`: "different from Meta Verified for businesses and won't give you a verified badge.") | Any WABA / business portfolio |
| **Official Business Account (OBA)** | The old free green tick, granted by Meta on request to notable brands. | API numbers ≥30 days on the platform. **Not granted to WhatsApp Business app numbers.** (Meta OBA page) |
| **Meta Verified for business / Meta One** | Paid badge subscription (Meta One from 15 Sep 2026 bundles it with impersonation protection and Business Agent). | Business-app numbers and API numbers |

**What is verified:**

- The paid badge is the only badge an app number can get (Meta OBA page). For an API number
  both routes exist, but OBA is discretionary and slow, so the paid badge is the one to plan on.
- Meta One is a subscription on the business portfolio, not a connection method. It does not
  create, restrict or require any API integration (`COEXISTENCE-2026-09-26.md` §9b).

**What is BSP-reported and disagrees:**

- 360dialog: on a coexistence number, "Meta Verified — Yes, it will be maintained." Classic
  business verification is *not* available to coexistence accounts; PLBV or Meta Verified is.
- respond.io: "You will not lose your Meta Verified badge … through WhatsApp Coexistence." Note
  the badge may drop for a few days while the number activates.
- Wati (10 Aug 2026): "you can have either the CoEx integration or paid Business Verification
  active, but not both at the same time," and re-enabling one "may be disconnected" from the
  other.

The Wati statement is the outlier. It is most likely describing Wati's own integration flow
(Wati re-runs Embedded Signup when the badge state changes), not the platform. It cannot be
ruled out from Meta's side, because Meta's help pages on Meta Verified for businesses do not
mention coexistence at all — and they do not render fully for our fetcher, so that absence is
partly a fetcher limitation.

**What this means for the build:**

- The badge is not tied to *which API integration* the number uses. Under the account model
  it belongs to the WhatsApp account (the number and identity), not to a Messaging account. So
  moving from Wati to our tool does not touch it. This follows from the split
  (`ACCOUNT-MODEL-EVOLUTION-2026-09-26.md`) rather than from an explicit Meta sentence; flagged
  as inferred.
- **Sequence:** onboard the app number to coexistence first, confirm the tool works, then buy
  the badge. Buying first risks a lapse during onboarding (partners say days) and, if Wati's
  either/or is real for our flow too, a failed onboarding. Buying after risks nothing that
  onboarding did not already settle.
- The requirement "the API I have must allow me for this" is satisfied on our own Messaging
  account because the badge is independent of it. It is Wati's product that does not offer a
  route, not Meta's platform.

**Verdict:** met. The only open point is the coexistence interaction, which Meta does not
document and BSPs disagree on; the sequencing rule removes the risk from our path, and the
worst case (badge drops for days during onboarding) is a cosmetic gap, not a lost badge.

## 3. Rapid response, metrics, chats for AI, cross-platform identity

Split into the four things the owner actually asked for.

### 3a. Rapid response

- Inbound messages arrive as `messages` webhooks within seconds, on any number the app is
  subscribed to (`webhooks-overview.md`). On a coexistence number, replies typed on the phone
  arrive as `smb_message_echoes`, so the inbox shows the whole conversation whichever side
  answered.
- The 24-hour customer service window applies to API sends only; app sends are free and outside
  it (`coexistence-onboarding.md`, Pricing and Customer service window). This is exactly the
  owner's current fallback pattern, kept, and now visible in the tool.
- Throughput: 80 mps default on a pure API number, 20 mps fixed on a coexistence number
  (`throughput.md`). Both are far above a single-operator inbox.
- Nothing in this depends on Wati, a partner, or the account model.

### 3b. All metrics, pullable for marketing and templates

Three sources, all ours to store:

1. **Status webhooks** (`webhook-messages-status.md`): `sent`, `delivered`, `read`, `failed`
   per message, with the conversation category and pricing on the `sent` status. Stored per
   message, this gives delivery and read rates per template, per broadcast, per customer, per
   day — the numbers Wati shows, plus the ones it does not (time-to-read, failure reasons).
   Caveat: `read` is only sent if the customer has read receipts on; `delivered` is skipped when
   the message was read on arrival. Both are documented and both are normal.
2. **Template Analytics API** (Business Management API, `analytics` and `template_analytics`
   edges): sent / delivered / read counts and **button clicks per button** per template, with
   daily granularity, plus template groups for comparing variants. Requires enabling analytics
   on the account once. Click tracking is subject to the customer opting out
   (`cta_url_link_tracking_opted_out` on the status webhook).
3. **Template state webhooks**: `template_status_update`, `template_quality_update`,
   `template_category_update` — the "why did my carousel stop" data.

Under the account model, metrics belong to the Messaging account that sent the message. Wati's
history stays in Wati; ours starts the day our account sends its first message. The nightly
ingest in `tcgsouq-social` already pulls Wati's broadcast stats into `wa_broadcasts` /
`wa_messages`, so the historical numbers are not lost when Wati goes.

### 3c. All chats available for AI analysis

- Every inbound message body, media id and context arrives in the `messages` webhook; every
  outbound sent by the tool is known to the tool; every outbound typed on the phone arrives via
  `smb_message_echoes` (coexistence only). Stored in Supabase, the full transcript exists
  without any export step.
- **History**: coexistence syncs up to 6 months of 1:1 chats once, within 24 hours of
  onboarding, via the `history` webhook — that is the back-catalogue for the app number.
  Wati's history comes from the Wati export (Settings → Import/Export Chats) plus the
  `/conversations/{target}/messages` pulls already scoped; both are covered in the earlier
  session notes.
- **Media** is the one thing that needs a decision: a media id received in a webhook can be
  downloaded for **7 days**, and each download URL lives **5 minutes** (`media.md`). If the AI
  is to see images (proofs of payment, damaged-card photos), the tool must download media on
  receipt and store it. Cheap, but it must be built in, not added later.
- No Meta rule prevents running an AI over your own conversations; the WhatsApp Business
  Policy governs what you *send*, and the tool's replies remain human-or-service messages. The
  constraint is the same one as for Customer Match: consent and the privacy notice, which the
  charter already requires.

### 3d. Connected to the cross-platform customer-recognition tool

- Identity key: from Apr–Jul 2026 Meta issues **BSUIDs** and may omit the phone number from
  webhooks unless the customer has interacted within 30 days or is in the contact book. The
  schema therefore keys `wa_contacts` on BSUID with phone as an attribute, and the identity
  graph in Supabase joins BSUID ↔ phone ↔ Shopify customer ↔ Instagram/Messenger PSID. This is
  already in the plan (`COEXISTENCE-2026-09-26.md` §4 item 6) and is what makes "recognise the
  customer on any channel" possible after phone numbers stop being reliable.
- **Open, needs a build-time decision:** under the account model one number can carry two
  Messaging accounts (Wati's and ours) during the migration. Meta has not yet published how an
  *inbound* message is routed when two integrations are subscribed to the same number — to
  both, or to the one the customer last talked to. Until Phase 1 documentation lands (H2 2026)
  the safe assumption is "one inbound owner per number", which means: during the overlap, our
  tool reads Wati's inbound via the nightly pull, and takes over inbound only when Wati is
  unsubscribed from that number. Recorded as the first question to answer when Phase 1 docs
  appear.

**Verdict:** met. Everything here is the ordinary Cloud API surface; the pieces that are new
(BSUID keys, `smb_message_echoes`, media capture) are cheap and are already in the plan.

## What can still break it — and it is only Meta

The owner's framing was right: none of the three depends on Wati, a partner, or on us doing
anything clever; all three depend on Meta not changing things. The changes that would matter,
in the order they are likely:

1. **Template pausing / re-categorisation** of a carousel — Meta already does this on
   read-rate; watched by webhook. Recoverable in a day.
2. **Account model Phase 1 routing rules** for inbound on a number with two Messaging accounts
   (3d). Affects only the overlap period; a sequencing choice, not a capability loss.
3. **Meta Verified terms** changing for coexistence numbers. Cosmetic, recoverable by
   re-subscribing.
4. **Coexistence availability in the UAE** — still the gating check from
   `COEXISTENCE-2026-09-26.md` §9. If it fails, the app number stays app-only, the Wati number
   becomes our number under the account model, and all three requirements are still met; only
   the "same number on phone and API" convenience is lost.

None of these removes a requirement. Nothing in this review found a route on which any of the
three is unavailable.

## Sources

Meta (snapshots in `docs/platform/whatsapp-cloud-api/`): `templates-carousel.md`,
`message-template-api.md`, `templates-pausing.md`, `templates-quality.md`,
`coexistence-onboarding.md`, `throughput.md`, `webhook-messages-status.md`,
`webhooks-overview.md`, `media.md`; `docs/platform/whatsapp-policy/business-verification-help.md`;
Meta "Official Business Account" help page (live, 26 Sep 2026); Template Analytics API (Business
Management API reference, live).
BSP-reported: 360dialog partner docs — WhatsApp Coexistence (live); respond.io — WhatsApp
Coexistence FAQ (live); Wati Knowledge Base — CoEx FAQ, 10 Aug 2026 (live).
