---
title: "customerWhatsAppMarketingConsentUpdate"
source: "https://shopify.dev/docs/api/admin-graphql/2026-07/mutations/customerWhatsAppMarketingConsentUpdate"
final_url: "https://shopify.dev/docs/api/admin-graphql/latest/mutations/customerWhatsAppMarketingConsentUpdate"
platform: "shopify"
fetched_at: "2026-09-11T09:20:10Z"
last_checked_at: "2026-09-11T10:13:18Z"
previous_fetched_at: ""
http_status: "200"
format: "html-converted"
sha256: "ddb1a5314fc189014e20f53ea165f32b024484f4507f51a45ed9d8ecb3535aa1"
---

Choose a version:

unstable 2026-10 release candidate2026-07 latest2026-04 2026-01 2025-10 

2026-07latest

Requires `write_customers` access scope. Also: The user must have permission to create and edit customers.

Updates a [customer](https://shopify.dev/docs/api/admin-graphql/latest/objects/Customer)'s WhatsApp marketing consent information. Shopify identifies the customer's
WhatsApp account by their [phone number](https://shopify.dev/docs/api/admin-graphql/latest/objects/CustomerPhoneNumber).

You can subscribe or unsubscribe the customer from WhatsApp marketing and
specify the [opt-in level](https://shopify.dev/docs/api/admin-graphql/latest/mutations/customerWhatsAppMarketingConsentUpdate#arguments-input.fields.whatsAppMarketingConsent.optInLevel).
You can also include when and [where](https://shopify.dev/docs/api/admin-graphql/latest/mutations/customerWhatsAppMarketingConsentUpdate#arguments-input.fields.whatsAppMarketingConsent.sourceLocationId)
the consent was collected.

- input (CustomerWhatsAppMarketingConsentUpdateInput!)

[Anchor to input](/docs/api/admin-graphql/latest/mutations/customerWhatsAppMarketingConsentUpdate#arguments-input)input •[CustomerWhatsAppMarketingConsentUpdateInput!](/docs/api/admin-graphql/latest/input-objects/CustomerWhatsAppMarketingConsentUpdateInput) required
:   Specifies the input fields to update a customer's WhatsApp marketing consent information.

    Show input fields

---

Was this section helpful?

## [Anchor to CustomerWhatsAppMarketingConsentUpdatePayload returns](/docs/api/admin-graphql/latest/mutations/customerWhatsAppMarketingConsentUpdate#returns)CustomerWhatsAppMarketingConsentUpdatePayload returns

- customerPhoneNumber (CustomerPhoneNumber)
- userErrors ([CustomerMarketingConsentError!]!)

[Anchor to customerPhoneNumber](/docs/api/admin-graphql/latest/mutations/customerWhatsAppMarketingConsentUpdate#returns-customerPhoneNumber)customerPhoneNumber •[CustomerPhoneNumber](/docs/api/admin-graphql/latest/objects/CustomerPhoneNumber)
:   The [customer phone number](https://shopify.dev/docs/api/admin-graphql/latest/objects/CustomerPhoneNumber)
    with the updated WhatsApp marketing consent information.

    Show fields

[Anchor to userErrors](/docs/api/admin-graphql/latest/mutations/customerWhatsAppMarketingConsentUpdate#returns-userErrors)userErrors •[[CustomerMarketingConsentError!]!](/docs/api/admin-graphql/latest/objects/CustomerMarketingConsentError) non-null
:   The list of errors that occurred from executing the mutation.

    Show fields

---

Was this section helpful?
