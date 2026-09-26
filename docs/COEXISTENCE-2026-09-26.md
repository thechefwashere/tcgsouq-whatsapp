# Coexistence — one number on the WhatsApp Business app *and* the Cloud API

**Checked 26 Sep 2026** against Meta's own documentation, Meta's changelog, and three BSPs
(Wati, 360dialog, one availability checker). Prompted by the owner's question on the same day:
does the number now get to exist as both API and the regular app at once, and what does that do
to the Wati-replacement plan?

Short answer: **yes, it exists, it is GA, and the plan is wrong to have written it off** — but
it comes with a sequencing constraint on the current number, two things to verify before
committing, and a handful of operating rules that never go away. Details below, with what is
verified separated from what is reported.

## 1. What it is, verified

Meta calls the feature *onboarding WhatsApp Business app users*; the docs say it "is sometimes
referred to as 'Coexistence'". Source (snapshotted in this repo on 11 Sep, byte-identical live
on 26 Sep):
`docs/platform/whatsapp-cloud-api/coexistence-onboarding.md`.

> "After a business customer chooses this option and onboards successfully, they can use your app
> to send high volumes of messages. They can still send messages on a one-to-one basis using the
> WhatsApp Business app, and WhatsApp keeps messaging history between both apps in sync."

Timeline, from Meta's changelog:

| Date | Entry |
|---|---|
| 11 Feb 2025 | "Added ability for solution providers to onboard WhatsApp Business app users via Embedded Signup (aka 'Coexistence')." |
| 5 May 2025 | India country code added |
| 8 Oct 2025 | Embedded Signup v4 available |
| 23 Oct 2025 | Australia, Japan, Philippines, Russia, South Korea, Turkey, EEA/EU, UK added |
| 25 Nov 2025 | Edit and revoke message webhooks supported for coexistence numbers |
| 12 May 2026 | Embedded Signup v4 public preview: "Phone Number First" flow |
| **15 Oct 2026** | **Embedded Signup v2 deprecated.** Build on v4. |

## 2. The rules, verified against Meta

Everything in this table is from Meta's page unless marked.

| Rule | Detail |
|---|---|
| Who can enable it | "You must already be a Solution Partner or Tech Provider." Tech Provider is a self-serve developer role (business verification + App Review for two permissions), not a partnership Meta grants — see §4 |
| App version | WhatsApp Business app ≥ 2.24.17 |
| Onboarding mechanism | Embedded Signup with session logging; v4 supports the business-app flow via login configuration |
| Throughput | "fixed throughput of 20 mps" while the number is on both |
| History sync | "All chat messages in the most recent 6 months can be synchronized" — **once**, initiated by the partner, and "you have 24 hours to synchronize their contacts and messaging history, otherwise they must be offboarded and they must complete the flow again" |
| Contacts sync | all contacts with a WhatsApp number, once; later changes arrive as `smb_app_state_sync` webhooks |
| Ongoing mirror | every message sent from the app arrives as an `smb_message_echoes` webhook; API messages appear in the app |
| Disabled *in the app* after onboarding | broadcast lists (existing become read-only), disappearing messages, view-once, live location |
| Not available *to the API* on a coexistence number | group chats, voice/video calls, business tools (catalog, orders, status), messaging tools (greeting, away, quick replies, labels), business profile edits, Channels |
| Pricing | "messages sent by the business via the WhatsApp Business app will continue to be free, but messages sent via Cloud API will be subject to Cloud API pricing" |
| Customer service window | applies to API messages only; app messages "do not create, extend, or affect Cloud API conversation windows or Cloud API pricing" |
| Linked devices | all companions unlinked at onboarding, re-linkable except WhatsApp for Windows and WearOS |
| Disconnection | the business disconnects from the app: Settings → Account → Business Platform → Disconnect. The Deregister API cannot be used on a coexistence number |
| Auto-disconnect | `PARTNER_REMOVED` with `PRIMARY_INACTIVITY` — "primary device was inactive for approximately 14 days"; `COMPANION_INACTIVITY` ~30 days; `USER_RE_REGISTERED` if the number is re-registered on a new device; `BUSINESS_DOWNGRADE` if registered with the consumer app |

