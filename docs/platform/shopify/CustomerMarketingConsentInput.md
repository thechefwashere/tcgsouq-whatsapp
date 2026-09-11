---
title: "CustomerMarketingConsentInput"
source: "https://shopify.dev/docs/api/admin-graphql/2026-07/input-objects/CustomerMarketingConsentInput"
final_url: "https://shopify.dev/docs/api/admin-graphql/latest/input-objects/CustomerMarketingConsentInput"
platform: "shopify"
fetched_at: "2026-09-11T09:20:10Z"
last_checked_at: "2026-09-11T10:13:18Z"
previous_fetched_at: ""
http_status: "200"
format: "html-converted"
sha256: "4373de9b1b80c4ab362d2c4dba28895320e58ab8e091c4a0005d0ea02e8dafd9"
---

Choose a version:

unstable 2026-10 release candidate2026-07 latest2026-04 2026-01 2025-10 

2026-07latest

The input fields for marketing consent information when a
[customer](https://shopify.dev/docs/api/admin-graphql/latest/objects/Customer)
consents to receive marketing material on a specific channel. Channel-specific
consent mutations like [`customerWhatsAppMarketingConsentUpdate`](https://shopify.dev/docs/api/admin-graphql/latest/mutations/customerWhatsAppMarketingConsentUpdate)
use this input.

## [Anchor to Fields](/docs/api/admin-graphql/latest/input-objects/CustomerMarketingConsentInput#fields)Fields

- optInLevel (CustomerMarketingOptInLevel)
- sourceLocationId (ID)
- state (CustomerMarketingConsentState!)
- updatedAt (DateTime)

[Anchor to optInLevel](/docs/api/admin-graphql/latest/input-objects/CustomerMarketingConsentInput#fields-optInLevel)optInLevel •[CustomerMarketingOptInLevel](/docs/api/admin-graphql/latest/enums/CustomerMarketingOptInLevel)
:   The [marketing subscription opt-in level](https://shopify.dev/docs/api/admin-graphql/latest/enums/CustomerMarketingOptInLevel)
    that was set when the customer consented to receive marketing information.

    Show enum values

[Anchor to sourceLocationId](/docs/api/admin-graphql/latest/input-objects/CustomerMarketingConsentInput#fields-sourceLocationId)sourceLocationId •[ID](/docs/api/admin-graphql/latest/scalars/ID)
:   Identifies the [location](https://shopify.dev/docs/api/admin-graphql/latest/objects/Location)
    where the customer consented to receiving marketing material.

[Anchor to state](/docs/api/admin-graphql/latest/input-objects/CustomerMarketingConsentInput#fields-state)state •[CustomerMarketingConsentState!](/docs/api/admin-graphql/latest/enums/CustomerMarketingConsentState) non-null
:   The [marketing consent state](https://shopify.dev/docs/api/admin-graphql/latest/enums/CustomerMarketingConsentState)
    to set for the customer on this channel.

    Show enum values

[Anchor to updatedAt](/docs/api/admin-graphql/latest/input-objects/CustomerMarketingConsentInput#fields-updatedAt)updatedAt •[DateTime](/docs/api/admin-graphql/latest/scalars/DateTime)
:   The date and time when the customer consented to receive marketing material.
    If no date is provided, then the date and time when the consent information was sent is used.

---

Was this section helpful?

## [Anchor to Input objects using this input](/docs/api/admin-graphql/latest/input-objects/CustomerMarketingConsentInput#input-objects-using-this-input)Input objects using this input

[Anchor to CustomerInput.whatsAppMarketingConsent](/docs/api/admin-graphql/latest/input-objects/CustomerMarketingConsentInput#reference-CustomerInput.whatsAppMarketingConsent)[CustomerInput.whatsAppMarketingConsent](/docs/api/admin-graphql/latest/input-objects/CustomerInput#fields-whatsAppMarketingConsent) •INPUT OBJECT
:   The input fields and values to use when creating or updating a customer.

[Anchor to CustomerWhatsAppMarketingConsentUpdateInput.whatsAppMarketingConsent](/docs/api/admin-graphql/latest/input-objects/CustomerMarketingConsentInput#reference-CustomerWhatsAppMarketingConsentUpdateInput.whatsAppMarketingConsent)[CustomerWhatsAppMarketingConsentUpdateInput.whatsAppMarketingConsent](/docs/api/admin-graphql/latest/input-objects/CustomerWhatsAppMarketingConsentUpdateInput#fields-whatsAppMarketingConsent) •INPUT OBJECT
:   The input fields to update a customer's WhatsApp marketing consent information.

---

Was this section helpful?
