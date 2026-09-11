---
title: "CustomerWhatsAppMarketingConsent"
source: "https://shopify.dev/docs/api/admin-graphql/2026-07/objects/CustomerWhatsAppMarketingConsent"
final_url: "https://shopify.dev/docs/api/admin-graphql/latest/objects/CustomerWhatsAppMarketingConsent"
platform: "shopify"
fetched_at: "2026-09-11T09:20:10Z"
last_checked_at: "2026-09-11T10:13:18Z"
previous_fetched_at: ""
http_status: "200"
format: "html-converted"
sha256: "41a7f25dd1686231b5cbeb5da6459971a04df931bb3183173f1671f4f5541d4d"
---

Choose a version:

unstable 2026-10 release candidate2026-07 latest2026-04 2026-01 2025-10 

2026-07latest

Requires `read_customers` access scope.

The WhatsApp marketing consent information for a [customer's phone number](https://shopify.dev/docs/api/admin-graphql/latest/objects/CustomerPhoneNumber). Implements the [`CustomerMarketingConsent`](https://shopify.dev/docs/api/admin-graphql/latest/interfaces/CustomerMarketingConsent)
interface. Use the [`customerWhatsAppMarketingConsentUpdate`](https://shopify.dev/docs/api/admin-graphql/latest/mutations/customerWhatsAppMarketingConsentUpdate)
mutation to update it.

## [Anchor to Fields](/docs/api/admin-graphql/latest/objects/CustomerWhatsAppMarketingConsent#fields)Fields

- collectedFrom (CustomerConsentCollectedFrom)
- optInLevel (CustomerMarketingOptInLevel)
- sourceLocation (Location)
- state (CustomerMarketingConsentState!)
- updatedAt (DateTime)

[Anchor to collectedFrom](/docs/api/admin-graphql/latest/objects/CustomerWhatsAppMarketingConsent#field-CustomerWhatsAppMarketingConsent.fields.collectedFrom)collectedFrom •[CustomerConsentCollectedFrom](/docs/api/admin-graphql/latest/enums/CustomerConsentCollectedFrom)
:   The [source](https://shopify.dev/docs/api/admin-graphql/latest/enums/CustomerConsentCollectedFrom) from which the marketing consent was collected.

    Show enum values

[Anchor to optInLevel](/docs/api/admin-graphql/latest/objects/CustomerWhatsAppMarketingConsent#field-CustomerWhatsAppMarketingConsent.fields.optInLevel)optInLevel •[CustomerMarketingOptInLevel](/docs/api/admin-graphql/latest/enums/CustomerMarketingOptInLevel)
:   The [marketing subscription opt-in level](https://shopify.dev/docs/api/admin-graphql/latest/enums/CustomerMarketingOptInLevel)
    that was set when the customer's marketing consent was last updated. Follows
    M3AAWG best practices guidelines.

    Show enum values

[Anchor to sourceLocation](/docs/api/admin-graphql/latest/objects/CustomerWhatsAppMarketingConsent#field-CustomerWhatsAppMarketingConsent.fields.sourceLocation)sourceLocation •[Location](/docs/api/admin-graphql/latest/objects/Location)
:   The [location](https://shopify.dev/docs/api/admin-graphql/latest/objects/Location)
    where the customer consented to receive marketing material.

    Show fields

[Anchor to state](/docs/api/admin-graphql/latest/objects/CustomerWhatsAppMarketingConsent#field-CustomerWhatsAppMarketingConsent.fields.state)state •[CustomerMarketingConsentState!](/docs/api/admin-graphql/latest/enums/CustomerMarketingConsentState) non-null
:   The customer's current [marketing consent state](https://shopify.dev/docs/api/admin-graphql/latest/enums/CustomerMarketingConsentState)
    for this channel.

    Show enum values

[Anchor to updatedAt](/docs/api/admin-graphql/latest/objects/CustomerWhatsAppMarketingConsent#field-CustomerWhatsAppMarketingConsent.fields.updatedAt)updatedAt •[DateTime](/docs/api/admin-graphql/latest/scalars/DateTime)
:   The date and time when the marketing consent was updated.

    No date is provided if the customer has never updated their marketing consent for this channel.

---

Was this section helpful?

---

## [Anchor to Interfaces](/docs/api/admin-graphql/latest/objects/CustomerWhatsAppMarketingConsent#interfaces)Interfaces

- CustomerMarketingConsent

[Anchor to CustomerMarketingConsent](/docs/api/admin-graphql/latest/objects/CustomerWhatsAppMarketingConsent#interface-CustomerMarketingConsent)[CustomerMarketingConsent](/docs/api/admin-graphql/latest/interfaces/CustomerMarketingConsent) •interface

---

Was this section helpful?
