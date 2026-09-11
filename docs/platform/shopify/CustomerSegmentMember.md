---
title: "CustomerSegmentMember"
source: "https://shopify.dev/docs/api/admin-graphql/2026-07/objects/CustomerSegmentMember"
final_url: "https://shopify.dev/docs/api/admin-graphql/latest/objects/CustomerSegmentMember"
platform: "shopify"
fetched_at: "2026-09-11T09:20:10Z"
last_checked_at: "2026-09-11T10:17:58Z"
previous_fetched_at: ""
http_status: "200"
format: "html-converted"
sha256: "44828f6a5b23bff938205863c033f414cf4e157ca9cad33763b696f7c8f439ce"
---

Choose a version:

unstable 2026-10 release candidate2026-07 latest2026-04 2026-01 2025-10 

2026-07latest

Requires `read_customers` access scope. Also: The user must not have restricted access.

The member of a segment.

## [Anchor to Fields](/docs/api/admin-graphql/latest/objects/CustomerSegmentMember#fields)Fields

- amountSpent (MoneyV2)
- defaultAddress (MailingAddress)
- defaultEmailAddress (CustomerEmailAddress)
- defaultPhoneNumber (CustomerPhoneNumber)
- displayName (String!)
- firstName (String)
- id (ID!)
- lastName (String)
- lastOrderId (ID)
- mergeable (CustomerMergeable!)
- metafield (Metafield)
- metafields (MetafieldConnection!)
- note (String)
- numberOfOrders (UnsignedInt64)