Reported by BSPs, not on Meta's page — treat as operational folklore until observed:

- Open the app at least every **13 days** to be safe (360dialog, Wati). Do not uninstall it — that disconnects.
- Media history syncs only ~2 weeks back; text goes back 6 months (Wati).
- Official Business Account (blue tick) and the Calling API are not supported on coexistence numbers (360dialog); Wati adds Catalog.
- Wati, in its own limitations article (updated 10 Aug 2026), warns that chat sync can start and stop, and steers customers to plain Cloud API "for a more reliable experience". Worth knowing the incumbent BSP does not love it.

## 3. Where the plan is wrong

`tcgsouq-shopify/docs/social-hub/ALIGNMENT-2026-09-11.md` §4, out of scope:

> "Coexistence with the WhatsApp Business app (partner-only feature, not relevant)."

And `research/whatsapp-cloud-api.md` §10: "a direct business with its own app cannot enable it."

Both rest on reading "Solution Partner or Tech Provider" as a status only messaging vendors have.
It is not. Meta's Tech Provider page describes a self-serve path open to any developer with a Meta
app, a connected business portfolio, business verification, and App Review for
`whatsapp_business_messaging` and `whatsapp_business_management` Advanced Access — the same App
Review the social hub's Meta app will go through anyway. There is no separate gate.

What the plan got right still holds: a brand-new number as the primary, the existing number
retired over 6–12 months, the WABA kept, Wati disconnected at go-live. Coexistence fits *inside*
that plan; it changes what the number does day to day, not the migration.

## 4. What it would take — the parts that are new

1. **Tech Provider enrolment on our own Meta app.** Business verification (already a long-lead
   item in the plan) plus App Review with two demo videos: sending a message and creating a
   template. Weeks, not days. Kickoff assumed "no App Review needed for own-business use" — true
   for plain Cloud API on assets we own, **not verified for Embedded Signup**. Meta: "You will not
   be able to onboard business customers until your app has been approved for advanced access."
   Meta also says app admins and developers "can begin testing the flow using their own Meta
   credentials" in development mode. Whether that test onboarding *completes* for our own
   portfolio without Advanced Access is unknown. It is the first thing to try, because the answer
   is either "no review needed" or "start the review now".
2. **Embedded Signup v4**, business-app flow enabled via login configuration, hosted on an HTTPS
   page we control (`hub.tcgsouq.com` qualifies). v2 dies 15 Oct 2026; do not start on it.
3. **Three extra webhook fields** subscribed before onboarding: `history`, `smb_app_state_sync`,
   `smb_message_echoes` — plus `account_update` to catch disconnections.
4. **The 24-hour sync window** at onboarding: kick off contacts sync, then history sync,
   immediately after the flow completes; keep the phone unlocked and the app open; expect hours.
5. **Skip the register step** in Tech Provider onboarding — the number is already registered.
6. **Schema**: store Meta's business-scoped user ID (`BSUID`, e.g. `AE.1349…`) alongside the
   phone. Since April 2026 BSUIDs appear in webhooks; since July 2026 the user's phone number is
   omitted unless there was an interaction in the last 30 days or the user is in the portfolio's
   contact book. The capture layer keys `wa_messages` on `phone_e164`; a coexistence build must
   key on BSUID and treat the phone as an attribute. This is true with or without coexistence.

## 5. Which number — the constraint that decides the sequence

