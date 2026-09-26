# Account Model Evolution — the WABA splits in two, and one number can carry several integrations

**Checked 26 Sep 2026** against Meta's Account Model Evolution pages (overview, messaging,
onboarding) and its developer video (published 16 Jun 2026), with two BSP write-ups as
secondary sources. The owner raised this as "WAME" — WhatsApp Account Model Evolution — alongside
coexistence. The two are separate programmes; together they are what makes the number flexible.
Coexistence is in `COEXISTENCE-2026-09-26.md`. This file is the account model.

## 1. What changes, in one paragraph

Meta: "The WhatsApp Business account is evolving into two unique accounts: one for phone
numbers, one for template messages and billing." The **WhatsApp account (WAAC)** holds the phone
number, display name, business profile, catalog and, later, username. The **Messaging account**
holds templates, billing and webhook subscriptions. A phone number can have several Messaging
accounts at once — "each partner working with a client receives their own Messaging Account" —
and "each Messaging Account has its own payment method, completely independent from other
Messaging Accounts." Users see one number; billing and templates are separate per integration.

| Asset | Was on | Now on |
|---|---|---|
| Phone number | WABA | WhatsApp account |
| Display name, profile, catalog | WABA / number | WhatsApp account |
| Quality rating, messaging limits, conversation history | number | WhatsApp account / number — **shared by every integration on that number** |
| Message templates | WABA | Messaging account — **not shared across Messaging accounts** |
| Billing / payment method | WABA | Messaging account |
| Webhook subscriptions | WABA | Messaging account |

## 2. Timeline, from Meta

| Phase | When | What Meta does | What we must do |
|---|---|---|---|
| 1 — General availability | **H2 2026** (now) | Automatic migration. Messaging accounts keep the old WABA IDs; WhatsApp accounts exist but have no exposed ID yet. `messaging_account_id` becomes an optional parameter on the Messages API | Nothing, unless one number has more than one Messaging account — then pass `messaging_account_id` |
| 2 — New Graph API | H1 2027 | Newest API version requires `messaging_account_id` in multi-account setups; new endpoints for WhatsApp account and Messaging account management; new `whatsapp_account` webhook topic; distinct WAAC IDs returned | Adopt the new version; store WAAC IDs |
| 3 — Mandatory | H1 2028 | Every API version requires `messaging_account_id` in multi-account setups; APIs use WAAC IDs instead of phone number IDs | Complete the transition |

One hard date inside Phase 1: `paid_messaging_account_id` "is supported as a deprecated,
backward-compatible alias; migrate to `messaging_account_id` by **December 31, 2026**." New code
should never use the old name.

Embedded Signup: "Updated Embedded Signup flows automatically create a separate Messaging
Account per partner and return the ID in the existing WABA ID field — no changes to your
existing integration needed." And for coexistence specifically: "Existing WhatsApp Business app
phone numbers using coexistence are migrated into the WhatsApp Business Account model, and new
WhatsApp Business app phone numbers onboard directly into the new model." The two programmes
are compatible.

## 3. What it does to the plan

The alignment doc's WhatsApp section rests on one constraint, stated at item 8 and decision 1:
**a WABA has one credit line**, so while Wati's line is attached every message our tool sends
bills through Wati, and Wati keeps receiving webhooks for every number. That forced a hard
cut-over — attach our own card, disconnect Wati, move everything on one day.

Under the new model that constraint is the thing being removed. Meta, addressed to direct
developers: "Share your phone number with a partner to outsource specific use cases while
keeping your direct integration for everything else. Each integration gets its own Messaging
Account, so billing stays separate between your direct integration and any partners." And to
partners: "Clients currently sharing a phone number with an agency or a direct API integration
can now add you as a partner on the same number."

So, on the same number, at the same time:

- **Wati**, on its Messaging account, on Wati's credit line — until we stop using it.
- **Our own integration**, on our Messaging account, on our card — for broadcasts, Shopify
  order updates, the desk inbox.
- **The WhatsApp Business app** on the phone, if coexistence passes its two checks — free 1:1
  replies.

That turns the migration from a cliff into a slope: build and prove our side while Wati still
runs, move broadcasts one campaign at a time, and remove Wati when nothing depends on it. It
also weakens the case for a **new WABA** (alignment §6, decision 1): separate billing was the
main reason to want one, and it now comes with the Messaging account.

### What the plan already got right, and keeps

- **Templates are rebuilt anyway.** "Templates belong to the Messaging Account in which they
  were created and are not shared across Messaging Accounts." Wati's templates stay Wati's.
  Meta adds that migrated templates reset quality and tier with "a ramp-up period of
  approximately 2–4 weeks" — so create ours early, on our account, and let them age.
- **The new number as primary, the old number retiring** — unaffected.
- **Warm-up is about recipients, not limits** — still true; limits are per portfolio.

### What is new, and has to be designed in

1. **Send `messaging_account_id` on every message from day one.** Optional in Phase 1 unless
   the number carries more than one Messaging account — and with Wati still attached, it does.
2. **Store both IDs.** `wa_accounts.messaging_account_id` now; a `waac_id` column ready for
   Phase 2. In Phase 1 the "WABA ID" Embedded Signup returns is actually the Messaging account
   ID — name the column for what it is.
3. **Quality is shared.** Rating and messaging limits follow the number, across every partner
   on it. A bad broadcast from Wati during the overlap hurts our sends, and vice versa. The
   health dashboard should watch the number, not our account.
4. **Throughput is shared, not stacked.** "When multiple partners share a phone number, they
   share the phone number's throughput capacity." Irrelevant at our volumes.
5. **Check `primary_funding_id`** on our Messaging account before the first paid send — Meta's
   own check for "is a payment method attached". If absent, "the account cannot send paid
   messages."

## 4. Open — could not be settled from Meta's pages

- **Inbound message fan-out.** Whether a customer's message is delivered to every Messaging
  account subscribed on the number or to one. Meta's webhook page says subscriptions are per
  Messaging account and retries go "to all apps that have subscribed"; it does not say
  whether *first* delivery does. This decides whether Wati and our inbox both see incoming
  messages during the overlap. Find out by subscribing and watching — it costs nothing.
- **Whether a direct developer can create a second Messaging account on a partner-held number
  today**, in Phase 1, or only through the partner-initiated / Embedded Signup flows Meta has
  documented so far. The onboarding page covers partners; the direct-developer path is asserted
  in the overview but not walked through.
- **Whether Wati has moved to the new model yet.** Meta's page says the migration is automatic
  in H2 2026; whether the owner's WABA has been split is visible in WhatsApp Manager (it now
  lists WhatsApp accounts and Messaging accounts separately — the 11 Sep snapshot of Meta's
  platform overview already uses that wording).

## 5. Sources

- Overview — https://developers.facebook.com/documentation/business-messaging/whatsapp/account-model-evolution
- Messaging accounts — https://developers.facebook.com/documentation/business-messaging/whatsapp/account-model-evolution/messaging/
- Onboarding under the new model — https://developers.facebook.com/documentation/business-messaging/whatsapp/account-model-evolution/onboarding/
- Developer video, 16 Jun 2026 — https://developers.meta.com/resources/videos/whatsapp-account-model-evolution/
- Meta for Developers announcement post — https://www.facebook.com/MetaforDevelopers/posts/1432194762274188
- Webhooks overview — https://developers.facebook.com/documentation/business-messaging/whatsapp/webhooks/overview
- Secondary: UnifyPort write-up — https://www.unifyport.ai/blog/whatsapp-account-model-evolution-waac-messaging-account/ ; 360dialog migrations — https://docs.360dialog.com/docs/hub/migrations