[Anchor to amountSpent](/docs/api/admin-graphql/latest/objects/CustomerSegmentMember#field-CustomerSegmentMember.fields.amountSpent)amountSpent •[MoneyV2](/docs/api/admin-graphql/latest/objects/MoneyV2)
:   The total amount of money that the member has spent on orders.

    Show fields

[Anchor to defaultAddress](/docs/api/admin-graphql/latest/objects/CustomerSegmentMember#field-CustomerSegmentMember.fields.defaultAddress)defaultAddress •[MailingAddress](/docs/api/admin-graphql/latest/objects/MailingAddress)
:   The member's default address.

    Show fields

[Anchor to defaultEmailAddress](/docs/api/admin-graphql/latest/objects/CustomerSegmentMember#field-CustomerSegmentMember.fields.defaultEmailAddress)defaultEmailAddress •[CustomerEmailAddress](/docs/api/admin-graphql/latest/objects/CustomerEmailAddress)
:   The member's default email address.

    Show fields

[Anchor to defaultPhoneNumber](/docs/api/admin-graphql/latest/objects/CustomerSegmentMember#field-CustomerSegmentMember.fields.defaultPhoneNumber)defaultPhoneNumber •[CustomerPhoneNumber](/docs/api/admin-graphql/latest/objects/CustomerPhoneNumber)
:   The member's default phone number.

    Show fields

[Anchor to displayName](/docs/api/admin-graphql/latest/objects/CustomerSegmentMember#field-CustomerSegmentMember.fields.displayName)displayName •[String!](/docs/api/admin-graphql/latest/scalars/String) non-null
:   The full name of the member, which is based on the values of the `first_name`
    and `last_name` fields. If the member's first name and last name aren't
    available, then the customer's email address is used. If the customer's email
    address isn't available, then the customer's phone number is used.

[Anchor to firstName](/docs/api/admin-graphql/latest/objects/CustomerSegmentMember#field-CustomerSegmentMember.fields.firstName)firstName •[String](/docs/api/admin-graphql/latest/scalars/String)
:   The member's first name.

[Anchor to id](/docs/api/admin-graphql/latest/objects/CustomerSegmentMember#field-CustomerSegmentMember.fields.id)id •[ID!](/docs/api/admin-graphql/latest/scalars/ID) non-null
:   The member’s ID.

[Anchor to lastName](/docs/api/admin-graphql/latest/objects/CustomerSegmentMember#field-CustomerSegmentMember.fields.lastName)lastName •[String](/docs/api/admin-graphql/latest/scalars/String)
:   The member's last name.

[Anchor to lastOrderId](/docs/api/admin-graphql/latest/objects/CustomerSegmentMember#field-CustomerSegmentMember.fields.lastOrderId)lastOrderId •[ID](/docs/api/admin-graphql/latest/scalars/ID)
:   The ID of the member's most recent order.

[Anchor to mergeable](/docs/api/admin-graphql/latest/objects/CustomerSegmentMember#field-CustomerSegmentMember.fields.mergeable)mergeable •[CustomerMergeable!](/docs/api/admin-graphql/latest/objects/CustomerMergeable) non-null
:   Whether the customer can be merged with another customer.

    Show fields

[Anchor to metafield](/docs/api/admin-graphql/latest/objects/CustomerSegmentMember#field-CustomerSegmentMember.fields.metafield)metafield •[Metafield](/docs/api/admin-graphql/latest/objects/Metafield)
:   A [custom field](https://shopify.dev/docs/apps/build/custom-data),
    including its `namespace` and `key`, that's associated with a Shopify resource
    for the purposes of adding and storing additional information.

    Show fields

    ### Arguments

    [Anchor to key](/docs/api/admin-graphql/latest/objects/CustomerSegmentMember#field-CustomerSegmentMember.fields.metafield.arguments.key)key •[String!](/docs/api/admin-graphql/latest/scalars/String) required
    :   The key for the metafield.

    [Anchor to namespace](/docs/api/admin-graphql/latest/objects/CustomerSegmentMember#field-CustomerSegmentMember.fields.metafield.arguments.namespace)namespace •[String](/docs/api/admin-graphql/latest/scalars/String)
    :   The container the metafield belongs to. If omitted, the app-reserved namespace will be used.

    ---

[Anchor to metafields](/docs/api/admin-graphql/latest/objects/CustomerSegmentMember#field-CustomerSegmentMember.fields.metafields)metafields •[MetafieldConnection!](/docs/api/admin-graphql/latest/connections/MetafieldConnection) non-null
:   A list of [custom fields](https://shopify.dev/docs/apps/build/custom-data)
    that a merchant associates with a Shopify resource.

    Show fields

    ### Arguments

    [Anchor to after](/docs/api/admin-graphql/latest/objects/CustomerSegmentMember#field-CustomerSegmentMember.fields.metafields.arguments.after)after •[String](/docs/api/admin-graphql/latest/scalars/String)
    :   The elements that come after the specified [cursor](https://shopify.dev/api/usage/pagination-graphql).

    [Anchor to before](/docs/api/admin-graphql/latest/objects/CustomerSegmentMember#field-CustomerSegmentMember.fields.metafields.arguments.before)before •[String](/docs/api/admin-graphql/latest/scalars/String)
    :   The elements that come before the specified [cursor](https://shopify.dev/api/usage/pagination-graphql).

    [Anchor to first](/docs/api/admin-graphql/latest/objects/CustomerSegmentMember#field-CustomerSegmentMember.fields.metafields.arguments.first)first •[Int](/docs/api/admin-graphql/latest/scalars/Int)
    :   The first `n` elements from the [paginated list](https://shopify.dev/api/usage/pagination-graphql).

    [Anchor to keys](/docs/api/admin-graphql/latest/objects/CustomerSegmentMember#field-CustomerSegmentMember.fields.metafields.arguments.keys)keys •[[String!]](/docs/api/admin-graphql/latest/scalars/String)
    :   List of keys of metafields in the format `namespace.key`, will be returned in the same format.

    [Anchor to last](/docs/api/admin-graphql/latest/objects/CustomerSegmentMember#field-CustomerSegmentMember.fields.metafields.arguments.last)last •[Int](/docs/api/admin-graphql/latest/scalars/Int)
    :   The last `n` elements from the [paginated list](https://shopify.dev/api/usage/pagination-graphql).

    [Anchor to namespace](/docs/api/admin-graphql/latest/objects/CustomerSegmentMember#field-CustomerSegmentMember.fields.metafields.arguments.namespace)namespace •[String](/docs/api/admin-graphql/latest/scalars/String)
    :   The metafield namespace to filter by. If omitted, all metafields are returned.

    [Anchor to reverse](/docs/api/admin-graphql/latest/objects/CustomerSegmentMember#field-CustomerSegmentMember.fields.metafields.arguments.reverse)reverse •[Boolean](/docs/api/admin-graphql/latest/scalars/Boolean) Default:false
    :   Reverse the order of the underlying list.

    ---

[Anchor to note](/docs/api/admin-graphql/latest/objects/CustomerSegmentMember#field-CustomerSegmentMember.fields.note)note •[String](/docs/api/admin-graphql/latest/scalars/String)
:   A note about the member.

[Anchor to numberOfOrders](/docs/api/admin-graphql/latest/objects/CustomerSegmentMember#field-CustomerSegmentMember.fields.numberOfOrders)numberOfOrders •[UnsignedInt64](/docs/api/admin-graphql/latest/scalars/UnsignedInt64)
:   The total number of orders that the member has made.

---

Was this section helpful?

---

## [Anchor to Queries](/docs/api/admin-graphql/latest/objects/CustomerSegmentMember#queries)Queries

- customerSegmentMembers (CustomerSegmentMemberConnection!)

[Anchor to customerSegmentMembers](/docs/api/admin-graphql/latest/objects/CustomerSegmentMember#query-customerSegmentMembers)[customerSegmentMembers](/docs/api/admin-graphql/latest/queries/customerSegmentMembers) •query
:   A paginated list of customers that belong to an individual [`Segment`](https://shopify.dev/docs/api/admin-graphql/latest/objects/Segment).
    Segments group customers based on criteria defined through [ShopifyQL queries](https://shopify.dev/docs/api/shopifyql/segment-query-language-reference).
    Access segment members with their profile information and purchase summary
    data. The connection includes statistics for analyzing segment attributes
    (such as average and sum calculations) and a total count of all members.
    The maximum page size is 1000.

    Show fields

    ### Arguments

    [Anchor to after](/docs/api/admin-graphql/latest/objects/CustomerSegmentMember#query-customerSegmentMembers.arguments.after)after •[String](/docs/api/admin-graphql/latest/scalars/String)
    :   The elements that come after the specified [cursor](https://shopify.dev/api/usage/pagination-graphql).

    [Anchor to before](/docs/api/admin-graphql/latest/objects/CustomerSegmentMember#query-customerSegmentMembers.arguments.before)before •[String](/docs/api/admin-graphql/latest/scalars/String)
    :   The elements that come before the specified [cursor](https://shopify.dev/api/usage/pagination-graphql).

    [Anchor to first](/docs/api/admin-graphql/latest/objects/CustomerSegmentMember#query-customerSegmentMembers.arguments.first)first •[Int](/docs/api/admin-graphql/latest/scalars/Int)
    :   The first `n` elements from the [paginated list](https://shopify.dev/api/usage/pagination-graphql).

    [Anchor to last](/docs/api/admin-graphql/latest/objects/CustomerSegmentMember#query-customerSegmentMembers.arguments.last)last •[Int](/docs/api/admin-graphql/latest/scalars/Int)
    :   The last `n` elements from the [paginated list](https://shopify.dev/api/usage/pagination-graphql).

    [Anchor to query](/docs/api/admin-graphql/latest/objects/CustomerSegmentMember#query-customerSegmentMembers.arguments.query)query •[String](/docs/api/admin-graphql/latest/scalars/String)
    :   The query that's used to filter the members. The query is composed of a
        combination of conditions on facts about customers such as
        `email_subscription_status = 'SUBSCRIBED'` with [this
        syntax](https://shopify.dev/api/shopifyql/segment-query-language-reference).

    [Anchor to queryId](/docs/api/admin-graphql/latest/objects/CustomerSegmentMember#query-customerSegmentMembers.arguments.queryId)queryId •[ID](/docs/api/admin-graphql/latest/scalars/ID)
    :   The ID of the segment members query.

    [Anchor to reverse](/docs/api/admin-graphql/latest/objects/CustomerSegmentMember#query-customerSegmentMembers.arguments.reverse)reverse •[Boolean](/docs/api/admin-graphql/latest/scalars/Boolean) Default:false
    :   Reverse the order of the list. The sorting behaviour defaults to ascending order.

    [Anchor to segmentId](/docs/api/admin-graphql/latest/objects/CustomerSegmentMember#query-customerSegmentMembers.arguments.segmentId)segmentId •[ID](/docs/api/admin-graphql/latest/scalars/ID)
    :   The ID of the segment.

    [Anchor to sortKey](/docs/api/admin-graphql/latest/objects/CustomerSegmentMember#query-customerSegmentMembers.arguments.sortKey)sortKey •[String](/docs/api/admin-graphql/latest/scalars/String)
    :   Sort the list by a given key. Valid values:
        • `created_at` - Sort by customer creation date
        • `first_order_date` - Sort by the date of the customer's first order
        • `last_abandoned_order_date` - Sort by the date of the customer's last abandoned checkout
        • `last_order_date` - Sort by the date of the customer's most recent order
        • `number_of_orders` - Sort by the total number of orders placed by the customer
        • `amount_spent` - Sort by the total amount the customer has spent across all orders

        Use with the `reverse` parameter to control sort direction (ascending by default, descending when reverse=true).

    [Anchor to timezone](/docs/api/admin-graphql/latest/objects/CustomerSegmentMember#query-customerSegmentMembers.arguments.timezone)timezone •[String](/docs/api/admin-graphql/latest/scalars/String)
    :   The timezone that's used to interpret relative date arguments. The timezone
        defaults to UTC if the timezone isn't provided.

    ---

---

Was this section helpful?

---

## [Anchor to Interfaces](/docs/api/admin-graphql/latest/objects/CustomerSegmentMember#interfaces)Interfaces

- HasMetafields

[Anchor to HasMetafields](/docs/api/admin-graphql/latest/objects/CustomerSegmentMember#interface-HasMetafields)[HasMetafields](/docs/api/admin-graphql/latest/interfaces/HasMetafields) •interface

---

Was this section helpful?