**The current number cannot coexist as it stands.** It is a pure Cloud API number under Wati; it
is not on the WhatsApp Business app. Meta's migration page: a number registered for Cloud API
cannot be used with the app "unless you deregister the number from Cloud API". 360dialog:
"this process only works for numbers registered in the app — it will not work the other way
around." Wati's own troubleshooting for "This number is registered to an existing WhatsApp
account": delete the configuration at the previous provider, re-register the number in the app,
"wait 1–2 months before attempting Coexistence again". And the history the owner cares about
lives in Wati, not in the app — the app would have nothing to sync.

So the existing number would need: deregister → app → a month or two of use → coexistence,
with an empty history. That is the retirement path, not the future.

**The new number is the natural fit, and the plan already has a warm-up period.** Register the
new number **on the WhatsApp Business app first**, use it from the phone for a few weeks, then
run the coexistence flow. Wati's eligibility guidance: "use the number actively in the WhatsApp
Business App for 7+ days (ideally 30–60 days)" — "Your phone number isn't eligible" is the
error for too-new accounts.

**UAE availability is reported, not confirmed by Meta.** Meta's changelog lists expansions
(India; then Australia, Japan, Philippines, Russia, South Korea, Turkey, EEA/EU, UK) and never
names the UAE. A third-party checker lists the United Arab Emirates as fully supported and only
Nigeria and South Africa as unsupported; Wati's help says "Meta is not allowing businesses to
onboard via Coexistence from select countries" without naming them. The flow itself returns a
plain error if the region is blocked ("This feature isn't available for phone numbers from this
region"). **Verify by attempting it, not by reading about it.**

## 6. What changes in the build, if the two checks pass

| Plan item | Before | After |
|---|---|---|
| **W7 Native Android app** | Required — the owner's non-negotiable is WhatsApp-speed sync on the phone, and the PWA was judged not enough | **Probably unnecessary.** The phone app *is* WhatsApp. Sync is Meta's problem, not ours |
| **W2 Inbox PWA** | Must fully replace the phone app for 1:1 support | Becomes the desk view: PC-sized inbox with Shopify context, mirrored via `smb_message_echoes`. Smaller, and later |
| **Broadcasts** | via API | Unchanged — API. App broadcast lists are disabled anyway |
| **1:1 replies** | via API, priced per message from 1 Oct 2026 | From the phone app: free, no window. From the desk view: API, priced |
| **Order/shipping utility templates** | via API | Unchanged |
| **Throughput** | number's tier | fixed 20 mps ≈ 1,500 recipients in ~75 s. Fine |
| **Health dashboard** | token, webhook, tier, quality | add: last app activity, `account_update` events, days since the phone last opened the app |
| **Meta app** | Live, system-user token, no App Review | Tech Provider, Embedded Signup v4, likely App Review |
| **History migration** | Wati export | Unchanged — coexistence syncs the *app's* history, and the app's history is empty |

**What does not change:** the WABA decision, the retirement of the old number, the Wati export
and consent import, the carousel templates, the Shopify webhooks, the shared Supabase.

## 7. The cost angle, because it lines up with the 1 October change

Confirmed on Meta's non-template pricing page (snapshot `pricing-non-template-messages.md`):
"Effective October 1, 2026, Meta will charge on a per-message basis for service messages" and
for utility templates inside the 24-hour window. Rates equal utility/authentication by market.

With coexistence, a reply typed in the WhatsApp Business app is free and outside the window
system entirely. For a one-person shop that answers customers from the phone, that removes the
new charge from the largest message category. The API pays for what the API is for: broadcasts,
automation, Shopify-triggered updates, and anything answered from the desk.

## 8. Operating rules that never go away

- The phone must open the app at least every ~13 days. A two-week trip without it disconnects
  the API side, and reconnecting means Embedded Signup and a fresh sync.
- Never uninstall the app on that phone. Never re-register the number on another device without
  planning the reconnect.
- One partner per number. Coexistence via Wati *and* via our app is not a thing.
- No group chats through the API; no calling API; no catalog. If any of those become wanted,
  it is API-only or app-only, not both.
- Windows desktop and WearOS companions stop working. WhatsApp Web, macOS and phones are fine.

## 9. Two checks before this changes the plan

1. **Region.** Put the new number on the WhatsApp Business app now — it needs the weeks of use
   anyway — and after ~30 days run the coexistence flow from our own Meta app in development
   mode. Either it proceeds, or it says the region is not supported. Ten minutes of the owner's
   time, once, after the wait.
2. **Access level.** The same attempt answers whether self-onboarding needs Advanced Access. If
   it does, the App Review is the long pole and starts immediately; the social hub needs the same
   review, so it is not wasted.

Until both pass, the plan stays as written. If both pass, W7 comes out of the roadmap and W2
shrinks.

## 10. Other Meta changes in the same window, briefly

- **1 Oct 2026**: service messages and in-window utility templates priced per message. Verified
  on Meta's page (§7). Third parties report a 1,000-per-number monthly free allowance; Meta's
  page does not.
- **1 Aug 2026**: Meta Business Agent billed per token ($2/1M). Irrelevant unless we use
  Meta's agent; our own automation remains "service" category.
- **15 Oct 2026**: Embedded Signup v2 deprecated (above).
- **Apr–Jul 2026**: BSUIDs and usernames; phone-number omission from webhooks (§4, item 6).
- **"WAME" = WhatsApp Account Model Evolution.** The WABA splits into a WhatsApp account (number)
  and per-integration Messaging accounts (templates, billing, webhooks), so one number can carry
  Wati and our own integration with separate billing. Covered in
  `ACCOUNT-MODEL-EVOLUTION-2026-09-26.md`; together with coexistence it is what makes the number
  flexible.

## Sources

Meta (primary):
- Onboard WhatsApp Business app users — https://developers.facebook.com/documentation/business-messaging/whatsapp/embedded-signup/onboarding-business-app-users
- Changelog — https://developers.facebook.com/documentation/business-messaging/whatsapp/changelog
- Embedded Signup versions — https://developers.facebook.com/documentation/business-messaging/whatsapp/embedded-signup/versions
- Embedded Signup implementation (dev-mode testing) — https://developers.facebook.com/documentation/business-messaging/whatsapp/embedded-signup/implementation
- Get started for Tech Providers — https://developers.facebook.com/documentation/business-messaging/whatsapp/solution-providers/get-started-for-tech-providers
- Onboarding customers as a Tech Provider — https://developers.facebook.com/documentation/business-messaging/whatsapp/embedded-signup/onboarding-customers-as-a-tech-provider
- Migrate an existing WhatsApp number — https://developers.facebook.com/documentation/business-messaging/whatsapp/solution-providers/migrate-existing-whatsapp-number-to-a-business-account/
- account_update webhook (disconnection reasons) — https://developers.facebook.com/documentation/business-messaging/whatsapp/webhooks/reference/account_update
- Pricing for non-template messages — https://developers.facebook.com/documentation/business-messaging/whatsapp/pricing/non-template-messages
- Business-scoped user IDs — https://developers.facebook.com/documentation/business-messaging/whatsapp/business-scoped-user-ids/

BSPs (secondary):
- 360dialog, Coexistence — https://docs.360dialog.com/docs/resources/phone-numbers/coexistence
- Wati, connect via CoEx — https://support.wati.io/en/articles/11822421-how-to-connect-your-whatsapp-number-to-wati-via-whatsapp-coexistence-coex
- Wati, CoEx limitations (10 Aug 2026) — https://support.wati.io/en/articles/14818473-understanding-whatsapp-coexistence-coex-limitations
- Wati, CoEx troubleshooting — https://support.wati.io/en/articles/11875544-troubleshooting-whatsapp-coexistence-signup-process-common-issues-and-how-to-resolve-them
- ChakraHQ availability checker (UAE listed as supported; no Meta citation) — https://chakrahq.com/product/whatsapp/tools/whatsapp-coexistence-support/
