---
title: "CustomerPhoneNumber"
source: "https://shopify.dev/docs/api/admin-graphql/2026-07/objects/CustomerPhoneNumber"
final_url: "https://shopify.dev/docs/api/admin-graphql/latest/objects/CustomerPhoneNumber"
platform: "shopify"
fetched_at: "2026-09-11T09:20:10Z"
last_checked_at: "2026-09-11T10:17:58Z"
previous_fetched_at: ""
http_status: "200"
format: "html-converted"
sha256: "c1696cb359c0e6edecac2d0647d4d2a8b1f963efcb572dd868e79995b1f89fcc"
---

Choose a version:

unstable 2026-10 release candidate2026-07 latest2026-04 2026-01 2025-10 

2026-07latest

Requires `read_customers` access scope.

A phone number.

## [Anchor to Fields](/docs/api/admin-graphql/latest/objects/CustomerPhoneNumber#fields)Fields

- phoneNumber (String!)
- whatsAppMarketingConsent (CustomerWhatsAppMarketingConsent!)

[Anchor to phoneNumber](/docs/api/admin-graphql/latest/objects/CustomerPhoneNumber#field-CustomerPhoneNumber.fields.phoneNumber)phoneNumber •[String!](/docs/api/admin-graphql/latest/scalars/String) non-null
:   A customer's phone number.

[Anchor to whatsAppMarketingConsent](/docs/api/admin-graphql/latest/objects/CustomerPhoneNumber#field-CustomerPhoneNumber.fields.whatsAppMarketingConsent)whatsAppMarketingConsent •[CustomerWhatsAppMarketingConsent!](/docs/api/admin-graphql/latest/objects/CustomerWhatsAppMarketingConsent) non-null
:   The [WhatsApp marketing consent](https://shopify.dev/docs/api/admin-graphql/latest/objects/CustomerWhatsAppMarketingConsent)
    information for the customer's phone number. Update with the [`customerWhatsAppMarketingConsentUpdate`](https://shopify.dev/docs/api/admin-graphql/latest/mutations/customerWhatsAppMarketingConsentUpdate) mutation.

    Show fields

### Deprecated fields

- marketingCollectedFrom (CustomerConsentCollectedFrom): deprecated
- marketingOptInLevel (CustomerMarketingOptInLevel): deprecated
- marketingState (CustomerSmsMarketingState!): deprecated
- marketingUpdatedAt (DateTime): deprecated
- sourceLocation (Location): deprecated

[Anchor to marketingCollectedFrom](/docs/api/admin-graphql/latest/objects/CustomerPhoneNumber#field-CustomerPhoneNumber.fields.marketingCollectedFrom)marketingCollectedFrom •[CustomerConsentCollectedFrom](/docs/api/admin-graphql/latest/enums/CustomerConsentCollectedFrom) Deprecated
:   Show enum values

[Anchor to marketingOptInLevel](/docs/api/admin-graphql/latest/objects/CustomerPhoneNumber#field-CustomerPhoneNumber.fields.marketingOptInLevel)marketingOptInLevel •[CustomerMarketingOptInLevel](/docs/api/admin-graphql/latest/enums/CustomerMarketingOptInLevel) Deprecated
:   Show enum values

[Anchor to marketingState](/docs/api/admin-graphql/latest/objects/CustomerPhoneNumber#field-CustomerPhoneNumber.fields.marketingState)marketingState •[CustomerSmsMarketingState!](/docs/api/admin-graphql/latest/enums/CustomerSmsMarketingState) non-nullDeprecated
:   Show enum values

[Anchor to marketingUpdatedAt](/docs/api/admin-graphql/latest/objects/CustomerPhoneNumber#field-CustomerPhoneNumber.fields.marketingUpdatedAt)marketingUpdatedAt •[DateTime](/docs/api/admin-graphql/latest/scalars/DateTime) Deprecated

[Anchor to sourceLocation](/docs/api/admin-graphql/latest/objects/CustomerPhoneNumber#field-CustomerPhoneNumber.fields.sourceLocation)sourceLocation •[Location](/docs/api/admin-graphql/latest/objects/Location) Deprecated
:   Show fields

---

Was this section helpful?

---

## [Anchor to Mutations](/docs/api/admin-graphql/latest/objects/CustomerPhoneNumber#mutations)Mutations

- customerWhatsAppMarketingConsentUpdate (CustomerWhatsAppMarketingConsentUpdatePayload)

[Anchor to customerWhatsAppMarketingConsentUpdate](/docs/api/admin-graphql/latest/objects/CustomerPhoneNumber#mutation-customerWhatsAppMarketingConsentUpdate)[customerWhatsAppMarketingConsentUpdate](/docs/api/admin-graphql/latest/mutations/customerWhatsAppMarketingConsentUpdate) •mutation
:   Updates a [customer](https://shopify.dev/docs/api/admin-graphql/latest/objects/Customer)'s WhatsApp marketing consent information. Shopify identifies the customer's
    WhatsApp account by their [phone number](https://shopify.dev/docs/api/admin-graphql/latest/objects/CustomerPhoneNumber).

    You can subscribe or unsubscribe the customer from WhatsApp marketing and
    specify the [opt-in level](https://shopify.dev/docs/api/admin-graphql/latest/mutations/customerWhatsAppMarketingConsentUpdate#arguments-input.fields.whatsAppMarketingConsent.optInLevel).
    You can also include when and [where](https://shopify.dev/docs/api/admin-graphql/latest/mutations/customerWhatsAppMarketingConsentUpdate#arguments-input.fields.whatsAppMarketingConsent.sourceLocationId)
    the consent was collected.

    Show payload

    ### Arguments

    [Anchor to input](/docs/api/admin-graphql/latest/objects/CustomerPhoneNumber#mutation-customerWhatsAppMarketingConsentUpdate.arguments.input)input •[CustomerWhatsAppMarketingConsentUpdateInput!](/docs/api/admin-graphql/latest/input-objects/CustomerWhatsAppMarketingConsentUpdateInput) required
    :   Specifies the input fields to update a customer's WhatsApp marketing consent information.

        Show input fields

    ---

---

Was this section helpful?
