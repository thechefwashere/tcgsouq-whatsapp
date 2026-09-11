---
title: "WebhookSubscriptionTopic"
source: "https://shopify.dev/docs/api/admin-graphql/2026-07/enums/WebhookSubscriptionTopic"
final_url: "https://shopify.dev/docs/api/admin-graphql/latest/enums/WebhookSubscriptionTopic"
platform: "shopify"
fetched_at: "2026-09-11T09:20:10Z"
last_checked_at: "2026-09-11T10:17:58Z"
previous_fetched_at: ""
http_status: "200"
format: "html-converted"
sha256: "40a93e8e227faca9cdafe24347bf1ca246e845d1aca5e769de2edcc84aa373b7"
---

Choose a version:

unstable 2026-10 release candidate2026-07 latest2026-04 2026-01 2025-10 

2026-07latest

The supported topics for webhook subscriptions. You can use webhook subscriptions to receive
notifications about particular events in a shop.

You create [mandatory webhooks](https://shopify.dev/apps/webhooks/configuration/mandatory-webhooks#mandatory-compliance-webhooks) either via the
[Partner Dashboard](https://shopify.dev/apps/webhooks/configuration/mandatory-webhooks#subscribe-to-privacy-webhooks)
or by updating the [app configuration file](https://shopify.dev/apps/tools/cli/configuration#app-configuration-file-example).

---

Tip

To configure your subscription using the app configuration file, refer to the
[full list of topic
names](https://shopify.dev/docs/api/webhooks?reference=graphql).

**Tip:**

To configure your subscription using the app configuration file, refer to the
[full list of topic
names](https://shopify.dev/docs/api/webhooks?reference=graphql).

**Tip:** To configure your subscription using the app configuration file, refer to the
<a href="https://shopify.dev/docs/api/webhooks?reference=graphql">full list of topic
names</a>.

---

## [Anchor to Valid values](/docs/api/admin-graphql/latest/enums/WebhookSubscriptionTopic#valid-values)Valid values

- APP\_PURCHASES\_ONE\_TIME\_UPDATE
- APP\_SCOPES\_UPDATE
- APP\_SUBSCRIPTIONS\_APPROACHING\_CAPPED\_AMOUNT
- APP\_SUBSCRIPTIONS\_UPDATE
- APP\_UNINSTALLED
- AUDIT\_EVENTS\_ADMIN\_API\_ACTIVITY
- BULK\_OPERATIONS\_FINISH
- CARTS\_CREATE
- CARTS\_UPDATE
- CHANNELS\_DELETE
- CHECKOUTS\_CREATE
- CHECKOUTS\_DELETE
- CHECKOUTS\_UPDATE
- COLLECTION\_LISTINGS\_ADD
- COLLECTION\_LISTINGS\_REMOVE
- COLLECTION\_LISTINGS\_UPDATE
- COLLECTION\_PUBLICATIONS\_CREATE
- COLLECTION\_PUBLICATIONS\_DELETE
- COLLECTION\_PUBLICATIONS\_UPDATE
- COLLECTIONS\_CREATE
- COLLECTIONS\_DELETE
- COLLECTIONS\_UPDATE
- COMPANIES\_CREATE
- COMPANIES\_DELETE
- COMPANIES\_UPDATE
- COMPANY\_CONTACT\_ROLES\_ASSIGN
- COMPANY\_CONTACT\_ROLES\_REVOKE
- COMPANY\_CONTACTS\_CREATE
- COMPANY\_CONTACTS\_DELETE
- COMPANY\_CONTACTS\_UPDATE
- COMPANY\_LOCATIONS\_CREATE
- COMPANY\_LOCATIONS\_DELETE
- COMPANY\_LOCATIONS\_UPDATE
- CUSTOMER\_ACCOUNT\_SETTINGS\_UPDATE
- CUSTOMER\_GROUPS\_CREATE
- CUSTOMER\_GROUPS\_DELETE
- CUSTOMER\_GROUPS\_UPDATE
- CUSTOMER\_JOINED\_SEGMENT
- CUSTOMER\_LEFT\_SEGMENT
- CUSTOMER\_PAYMENT\_METHODS\_CREATE
- CUSTOMER\_PAYMENT\_METHODS\_REVOKE
- CUSTOMER\_PAYMENT\_METHODS\_UPDATE
- CUSTOMER\_TAGS\_ADDED
- CUSTOMER\_TAGS\_REMOVED
- CUSTOMERS\_CREATE
- CUSTOMERS\_DELETE
- CUSTOMERS\_DISABLE
- CUSTOMERS\_EMAIL\_MARKETING\_CONSENT\_UPDATE
- CUSTOMERS\_ENABLE
- CUSTOMERS\_MARKETING\_CONSENT\_UPDATE
- CUSTOMERS\_MERGE
- CUSTOMERS\_PURCHASING\_SUMMARY
- CUSTOMERS\_UPDATE
- CUSTOMERS\_WHATS\_APP\_MARKETING\_CONSENT\_UPDATE
- DELIVERY\_PROMISE\_SETTINGS\_UPDATE
- DISCOUNTS\_CREATE
- DISCOUNTS\_DELETE
- DISCOUNTS\_REDEEMCODE\_ADDED
- DISCOUNTS\_REDEEMCODE\_REMOVED
- DISCOUNTS\_UPDATE
- DISPUTES\_CREATE
- DISPUTES\_UPDATE
- DOMAINS\_CREATE
- DOMAINS\_DESTROY
- DOMAINS\_UPDATE
- DRAFT\_ORDERS\_CREATE
- DRAFT\_ORDERS\_DELETE
- DRAFT\_ORDERS\_UPDATE
- FINANCE\_APP\_STAFF\_MEMBER\_DELETE
- FINANCE\_APP\_STAFF\_MEMBER\_GRANT
- FINANCE\_APP\_STAFF\_MEMBER\_REVOKE
- FINANCE\_APP\_STAFF\_MEMBER\_UPDATE
- FINANCE\_KYC\_INFORMATION\_UPDATE
- FULFILLMENT\_EVENTS\_CREATE
- FULFILLMENT\_EVENTS\_DELETE
- FULFILLMENT\_HOLDS\_ADDED
- FULFILLMENT\_HOLDS\_RELEASED
- FULFILLMENT\_ORDERS\_CANCELLATION\_REQUEST\_ACCEPTED
- FULFILLMENT\_ORDERS\_CANCELLATION\_REQUEST\_REJECTED
- FULFILLMENT\_ORDERS\_CANCELLATION\_REQUEST\_SUBMITTED
- FULFILLMENT\_ORDERS\_CANCELLED
- FULFILLMENT\_ORDERS\_FULFILLMENT\_REQUEST\_ACCEPTED
- FULFILLMENT\_ORDERS\_FULFILLMENT\_REQUEST\_REJECTED
- FULFILLMENT\_ORDERS\_FULFILLMENT\_REQUEST\_SUBMITTED
- FULFILLMENT\_ORDERS\_FULFILLMENT\_SERVICE\_FAILED\_TO\_COMPLETE
- FULFILLMENT\_ORDERS\_HOLD\_RELEASED
- FULFILLMENT\_ORDERS\_LINE\_ITEMS\_PREPARED\_FOR\_LOCAL\_DELIVERY
- FULFILLMENT\_ORDERS\_LINE\_ITEMS\_PREPARED\_FOR\_PICKUP
- FULFILLMENT\_ORDERS\_MANUALLY\_REPORTED\_PROGRESS\_STOPPED
- FULFILLMENT\_ORDERS\_MERGED
- FULFILLMENT\_ORDERS\_MOVED
- FULFILLMENT\_ORDERS\_ORDER\_ROUTING\_COMPLETE
- FULFILLMENT\_ORDERS\_PLACED\_ON\_HOLD
- FULFILLMENT\_ORDERS\_PROGRESS\_REPORTED
- FULFILLMENT\_ORDERS\_RESCHEDULED
- FULFILLMENT\_ORDERS\_SCHEDULED\_FULFILLMENT\_ORDER\_READY
- FULFILLMENT\_ORDERS\_SPLIT
- FULFILLMENTS\_CREATE
- FULFILLMENTS\_UPDATE
- INVENTORY\_ITEMS\_CREATE
- INVENTORY\_ITEMS\_DELETE
- INVENTORY\_ITEMS\_UPDATE
- INVENTORY\_LEVELS\_CONNECT
- INVENTORY\_LEVELS\_DISCONNECT
- INVENTORY\_LEVELS\_UPDATE
- INVENTORY\_SHIPMENTS\_ADD\_ITEMS
- INVENTORY\_SHIPMENTS\_CREATE
- INVENTORY\_SHIPMENTS\_DELETE
- INVENTORY\_SHIPMENTS\_MARK\_IN\_TRANSIT
- INVENTORY\_SHIPMENTS\_RECEIVE\_ITEMS
- INVENTORY\_SHIPMENTS\_REMOVE\_ITEMS
- INVENTORY\_SHIPMENTS\_UPDATE\_ITEM\_QUANTITIES
- INVENTORY\_SHIPMENTS\_UPDATE\_TRACKING
- INVENTORY\_TRANSFERS\_ADD\_ITEMS
- INVENTORY\_TRANSFERS\_CANCEL
- INVENTORY\_TRANSFERS\_COMPLETE
- INVENTORY\_TRANSFERS\_READY\_TO\_SHIP
- INVENTORY\_TRANSFERS\_REMOVE\_ITEMS
- INVENTORY\_TRANSFERS\_UPDATE\_ITEM\_QUANTITIES
- INVENTORY\_TRANSFERS\_UPDATED
- LOCALES\_CREATE
- LOCALES\_DESTROY
- LOCALES\_UPDATE
- LOCATIONS\_ACTIVATE
- LOCATIONS\_CREATE
- LOCATIONS\_DEACTIVATE
- LOCATIONS\_DELETE
- LOCATIONS\_UPDATE
- MARKETS\_BACKUP\_REGION\_UPDATE
- MARKETS\_CREATE
- MARKETS\_DELETE
- MARKETS\_UPDATE
- METAFIELD\_DEFINITIONS\_CREATE
- METAFIELD\_DEFINITIONS\_DELETE
- METAFIELD\_DEFINITIONS\_UPDATE
- METAOBJECTS\_CREATE
- METAOBJECTS\_DELETE
- METAOBJECTS\_UPDATE
- ORDER\_TRANSACTIONS\_CREATE
- ORDERS\_CANCELLED
- ORDERS\_CREATE
- ORDERS\_DELETE
- ORDERS\_EDITED
- ORDERS\_FULFILLED
- ORDERS\_LINK\_REQUESTED
- ORDERS\_PAID
- ORDERS\_PARTIALLY\_FULFILLED
- ORDERS\_RISK\_ASSESSMENT\_CHANGED
- ORDERS\_SHOPIFY\_PROTECT\_ELIGIBILITY\_CHANGED
- ORDERS\_UPDATED
- PAYMENT\_SCHEDULES\_DUE
- PAYMENT\_TERMS\_CREATE
- PAYMENT\_TERMS\_DELETE
- PAYMENT\_TERMS\_UPDATE
- PRODUCT\_FEEDS\_CREATE
- PRODUCT\_FEEDS\_FULL\_SYNC
- PRODUCT\_FEEDS\_FULL\_SYNC\_FINISH
- PRODUCT\_FEEDS\_INCREMENTAL\_SYNC
- PRODUCT\_FEEDS\_UPDATE
- PRODUCT\_LISTINGS\_ADD
- PRODUCT\_LISTINGS\_REMOVE
- PRODUCT\_LISTINGS\_UPDATE
- PRODUCT\_PUBLICATIONS\_CREATE
- PRODUCT\_PUBLICATIONS\_DELETE
- PRODUCT\_PUBLICATIONS\_UPDATE
- PRODUCTS\_CREATE
- PRODUCTS\_DELETE
- PRODUCTS\_UPDATE
- PROFILES\_CREATE
- PROFILES\_DELETE
- PROFILES\_UPDATE
- REFUNDS\_CREATE
- RETURNS\_APPROVE
- RETURNS\_CANCEL
- RETURNS\_CLOSE
- RETURNS\_DECLINE
- RETURNS\_PROCESS
- RETURNS\_REOPEN
- RETURNS\_REQUEST
- RETURNS\_UPDATE
- REVERSE\_DELIVERIES\_ATTACH\_DELIVERABLE
- REVERSE\_FULFILLMENT\_ORDERS\_DISPOSE
- SCHEDULED\_PRODUCT\_LISTINGS\_ADD
- SCHEDULED\_PRODUCT\_LISTINGS\_REMOVE
- SCHEDULED\_PRODUCT\_LISTINGS\_UPDATE
- SEGMENTS\_CREATE
- SEGMENTS\_DELETE
- SEGMENTS\_UPDATE
- SELLING\_PLAN\_GROUPS\_CREATE
- SELLING\_PLAN\_GROUPS\_DELETE
- SELLING\_PLAN\_GROUPS\_UPDATE
- SHIPPING\_ADDRESSES\_CREATE
- SHIPPING\_ADDRESSES\_UPDATE
- SHOP\_UPDATE
- SUBSCRIPTION\_BILLING\_ATTEMPTS\_CHALLENGED
- SUBSCRIPTION\_BILLING\_ATTEMPTS\_FAILURE
- SUBSCRIPTION\_BILLING\_ATTEMPTS\_SUCCESS
- SUBSCRIPTION\_BILLING\_CYCLE\_EDITS\_CREATE
- SUBSCRIPTION\_BILLING\_CYCLE\_EDITS\_DELETE
- SUBSCRIPTION\_BILLING\_CYCLE\_EDITS\_UPDATE
- SUBSCRIPTION\_BILLING\_CYCLES\_SKIP
- SUBSCRIPTION\_BILLING\_CYCLES\_UNSKIP
- SUBSCRIPTION\_CONTRACTS\_ACTIVATE
- SUBSCRIPTION\_CONTRACTS\_CANCEL
- SUBSCRIPTION\_CONTRACTS\_CREATE
- SUBSCRIPTION\_CONTRACTS\_EXPIRE
- SUBSCRIPTION\_CONTRACTS\_FAIL
- SUBSCRIPTION\_CONTRACTS\_PAUSE
- SUBSCRIPTION\_CONTRACTS\_UPDATE
- TAX\_SERVICES\_CREATE
- TAX\_SERVICES\_UPDATE
- TENDER\_TRANSACTIONS\_CREATE
- THEMES\_CREATE
- THEMES\_DELETE
- THEMES\_PUBLISH
- THEMES\_UPDATE
- VARIANTS\_IN\_STOCK
- VARIANTS\_OUT\_OF\_STOCK

[Anchor to APP\_PURCHASES\_ONE\_TIME\_UPDATE](/docs/api/admin-graphql/latest/enums/WebhookSubscriptionTopic#enums-APP_PURCHASES_ONE_TIME_UPDATE)APP\_PURCHASES\_ONE\_TIME\_UPDATE
:   The webhook topic for `app_purchases_one_time/update` events. Occurs whenever a one-time app charge is updated.

[Anchor to APP\_SCOPES\_UPDATE](/docs/api/admin-graphql/latest/enums/WebhookSubscriptionTopic#enums-APP_SCOPES_UPDATE)APP\_SCOPES\_UPDATE
:   The webhook topic for `app/scopes_update` events. Occurs whenever the access
    scopes of any installation are modified. Allows apps to keep track of the
    granted access scopes of their installations.

[Anchor to APP\_SUBSCRIPTIONS\_APPROACHING\_CAPPED\_AMOUNT](/docs/api/admin-graphql/latest/enums/WebhookSubscriptionTopic#enums-APP_SUBSCRIPTIONS_APPROACHING_CAPPED_AMOUNT)APP\_SUBSCRIPTIONS\_APPROACHING\_CAPPED\_AMOUNT
:   The webhook topic for `app_subscriptions/approaching_capped_amount` events.
    Occurs when the balance used on an app subscription crosses 90% of the capped amount.

[Anchor to APP\_SUBSCRIPTIONS\_UPDATE](/docs/api/admin-graphql/latest/enums/WebhookSubscriptionTopic#enums-APP_SUBSCRIPTIONS_UPDATE)APP\_SUBSCRIPTIONS\_UPDATE
:   The webhook topic for `app_subscriptions/update` events. Occurs whenever an app subscription is updated.

[Anchor to APP\_UNINSTALLED](/docs/api/admin-graphql/latest/enums/WebhookSubscriptionTopic#enums-APP_UNINSTALLED)APP\_UNINSTALLED
:   The webhook topic for `app/uninstalled` events. Occurs whenever a shop has uninstalled the app.

[Anchor to AUDIT\_EVENTS\_ADMIN\_API\_ACTIVITY](/docs/api/admin-graphql/latest/enums/WebhookSubscriptionTopic#enums-AUDIT_EVENTS_ADMIN_API_ACTIVITY)AUDIT\_EVENTS\_ADMIN\_API\_ACTIVITY
:   The webhook topic for `audit_events/admin_api_activity` events. Triggers for
    each auditable Admin API request. This topic is limited to one active
    subscription per Plus store and requires the use of Google Cloud Pub/Sub or
    AWS EventBridge. Requires the `read_audit_events` scope.

[Anchor to BULK\_OPERATIONS\_FINISH](/docs/api/admin-graphql/latest/enums/WebhookSubscriptionTopic#enums-BULK_OPERATIONS_FINISH)BULK\_OPERATIONS\_FINISH
:   The webhook topic for `bulk_operations/finish` events. Notifies when a Bulk Operation finishes.

[Anchor to CARTS\_CREATE](/docs/api/admin-graphql/latest/enums/WebhookSubscriptionTopic#enums-CARTS_CREATE)CARTS\_CREATE
:   The webhook topic for `carts/create` events. Occurs when a cart is created in
    the online store. Other types of carts aren't supported. For example, the
    webhook doesn't support carts that are created in a custom storefront.
    Requires the `read_orders` scope.

[Anchor to CARTS\_UPDATE](/docs/api/admin-graphql/latest/enums/WebhookSubscriptionTopic#enums-CARTS_UPDATE)CARTS\_UPDATE
:   The webhook topic for `carts/update` events. Occurs when a cart is updated in
    the online store. Other types of carts aren't supported. For example, the
    webhook doesn't support carts that are updated in a custom storefront.
    Requires the `read_orders` scope.

[Anchor to CHANNELS\_DELETE](/docs/api/admin-graphql/latest/enums/WebhookSubscriptionTopic#enums-CHANNELS_DELETE)CHANNELS\_DELETE
:   The webhook topic for `channels/delete` events. Occurs whenever a channel is
    deleted. Requires the `read_publications` scope.

[Anchor to CHECKOUTS\_CREATE](/docs/api/admin-graphql/latest/enums/WebhookSubscriptionTopic#enums-CHECKOUTS_CREATE)CHECKOUTS\_CREATE
:   The webhook topic for `checkouts/create` events. Occurs whenever a checkout is created. Requires the `read_orders` scope.

[Anchor to CHECKOUTS\_DELETE](/docs/api/admin-graphql/latest/enums/WebhookSubscriptionTopic#enums-CHECKOUTS_DELETE)CHECKOUTS\_DELETE
:   The webhook topic for `checkouts/delete` events. Occurs whenever a checkout is deleted. Requires the `read_orders` scope.

[Anchor to CHECKOUTS\_UPDATE](/docs/api/admin-graphql/latest/enums/WebhookSubscriptionTopic#enums-CHECKOUTS_UPDATE)CHECKOUTS\_UPDATE
:   The webhook topic for `checkouts/update` events. Occurs whenever a checkout is updated. Requires the `read_orders` scope.

[Anchor to COLLECTION\_LISTINGS\_ADD](/docs/api/admin-graphql/latest/enums/WebhookSubscriptionTopic#enums-COLLECTION_LISTINGS_ADD)COLLECTION\_LISTINGS\_ADD
:   The webhook topic for `collection_listings/add` events. Occurs whenever a
    collection listing is added. Requires the `read_product_listings` scope.

[Anchor to COLLECTION\_LISTINGS\_REMOVE](/docs/api/admin-graphql/latest/enums/WebhookSubscriptionTopic#enums-COLLECTION_LISTINGS_REMOVE)COLLECTION\_LISTINGS\_REMOVE
:   The webhook topic for `collection_listings/remove` events. Occurs whenever a
    collection listing is removed. Requires the `read_product_listings` scope.

[Anchor to COLLECTION\_LISTINGS\_UPDATE](/docs/api/admin-graphql/latest/enums/WebhookSubscriptionTopic#enums-COLLECTION_LISTINGS_UPDATE)COLLECTION\_LISTINGS\_UPDATE
:   The webhook topic for `collection_listings/update` events. Occurs whenever a
    collection listing is updated. Requires the `read_product_listings` scope.

[Anchor to COLLECTION\_PUBLICATIONS\_CREATE](/docs/api/admin-graphql/latest/enums/WebhookSubscriptionTopic#enums-COLLECTION_PUBLICATIONS_CREATE)COLLECTION\_PUBLICATIONS\_CREATE
:   The webhook topic for `collection_publications/create` events. Occurs whenever
    a collection publication listing is created. Requires the `read_publications` scope.

[Anchor to COLLECTION\_PUBLICATIONS\_DELETE](/docs/api/admin-graphql/latest/enums/WebhookSubscriptionTopic#enums-COLLECTION_PUBLICATIONS_DELETE)COLLECTION\_PUBLICATIONS\_DELETE
:   The webhook topic for `collection_publications/delete` events. Occurs whenever
    a collection publication listing is deleted. Requires the `read_publications` scope.

[Anchor to COLLECTION\_PUBLICATIONS\_UPDATE](/docs/api/admin-graphql/latest/enums/WebhookSubscriptionTopic#enums-COLLECTION_PUBLICATIONS_UPDATE)COLLECTION\_PUBLICATIONS\_UPDATE
:   The webhook topic for `collection_publications/update` events. Occurs whenever
    a collection publication listing is updated. Requires the `read_publications` scope.

[Anchor to COLLECTIONS\_CREATE](/docs/api/admin-graphql/latest/enums/WebhookSubscriptionTopic#enums-COLLECTIONS_CREATE)COLLECTIONS\_CREATE
:   The webhook topic for `collections/create` events. Occurs whenever a
    collection is created. Requires the `read_products` scope.

[Anchor to COLLECTIONS\_DELETE](/docs/api/admin-graphql/latest/enums/WebhookSubscriptionTopic#enums-COLLECTIONS_DELETE)COLLECTIONS\_DELETE
:   The webhook topic for `collections/delete` events. Occurs whenever a
    collection is deleted. Requires the `read_products` scope.

[Anchor to COLLECTIONS\_UPDATE](/docs/api/admin-graphql/latest/enums/WebhookSubscriptionTopic#enums-COLLECTIONS_UPDATE)COLLECTIONS\_UPDATE
:   The webhook topic for `collections/update` events. Occurs whenever a
    collection is updated, including when a product is manually added or removed
    from the collection or when the collection rules change. Occurs once if
    multiple products are manually added or removed from a collection at the same
    time. Not fired when attribute changes affect whether a product matches a
    collection's rules. Requires the `read_products` scope.

[Anchor to COMPANIES\_CREATE](/docs/api/admin-graphql/latest/enums/WebhookSubscriptionTopic#enums-COMPANIES_CREATE)COMPANIES\_CREATE
:   The webhook topic for `companies/create` events. Occurs whenever a company is
    created. Requires at least one of the following scopes: read\_customers,
    read\_companies.

[Anchor to COMPANIES\_DELETE](/docs/api/admin-graphql/latest/enums/WebhookSubscriptionTopic#enums-COMPANIES_DELETE)COMPANIES\_DELETE
:   The webhook topic for `companies/delete` events. Occurs whenever a company is
    deleted. Requires at least one of the following scopes: read\_customers,
    read\_companies.

[Anchor to COMPANIES\_UPDATE](/docs/api/admin-graphql/latest/enums/WebhookSubscriptionTopic#enums-COMPANIES_UPDATE)COMPANIES\_UPDATE
:   The webhook topic for `companies/update` events. Occurs whenever a company is
    updated. Requires at least one of the following scopes: read\_customers,
    read\_companies.

[Anchor to COMPANY\_CONTACT\_ROLES\_ASSIGN](/docs/api/admin-graphql/latest/enums/WebhookSubscriptionTopic#enums-COMPANY_CONTACT_ROLES_ASSIGN)COMPANY\_CONTACT\_ROLES\_ASSIGN
:   The webhook topic for `company_contact_roles/assign` events. Occurs whenever a
    role is assigned to a contact at a location. Requires at least one of the
    following scopes: read\_customers, read\_companies.

[Anchor to COMPANY\_CONTACT\_ROLES\_REVOKE](/docs/api/admin-graphql/latest/enums/WebhookSubscriptionTopic#enums-COMPANY_CONTACT_ROLES_REVOKE)COMPANY\_CONTACT\_ROLES\_REVOKE
:   The webhook topic for `company_contact_roles/revoke` events. Occurs whenever a
    role is revoked from a contact at a location. Requires at least one of the
    following scopes: read\_customers, read\_companies.

[Anchor to COMPANY\_CONTACTS\_CREATE](/docs/api/admin-graphql/latest/enums/WebhookSubscriptionTopic#enums-COMPANY_CONTACTS_CREATE)COMPANY\_CONTACTS\_CREATE
:   The webhook topic for `company_contacts/create` events. Occurs whenever a
    company contact is created. Requires at least one of the following scopes:
    read\_customers, read\_companies.

[Anchor to COMPANY\_CONTACTS\_DELETE](/docs/api/admin-graphql/latest/enums/WebhookSubscriptionTopic#enums-COMPANY_CONTACTS_DELETE)COMPANY\_CONTACTS\_DELETE
:   The webhook topic for `company_contacts/delete` events. Occurs whenever a
    company contact is deleted. Requires at least one of the following scopes:
    read\_customers, read\_companies.

[Anchor to COMPANY\_CONTACTS\_UPDATE](/docs/api/admin-graphql/latest/enums/WebhookSubscriptionTopic#enums-COMPANY_CONTACTS_UPDATE)COMPANY\_CONTACTS\_UPDATE
:   The webhook topic for `company_contacts/update` events. Occurs whenever a
    company contact is updated. Requires at least one of the following scopes:
    read\_customers, read\_companies.

[Anchor to COMPANY\_LOCATIONS\_CREATE](/docs/api/admin-graphql/latest/enums/WebhookSubscriptionTopic#enums-COMPANY_LOCATIONS_CREATE)COMPANY\_LOCATIONS\_CREATE
:   The webhook topic for `company_locations/create` events. Occurs whenever a
    company location is created. Requires at least one of the following scopes:
    read\_customers, read\_companies.

[Anchor to COMPANY\_LOCATIONS\_DELETE](/docs/api/admin-graphql/latest/enums/WebhookSubscriptionTopic#enums-COMPANY_LOCATIONS_DELETE)COMPANY\_LOCATIONS\_DELETE
:   The webhook topic for `company_locations/delete` events. Occurs whenever a
    company location is deleted. Requires at least one of the following scopes:
    read\_customers, read\_companies.

[Anchor to COMPANY\_LOCATIONS\_UPDATE](/docs/api/admin-graphql/latest/enums/WebhookSubscriptionTopic#enums-COMPANY_LOCATIONS_UPDATE)COMPANY\_LOCATIONS\_UPDATE
:   The webhook topic for `company_locations/update` events. Occurs whenever a
    company location is updated. Requires at least one of the following scopes:
    read\_customers, read\_companies.

[Anchor to CUSTOMER\_ACCOUNT\_SETTINGS\_UPDATE](/docs/api/admin-graphql/latest/enums/WebhookSubscriptionTopic#enums-CUSTOMER_ACCOUNT_SETTINGS_UPDATE)CUSTOMER\_ACCOUNT\_SETTINGS\_UPDATE
:   The webhook topic for `customer_account_settings/update` events. Triggers when merchants change customer account setting.

[Anchor to CUSTOMER\_GROUPS\_CREATE](/docs/api/admin-graphql/latest/enums/WebhookSubscriptionTopic#enums-CUSTOMER_GROUPS_CREATE)CUSTOMER\_GROUPS\_CREATE
:   The webhook topic for `customer_groups/create` events. Occurs whenever a
    customer saved search is created. Requires the `read_customers` scope.

[Anchor to CUSTOMER\_GROUPS\_DELETE](/docs/api/admin-graphql/latest/enums/WebhookSubscriptionTopic#enums-CUSTOMER_GROUPS_DELETE)CUSTOMER\_GROUPS\_DELETE
:   The webhook topic for `customer_groups/delete` events. Occurs whenever a
    customer saved search is deleted. Requires the `read_customers` scope.

[Anchor to CUSTOMER\_GROUPS\_UPDATE](/docs/api/admin-graphql/latest/enums/WebhookSubscriptionTopic#enums-CUSTOMER_GROUPS_UPDATE)CUSTOMER\_GROUPS\_UPDATE
:   The webhook topic for `customer_groups/update` events. Occurs whenever a
    customer saved search is updated. Requires the `read_customers` scope.

[Anchor to CUSTOMER\_JOINED\_SEGMENT](/docs/api/admin-graphql/latest/enums/WebhookSubscriptionTopic#enums-CUSTOMER_JOINED_SEGMENT)CUSTOMER\_JOINED\_SEGMENT
:   The webhook topic for `customer.joined_segment` events. Triggers when a
    customer joins a segment. Requires the `read_customers` scope.

[Anchor to CUSTOMER\_LEFT\_SEGMENT](/docs/api/admin-graphql/latest/enums/WebhookSubscriptionTopic#enums-CUSTOMER_LEFT_SEGMENT)CUSTOMER\_LEFT\_SEGMENT
:   The webhook topic for `customer.left_segment` events. Triggers when a customer
    leaves a segment. Requires the `read_customers` scope.

[Anchor to CUSTOMER\_PAYMENT\_METHODS\_CREATE](/docs/api/admin-graphql/latest/enums/WebhookSubscriptionTopic#enums-CUSTOMER_PAYMENT_METHODS_CREATE)CUSTOMER\_PAYMENT\_METHODS\_CREATE
:   The webhook topic for `customer_payment_methods/create` events. Occurs
    whenever a customer payment method is created. Requires the
    `read_customer_payment_methods` scope.

[Anchor to CUSTOMER\_PAYMENT\_METHODS\_REVOKE](/docs/api/admin-graphql/latest/enums/WebhookSubscriptionTopic#enums-CUSTOMER_PAYMENT_METHODS_REVOKE)CUSTOMER\_PAYMENT\_METHODS\_REVOKE
:   The webhook topic for `customer_payment_methods/revoke` events. Occurs
    whenever a customer payment method is revoked. Requires the
    `read_customer_payment_methods` scope.

[Anchor to CUSTOMER\_PAYMENT\_METHODS\_UPDATE](/docs/api/admin-graphql/latest/enums/WebhookSubscriptionTopic#enums-CUSTOMER_PAYMENT_METHODS_UPDATE)CUSTOMER\_PAYMENT\_METHODS\_UPDATE
:   The webhook topic for `customer_payment_methods/update` events. Occurs
    whenever a customer payment method is updated. Requires the
    `read_customer_payment_methods` scope.

[Anchor to CUSTOMER\_TAGS\_ADDED](/docs/api/admin-graphql/latest/enums/WebhookSubscriptionTopic#enums-CUSTOMER_TAGS_ADDED)CUSTOMER\_TAGS\_ADDED
:   The webhook topic for `customer.tags_added` events. Triggers when tags are
    added to a customer. Requires the `read_customers` scope.

[Anchor to CUSTOMER\_TAGS\_REMOVED](/docs/api/admin-graphql/latest/enums/WebhookSubscriptionTopic#enums-CUSTOMER_TAGS_REMOVED)CUSTOMER\_TAGS\_REMOVED
:   The webhook topic for `customer.tags_removed` events. Triggers when tags are
    removed from a customer. Requires the `read_customers` scope.

[Anchor to CUSTOMERS\_CREATE](/docs/api/admin-graphql/latest/enums/WebhookSubscriptionTopic#enums-CUSTOMERS_CREATE)CUSTOMERS\_CREATE
:   The webhook topic for `customers/create` events. Occurs whenever a customer is
    created. Requires the `read_customers` scope.

[Anchor to CUSTOMERS\_DELETE](/docs/api/admin-graphql/latest/enums/WebhookSubscriptionTopic#enums-CUSTOMERS_DELETE)CUSTOMERS\_DELETE
:   The webhook topic for `customers/delete` events. Occurs whenever a customer is
    deleted. Requires the `read_customers` scope.

[Anchor to CUSTOMERS\_DISABLE](/docs/api/admin-graphql/latest/enums/WebhookSubscriptionTopic#enums-CUSTOMERS_DISABLE)CUSTOMERS\_DISABLE
:   The webhook topic for `customers/disable` events. Occurs whenever a customer
    account is disabled. Requires the `read_customers` scope.

[Anchor to CUSTOMERS\_EMAIL\_MARKETING\_CONSENT\_UPDATE](/docs/api/admin-graphql/latest/enums/WebhookSubscriptionTopic#enums-CUSTOMERS_EMAIL_MARKETING_CONSENT_UPDATE)CUSTOMERS\_EMAIL\_MARKETING\_CONSENT\_UPDATE
:   The webhook topic for `customers_email_marketing_consent/update` events.
    Occurs whenever a customer's email marketing consent is updated. Requires the
    `read_customers` scope.

[Anchor to CUSTOMERS\_ENABLE](/docs/api/admin-graphql/latest/enums/WebhookSubscriptionTopic#enums-CUSTOMERS_ENABLE)CUSTOMERS\_ENABLE
:   The webhook topic for `customers/enable` events. Occurs whenever a customer
    account is enabled. Requires the `read_customers` scope.

[Anchor to CUSTOMERS\_MARKETING\_CONSENT\_UPDATE](/docs/api/admin-graphql/latest/enums/WebhookSubscriptionTopic#enums-CUSTOMERS_MARKETING_CONSENT_UPDATE)CUSTOMERS\_MARKETING\_CONSENT\_UPDATE
:   The webhook topic for `customers_marketing_consent/update` events. Occurs
    whenever a customer's SMS marketing consent is updated. Requires the
    `read_customers` scope.

[Anchor to CUSTOMERS\_MERGE](/docs/api/admin-graphql/latest/enums/WebhookSubscriptionTopic#enums-CUSTOMERS_MERGE)CUSTOMERS\_MERGE
:   The webhook topic for `customers/merge` events. Triggers when two customers
    are merged Requires the `read_customer_merge` scope.

[Anchor to CUSTOMERS\_PURCHASING\_SUMMARY](/docs/api/admin-graphql/latest/enums/WebhookSubscriptionTopic#enums-CUSTOMERS_PURCHASING_SUMMARY)CUSTOMERS\_PURCHASING\_SUMMARY
:   The webhook topic for `customers/purchasing_summary` events. Occurs when a
    customer sales history change. Requires the `read_customers` scope.

[Anchor to CUSTOMERS\_UPDATE](/docs/api/admin-graphql/latest/enums/WebhookSubscriptionTopic#enums-CUSTOMERS_UPDATE)CUSTOMERS\_UPDATE
:   The webhook topic for `customers/update` events. Occurs whenever a customer is
    updated. Requires the `read_customers` scope.

[Anchor to CUSTOMERS\_WHATS\_APP\_MARKETING\_CONSENT\_UPDATE](/docs/api/admin-graphql/latest/enums/WebhookSubscriptionTopic#enums-CUSTOMERS_WHATS_APP_MARKETING_CONSENT_UPDATE)CUSTOMERS\_WHATS\_APP\_MARKETING\_CONSENT\_UPDATE
:   The webhook topic for `customers_whats_app_marketing_consent/update` events.
    Occurs whenever a customer's WhatsApp marketing consent is updated. Requires
    the `read_customers` scope.

[Anchor to DELIVERY\_PROMISE\_SETTINGS\_UPDATE](/docs/api/admin-graphql/latest/enums/WebhookSubscriptionTopic#enums-DELIVERY_PROMISE_SETTINGS_UPDATE)DELIVERY\_PROMISE\_SETTINGS\_UPDATE
:   The webhook topic for `delivery_promise_settings/update` events. Occurs when a
    promise setting is updated. Requires the `read_shipping` scope.

[Anchor to DISCOUNTS\_CREATE](/docs/api/admin-graphql/latest/enums/WebhookSubscriptionTopic#enums-DISCOUNTS_CREATE)DISCOUNTS\_CREATE
:   The webhook topic for `discounts/create` events. Occurs whenever a discount is
    created. Requires the `read_discounts` scope.

[Anchor to DISCOUNTS\_DELETE](/docs/api/admin-graphql/latest/enums/WebhookSubscriptionTopic#enums-DISCOUNTS_DELETE)DISCOUNTS\_DELETE
:   The webhook topic for `discounts/delete` events. Occurs whenever a discount is
    deleted. Requires the `read_discounts` scope.

[Anchor to DISCOUNTS\_REDEEMCODE\_ADDED](/docs/api/admin-graphql/latest/enums/WebhookSubscriptionTopic#enums-DISCOUNTS_REDEEMCODE_ADDED)DISCOUNTS\_REDEEMCODE\_ADDED
:   The webhook topic for `discounts/redeemcode_added` events. Occurs whenever a
    redeem code is added to a code discount. Requires the `read_discounts` scope.

[Anchor to DISCOUNTS\_REDEEMCODE\_REMOVED](/docs/api/admin-graphql/latest/enums/WebhookSubscriptionTopic#enums-DISCOUNTS_REDEEMCODE_REMOVED)DISCOUNTS\_REDEEMCODE\_REMOVED
:   The webhook topic for `discounts/redeemcode_removed` events. Occurs whenever a
    redeem code on a code discount is deleted. Requires the `read_discounts` scope.

[Anchor to DISCOUNTS\_UPDATE](/docs/api/admin-graphql/latest/enums/WebhookSubscriptionTopic#enums-DISCOUNTS_UPDATE)DISCOUNTS\_UPDATE
:   The webhook topic for `discounts/update` events. Occurs whenever a discount is
    updated. Requires the `read_discounts` scope.

[Anchor to DISPUTES\_CREATE](/docs/api/admin-graphql/latest/enums/WebhookSubscriptionTopic#enums-DISPUTES_CREATE)DISPUTES\_CREATE
:   The webhook topic for `disputes/create` events. Occurs whenever a dispute is
    created. Requires the `read_shopify_payments_disputes` scope.

[Anchor to DISPUTES\_UPDATE](/docs/api/admin-graphql/latest/enums/WebhookSubscriptionTopic#enums-DISPUTES_UPDATE)DISPUTES\_UPDATE
:   The webhook topic for `disputes/update` events. Occurs whenever a dispute is
    updated. Requires the `read_shopify_payments_disputes` scope.

[Anchor to DOMAINS\_CREATE](/docs/api/admin-graphql/latest/enums/WebhookSubscriptionTopic#enums-DOMAINS_CREATE)DOMAINS\_CREATE
:   The webhook topic for `domains/create` events. Occurs whenever a domain is created.

[Anchor to DOMAINS\_DESTROY](/docs/api/admin-graphql/latest/enums/WebhookSubscriptionTopic#enums-DOMAINS_DESTROY)DOMAINS\_DESTROY
:   The webhook topic for `domains/destroy` events. Occurs whenever a domain is destroyed.

[Anchor to DOMAINS\_UPDATE](/docs/api/admin-graphql/latest/enums/WebhookSubscriptionTopic#enums-DOMAINS_UPDATE)DOMAINS\_UPDATE
:   The webhook topic for `domains/update` events. Occurs whenever a domain is updated.

[Anchor to DRAFT\_ORDERS\_CREATE](/docs/api/admin-graphql/latest/enums/WebhookSubscriptionTopic#enums-DRAFT_ORDERS_CREATE)DRAFT\_ORDERS\_CREATE
:   The webhook topic for `draft_orders/create` events. Occurs whenever a draft
    order is created. Requires the `read_draft_orders` scope.

[Anchor to DRAFT\_ORDERS\_DELETE](/docs/api/admin-graphql/latest/enums/WebhookSubscriptionTopic#enums-DRAFT_ORDERS_DELETE)DRAFT\_ORDERS\_DELETE
:   The webhook topic for `draft_orders/delete` events. Occurs whenever a draft
    order is deleted. Requires the `read_draft_orders` scope.

[Anchor to DRAFT\_ORDERS\_UPDATE](/docs/api/admin-graphql/latest/enums/WebhookSubscriptionTopic#enums-DRAFT_ORDERS_UPDATE)DRAFT\_ORDERS\_UPDATE
:   The webhook topic for `draft_orders/update` events. Occurs whenever a draft
    order is updated. Requires the `read_draft_orders` scope.

[Anchor to FINANCE\_APP\_STAFF\_MEMBER\_DELETE](/docs/api/admin-graphql/latest/enums/WebhookSubscriptionTopic#enums-FINANCE_APP_STAFF_MEMBER_DELETE)FINANCE\_APP\_STAFF\_MEMBER\_DELETE
:   The webhook topic for `finance_app_staff_member/delete` events. Triggers when
    a staff with access to all or some finance app has been removed. Requires the
    `read_financial_kyc_information` scope.

[Anchor to FINANCE\_APP\_STAFF\_MEMBER\_GRANT](/docs/api/admin-graphql/latest/enums/WebhookSubscriptionTopic#enums-FINANCE_APP_STAFF_MEMBER_GRANT)FINANCE\_APP\_STAFF\_MEMBER\_GRANT
:   The webhook topic for `finance_app_staff_member/grant` events. Triggers when a
    staff is granted access to all or some finance app. Requires the
    `read_financial_kyc_information` scope.

[Anchor to FINANCE\_APP\_STAFF\_MEMBER\_REVOKE](/docs/api/admin-graphql/latest/enums/WebhookSubscriptionTopic#enums-FINANCE_APP_STAFF_MEMBER_REVOKE)FINANCE\_APP\_STAFF\_MEMBER\_REVOKE
:   The webhook topic for `finance_app_staff_member/revoke` events. Triggers when
    a staff's access to all or some finance app has been revoked. Requires the
    `read_financial_kyc_information` scope.

[Anchor to FINANCE\_APP\_STAFF\_MEMBER\_UPDATE](/docs/api/admin-graphql/latest/enums/WebhookSubscriptionTopic#enums-FINANCE_APP_STAFF_MEMBER_UPDATE)FINANCE\_APP\_STAFF\_MEMBER\_UPDATE
:   The webhook topic for `finance_app_staff_member/update` events. Triggers when
    a staff's information has been updated. Requires the
    `read_financial_kyc_information` scope.

[Anchor to FINANCE\_KYC\_INFORMATION\_UPDATE](/docs/api/admin-graphql/latest/enums/WebhookSubscriptionTopic#enums-FINANCE_KYC_INFORMATION_UPDATE)FINANCE\_KYC\_INFORMATION\_UPDATE
:   The webhook topic for `finance_kyc_information/update` events. Occurs whenever
    shop's finance KYC information was updated Requires the
    `read_financial_kyc_information` scope.

[Anchor to FULFILLMENT\_EVENTS\_CREATE](/docs/api/admin-graphql/latest/enums/WebhookSubscriptionTopic#enums-FULFILLMENT_EVENTS_CREATE)FULFILLMENT\_EVENTS\_CREATE
:   The webhook topic for `fulfillment_events/create` events. Occurs whenever a
    fulfillment event is created. Requires the `read_fulfillments` scope.

[Anchor to FULFILLMENT\_EVENTS\_DELETE](/docs/api/admin-graphql/latest/enums/WebhookSubscriptionTopic#enums-FULFILLMENT_EVENTS_DELETE)FULFILLMENT\_EVENTS\_DELETE
:   The webhook topic for `fulfillment_events/delete` events. Occurs whenever a
    fulfillment event is deleted. Requires the `read_fulfillments` scope.

[Anchor to FULFILLMENT\_HOLDS\_ADDED](/docs/api/admin-graphql/latest/enums/WebhookSubscriptionTopic#enums-FULFILLMENT_HOLDS_ADDED)FULFILLMENT\_HOLDS\_ADDED
:   The webhook topic for `fulfillment_holds/added` events. Occurs each time that a hold is added to a fulfillment order.

    For cases where multiple holds are applied to a fulfillment order, this webhook will trigger after each hold is applied.
    Requires at least one of the following scopes:
    read\_merchant\_managed\_fulfillment\_orders, read\_assigned\_fulfillment\_orders,
    read\_third\_party\_fulfillment\_orders, read\_marketplace\_fulfillment\_orders.

[Anchor to FULFILLMENT\_HOLDS\_RELEASED](/docs/api/admin-graphql/latest/enums/WebhookSubscriptionTopic#enums-FULFILLMENT_HOLDS_RELEASED)FULFILLMENT\_HOLDS\_RELEASED
:   The webhook topic for `fulfillment_holds/released` events. Occurs each time
    that a hold is released from a fulfillment order.
    For cases where multiple holds are released from a fulfillment order a the
    same time, this webhook will trigger for each released hold.
    Requires at least one of the following scopes:
    read\_merchant\_managed\_fulfillment\_orders, read\_assigned\_fulfillment\_orders,
    read\_third\_party\_fulfillment\_orders, read\_marketplace\_fulfillment\_orders.

[Anchor to FULFILLMENT\_ORDERS\_CANCELLATION\_REQUEST\_ACCEPTED](/docs/api/admin-graphql/latest/enums/WebhookSubscriptionTopic#enums-FULFILLMENT_ORDERS_CANCELLATION_REQUEST_ACCEPTED)FULFILLMENT\_ORDERS\_CANCELLATION\_REQUEST\_ACCEPTED
:   The webhook topic for `fulfillment_orders/cancellation_request_accepted`
    events. Occurs when a 3PL accepts a fulfillment cancellation request, received
    from a merchant. Requires at least one of the following scopes:
    read\_merchant\_managed\_fulfillment\_orders, read\_assigned\_fulfillment\_orders,
    read\_third\_party\_fulfillment\_orders, read\_marketplace\_fulfillment\_orders.

[Anchor to FULFILLMENT\_ORDERS\_CANCELLATION\_REQUEST\_REJECTED](/docs/api/admin-graphql/latest/enums/WebhookSubscriptionTopic#enums-FULFILLMENT_ORDERS_CANCELLATION_REQUEST_REJECTED)FULFILLMENT\_ORDERS\_CANCELLATION\_REQUEST\_REJECTED
:   The webhook topic for `fulfillment_orders/cancellation_request_rejected`
    events. Occurs when a 3PL rejects a fulfillment cancellation request, received
    from a merchant. Requires at least one of the following scopes:
    read\_merchant\_managed\_fulfillment\_orders, read\_assigned\_fulfillment\_orders,
    read\_third\_party\_fulfillment\_orders, read\_marketplace\_fulfillment\_orders.

[Anchor to FULFILLMENT\_ORDERS\_CANCELLATION\_REQUEST\_SUBMITTED](/docs/api/admin-graphql/latest/enums/WebhookSubscriptionTopic#enums-FULFILLMENT_ORDERS_CANCELLATION_REQUEST_SUBMITTED)FULFILLMENT\_ORDERS\_CANCELLATION\_REQUEST\_SUBMITTED
:   The webhook topic for `fulfillment_orders/cancellation_request_submitted`
    events. Occurs when a merchant requests a fulfillment request to be cancelled
    after that request was approved by a 3PL. Requires at least one of the
    following scopes: read\_merchant\_managed\_fulfillment\_orders,
    read\_assigned\_fulfillment\_orders, read\_third\_party\_fulfillment\_orders,
    read\_marketplace\_fulfillment\_orders.

[Anchor to FULFILLMENT\_ORDERS\_CANCELLED](/docs/api/admin-graphql/latest/enums/WebhookSubscriptionTopic#enums-FULFILLMENT_ORDERS_CANCELLED)FULFILLMENT\_ORDERS\_CANCELLED
:   The webhook topic for `fulfillment_orders/cancelled` events. Occurs when a
    fulfillment order is cancelled. Requires at least one of the following scopes:
    read\_merchant\_managed\_fulfillment\_orders, read\_assigned\_fulfillment\_orders,
    read\_third\_party\_fulfillment\_orders, read\_marketplace\_fulfillment\_orders.

[Anchor to FULFILLMENT\_ORDERS\_FULFILLMENT\_REQUEST\_ACCEPTED](/docs/api/admin-graphql/latest/enums/WebhookSubscriptionTopic#enums-FULFILLMENT_ORDERS_FULFILLMENT_REQUEST_ACCEPTED)FULFILLMENT\_ORDERS\_FULFILLMENT\_REQUEST\_ACCEPTED
:   The webhook topic for `fulfillment_orders/fulfillment_request_accepted`
    events. Occurs when a fulfillment service accepts a request to fulfill a
    fulfillment order. Requires at least one of the following scopes:
    read\_merchant\_managed\_fulfillment\_orders, read\_assigned\_fulfillment\_orders,
    read\_third\_party\_fulfillment\_orders, read\_marketplace\_fulfillment\_orders.

[Anchor to FULFILLMENT\_ORDERS\_FULFILLMENT\_REQUEST\_REJECTED](/docs/api/admin-graphql/latest/enums/WebhookSubscriptionTopic#enums-FULFILLMENT_ORDERS_FULFILLMENT_REQUEST_REJECTED)FULFILLMENT\_ORDERS\_FULFILLMENT\_REQUEST\_REJECTED
:   The webhook topic for `fulfillment_orders/fulfillment_request_rejected`
    events. Occurs when a 3PL rejects a fulfillment request that was sent by a
    merchant. Requires at least one of the following scopes:
    read\_merchant\_managed\_fulfillment\_orders, read\_assigned\_fulfillment\_orders,
    read\_third\_party\_fulfillment\_orders, read\_marketplace\_fulfillment\_orders.

[Anchor to FULFILLMENT\_ORDERS\_FULFILLMENT\_REQUEST\_SUBMITTED](/docs/api/admin-graphql/latest/enums/WebhookSubscriptionTopic#enums-FULFILLMENT_ORDERS_FULFILLMENT_REQUEST_SUBMITTED)FULFILLMENT\_ORDERS\_FULFILLMENT\_REQUEST\_SUBMITTED
:   The webhook topic for `fulfillment_orders/fulfillment_request_submitted`
    events. Occurs when a merchant submits a fulfillment request to a 3PL.
    Requires at least one of the following scopes:
    read\_merchant\_managed\_fulfillment\_orders, read\_assigned\_fulfillment\_orders,
    read\_third\_party\_fulfillment\_orders, read\_marketplace\_fulfillment\_orders.

[Anchor to FULFILLMENT\_ORDERS\_FULFILLMENT\_SERVICE\_FAILED\_TO\_COMPLETE](/docs/api/admin-graphql/latest/enums/WebhookSubscriptionTopic#enums-FULFILLMENT_ORDERS_FULFILLMENT_SERVICE_FAILED_TO_COMPLETE)FULFILLMENT\_ORDERS\_FULFILLMENT\_SERVICE\_FAILED\_TO\_COMPLETE
:   The webhook topic for
    `fulfillment_orders/fulfillment_service_failed_to_complete` events. Occurs
    when a fulfillment service intends to close an in\_progress fulfillment order.
    Requires at least one of the following scopes:
    read\_merchant\_managed\_fulfillment\_orders, read\_assigned\_fulfillment\_orders,
    read\_third\_party\_fulfillment\_orders, read\_marketplace\_fulfillment\_orders.

[Anchor to FULFILLMENT\_ORDERS\_HOLD\_RELEASED](/docs/api/admin-graphql/latest/enums/WebhookSubscriptionTopic#enums-FULFILLMENT_ORDERS_HOLD_RELEASED)FULFILLMENT\_ORDERS\_HOLD\_RELEASED
:   The webhook topic for `fulfillment_orders/hold_released` events. Occurs when a
    fulfillment order is released and is no longer on hold.

    If a fulfillment order has multiple holds then this webhook will only be
    triggered once when the last hold is released and the status of the
    fulfillment order is no longer `ON_HOLD`.
    Requires at least one of the following scopes:
    read\_merchant\_managed\_fulfillment\_orders, read\_assigned\_fulfillment\_orders,
    read\_third\_party\_fulfillment\_orders, read\_marketplace\_fulfillment\_orders.

[Anchor to FULFILLMENT\_ORDERS\_LINE\_ITEMS\_PREPARED\_FOR\_LOCAL\_DELIVERY](/docs/api/admin-graphql/latest/enums/WebhookSubscriptionTopic#enums-FULFILLMENT_ORDERS_LINE_ITEMS_PREPARED_FOR_LOCAL_DELIVERY)FULFILLMENT\_ORDERS\_LINE\_ITEMS\_PREPARED\_FOR\_LOCAL\_DELIVERY
:   The webhook topic for
    `fulfillment_orders/line_items_prepared_for_local_delivery` events. Occurs
    whenever a fulfillment order's line items are prepared for local delivery.
    Requires at least one of the following scopes:
    read\_merchant\_managed\_fulfillment\_orders, read\_assigned\_fulfillment\_orders,
    read\_third\_party\_fulfillment\_orders, read\_marketplace\_fulfillment\_orders.

[Anchor to FULFILLMENT\_ORDERS\_LINE\_ITEMS\_PREPARED\_FOR\_PICKUP](/docs/api/admin-graphql/latest/enums/WebhookSubscriptionTopic#enums-FULFILLMENT_ORDERS_LINE_ITEMS_PREPARED_FOR_PICKUP)FULFILLMENT\_ORDERS\_LINE\_ITEMS\_PREPARED\_FOR\_PICKUP
:   The webhook topic for `fulfillment_orders/line_items_prepared_for_pickup`
    events. Triggers when one or more of the line items for a fulfillment order
    are prepared for pickup Requires at least one of the following scopes:
    read\_merchant\_managed\_fulfillment\_orders, read\_assigned\_fulfillment\_orders,
    read\_third\_party\_fulfillment\_orders, read\_marketplace\_fulfillment\_orders.

[Anchor to FULFILLMENT\_ORDERS\_MANUALLY\_REPORTED\_PROGRESS\_STOPPED](/docs/api/admin-graphql/latest/enums/WebhookSubscriptionTopic#enums-FULFILLMENT_ORDERS_MANUALLY_REPORTED_PROGRESS_STOPPED)FULFILLMENT\_ORDERS\_MANUALLY\_REPORTED\_PROGRESS\_STOPPED
:   The webhook topic for `fulfillment_orders/manually_reported_progress_stopped`
    events. Occurs when a fulfillment order that has previously been manually
    marked as in progress is marked back as open. Requires at least one of the
    following scopes: read\_merchant\_managed\_fulfillment\_orders,
    read\_assigned\_fulfillment\_orders, read\_third\_party\_fulfillment\_orders.

[Anchor to FULFILLMENT\_ORDERS\_MERGED](/docs/api/admin-graphql/latest/enums/WebhookSubscriptionTopic#enums-FULFILLMENT_ORDERS_MERGED)FULFILLMENT\_ORDERS\_MERGED
:   The webhook topic for `fulfillment_orders/merged` events. Occurs when multiple
    fulfillment orders are merged into a single fulfillment order. Requires at
    least one of the following scopes: read\_merchant\_managed\_fulfillment\_orders,
    read\_assigned\_fulfillment\_orders, read\_third\_party\_fulfillment\_orders.

[Anchor to FULFILLMENT\_ORDERS\_MOVED](/docs/api/admin-graphql/latest/enums/WebhookSubscriptionTopic#enums-FULFILLMENT_ORDERS_MOVED)FULFILLMENT\_ORDERS\_MOVED
:   The webhook topic for `fulfillment_orders/moved` events. Occurs whenever the
    location which is assigned to fulfill one or more fulfillment order line items is changed.

    - `original_fulfillment_order` - The final state of the original fulfillment order.
    - `moved_fulfillment_order` - The fulfillment order which now contains the re-assigned line items.
    - `source_location` - The original location which was assigned to fulfill the
      line items (available as of the `2023-04` API version).
    - `destination_location_id` - The ID of the location which is now responsible for fulfilling the line items.

    **Note:** The [assignedLocation](https://shopify.dev/docs/api/admin-graphql/latest/objects/fulfillmentorder#field-fulfillmentorder-assignedlocation)
    of the `original_fulfillment_order` might be changed by the move operation.
    If you need to determine the originally assigned location, then you should refer to the `source_location`.

    [Learn more about moving line items](https://shopify.dev/docs/api/admin-graphql/latest/mutations/fulfillmentOrderMove).
    Requires at least one of the following scopes:
    read\_merchant\_managed\_fulfillment\_orders, read\_assigned\_fulfillment\_orders,
    read\_third\_party\_fulfillment\_orders, read\_marketplace\_fulfillment\_orders.

[Anchor to FULFILLMENT\_ORDERS\_ORDER\_ROUTING\_COMPLETE](/docs/api/admin-graphql/latest/enums/WebhookSubscriptionTopic#enums-FULFILLMENT_ORDERS_ORDER_ROUTING_COMPLETE)FULFILLMENT\_ORDERS\_ORDER\_ROUTING\_COMPLETE
:   The webhook topic for `fulfillment_orders/order_routing_complete` events.
    Occurs when an order has finished being routed and it's fulfillment orders
    assigned to a fulfillment service's location. Requires at least one of the
    following scopes: read\_merchant\_managed\_fulfillment\_orders,
    read\_assigned\_fulfillment\_orders, read\_third\_party\_fulfillment\_orders,
    read\_buyer\_membership\_orders, read\_marketplace\_fulfillment\_orders.

[Anchor to FULFILLMENT\_ORDERS\_PLACED\_ON\_HOLD](/docs/api/admin-graphql/latest/enums/WebhookSubscriptionTopic#enums-FULFILLMENT_ORDERS_PLACED_ON_HOLD)FULFILLMENT\_ORDERS\_PLACED\_ON\_HOLD
:   The webhook topic for `fulfillment_orders/placed_on_hold` events. Occurs when
    a fulfillment order transitions to the `ON_HOLD` status

    For cases where multiple holds are applied to a fulfillment order, this
    webhook will only trigger once when the first hold is applied and the
    fulfillment order status changes to `ON_HOLD`.
    Requires at least one of the following scopes:
    read\_merchant\_managed\_fulfillment\_orders, read\_assigned\_fulfillment\_orders,
    read\_third\_party\_fulfillment\_orders, read\_marketplace\_fulfillment\_orders.

[Anchor to FULFILLMENT\_ORDERS\_PROGRESS\_REPORTED](/docs/api/admin-graphql/latest/enums/WebhookSubscriptionTopic#enums-FULFILLMENT_ORDERS_PROGRESS_REPORTED)FULFILLMENT\_ORDERS\_PROGRESS\_REPORTED
:   The webhook topic for `fulfillment_orders/progress_reported` events. Occurs
    when progress is reported for a fulfillment order. Requires at least one of
    the following scopes: read\_merchant\_managed\_fulfillment\_orders,
    read\_assigned\_fulfillment\_orders, read\_third\_party\_fulfillment\_orders.

[Anchor to FULFILLMENT\_ORDERS\_RESCHEDULED](/docs/api/admin-graphql/latest/enums/WebhookSubscriptionTopic#enums-FULFILLMENT_ORDERS_RESCHEDULED)FULFILLMENT\_ORDERS\_RESCHEDULED
:   The webhook topic for `fulfillment_orders/rescheduled` events. Triggers when a fulfillment order is rescheduled.

    Fulfillment orders may be merged if they have the same `fulfillAt` datetime.
    If the fulfillment order is merged then the resulting fulfillment order will be indicated in the webhook body.
    Otherwise it will be the original fulfillment order with an updated `fulfill_at` datetime.
    Requires at least one of the following scopes:
    read\_merchant\_managed\_fulfillment\_orders, read\_assigned\_fulfillment\_orders,
    read\_third\_party\_fulfillment\_orders, read\_marketplace\_fulfillment\_orders.

[Anchor to FULFILLMENT\_ORDERS\_SCHEDULED\_FULFILLMENT\_ORDER\_READY](/docs/api/admin-graphql/latest/enums/WebhookSubscriptionTopic#enums-FULFILLMENT_ORDERS_SCHEDULED_FULFILLMENT_ORDER_READY)FULFILLMENT\_ORDERS\_SCHEDULED\_FULFILLMENT\_ORDER\_READY
:   The webhook topic for `fulfillment_orders/scheduled_fulfillment_order_ready`
    events. Occurs whenever a fulfillment order which was scheduled becomes due.
    Requires at least one of the following scopes:
    read\_merchant\_managed\_fulfillment\_orders, read\_assigned\_fulfillment\_orders,
    read\_third\_party\_fulfillment\_orders, read\_marketplace\_fulfillment\_orders.

[Anchor to FULFILLMENT\_ORDERS\_SPLIT](/docs/api/admin-graphql/latest/enums/WebhookSubscriptionTopic#enums-FULFILLMENT_ORDERS_SPLIT)FULFILLMENT\_ORDERS\_SPLIT
:   The webhook topic for `fulfillment_orders/split` events. Occurs when a
    fulfillment order is split into multiple fulfillment orders. Requires at least
    one of the following scopes: read\_merchant\_managed\_fulfillment\_orders,
    read\_assigned\_fulfillment\_orders, read\_third\_party\_fulfillment\_orders.

[Anchor to FULFILLMENTS\_CREATE](/docs/api/admin-graphql/latest/enums/WebhookSubscriptionTopic#enums-FULFILLMENTS_CREATE)FULFILLMENTS\_CREATE
:   The webhook topic for `fulfillments/create` events. Occurs whenever a
    fulfillment is created. Requires at least one of the following scopes:
    read\_fulfillments, read\_marketplace\_orders.

[Anchor to FULFILLMENTS\_UPDATE](/docs/api/admin-graphql/latest/enums/WebhookSubscriptionTopic#enums-FULFILLMENTS_UPDATE)FULFILLMENTS\_UPDATE
:   The webhook topic for `fulfillments/update` events. Occurs whenever a
    fulfillment is updated. Requires at least one of the following scopes:
    read\_fulfillments, read\_marketplace\_orders.

[Anchor to INVENTORY\_ITEMS\_CREATE](/docs/api/admin-graphql/latest/enums/WebhookSubscriptionTopic#enums-INVENTORY_ITEMS_CREATE)INVENTORY\_ITEMS\_CREATE
:   The webhook topic for `inventory_items/create` events. Occurs whenever an
    inventory item is created. Requires at least one of the following scopes:
    read\_inventory, read\_products.

[Anchor to INVENTORY\_ITEMS\_DELETE](/docs/api/admin-graphql/latest/enums/WebhookSubscriptionTopic#enums-INVENTORY_ITEMS_DELETE)INVENTORY\_ITEMS\_DELETE
:   The webhook topic for `inventory_items/delete` events. Occurs whenever an
    inventory item is deleted. Requires at least one of the following scopes:
    read\_inventory, read\_products.

[Anchor to INVENTORY\_ITEMS\_UPDATE](/docs/api/admin-graphql/latest/enums/WebhookSubscriptionTopic#enums-INVENTORY_ITEMS_UPDATE)INVENTORY\_ITEMS\_UPDATE
:   The webhook topic for `inventory_items/update` events. Occurs whenever an
    inventory item is updated. Requires at least one of the following scopes:
    read\_inventory, read\_products.

[Anchor to INVENTORY\_LEVELS\_CONNECT](/docs/api/admin-graphql/latest/enums/WebhookSubscriptionTopic#enums-INVENTORY_LEVELS_CONNECT)INVENTORY\_LEVELS\_CONNECT
:   The webhook topic for `inventory_levels/connect` events. Occurs whenever an
    inventory level is connected. Requires the `read_inventory` scope.

[Anchor to INVENTORY\_LEVELS\_DISCONNECT](/docs/api/admin-graphql/latest/enums/WebhookSubscriptionTopic#enums-INVENTORY_LEVELS_DISCONNECT)INVENTORY\_LEVELS\_DISCONNECT
:   The webhook topic for `inventory_levels/disconnect` events. Occurs whenever an
    inventory level is disconnected. Requires the `read_inventory` scope.

[Anchor to INVENTORY\_LEVELS\_UPDATE](/docs/api/admin-graphql/latest/enums/WebhookSubscriptionTopic#enums-INVENTORY_LEVELS_UPDATE)INVENTORY\_LEVELS\_UPDATE
:   The webhook topic for `inventory_levels/update` events. Occurs whenever an
    inventory level is updated. Requires the `read_inventory` scope.

[Anchor to INVENTORY\_SHIPMENTS\_ADD\_ITEMS](/docs/api/admin-graphql/latest/enums/WebhookSubscriptionTopic#enums-INVENTORY_SHIPMENTS_ADD_ITEMS)INVENTORY\_SHIPMENTS\_ADD\_ITEMS
:   The webhook topic for `inventory_shipments/add_items` events. Occurs whenever
    items are added to a shipment. Requires the `read_inventory_shipments` scope.

[Anchor to INVENTORY\_SHIPMENTS\_CREATE](/docs/api/admin-graphql/latest/enums/WebhookSubscriptionTopic#enums-INVENTORY_SHIPMENTS_CREATE)INVENTORY\_SHIPMENTS\_CREATE
:   The webhook topic for `inventory_shipments/create` events. Triggers when a
    shipment is created. Requires the `read_inventory_shipments` scope.

[Anchor to INVENTORY\_SHIPMENTS\_DELETE](/docs/api/admin-graphql/latest/enums/WebhookSubscriptionTopic#enums-INVENTORY_SHIPMENTS_DELETE)INVENTORY\_SHIPMENTS\_DELETE
:   The webhook topic for `inventory_shipments/delete` events. Triggers when a
    shipment is deleted. Requires the `read_inventory_shipments` scope.

[Anchor to INVENTORY\_SHIPMENTS\_MARK\_IN\_TRANSIT](/docs/api/admin-graphql/latest/enums/WebhookSubscriptionTopic#enums-INVENTORY_SHIPMENTS_MARK_IN_TRANSIT)INVENTORY\_SHIPMENTS\_MARK\_IN\_TRANSIT
:   The webhook topic for `inventory_shipments/mark_in_transit` events. Triggers
    when a shipment is marked as in transit. Requires the
    `read_inventory_shipments` scope.

[Anchor to INVENTORY\_SHIPMENTS\_RECEIVE\_ITEMS](/docs/api/admin-graphql/latest/enums/WebhookSubscriptionTopic#enums-INVENTORY_SHIPMENTS_RECEIVE_ITEMS)INVENTORY\_SHIPMENTS\_RECEIVE\_ITEMS
:   The webhook topic for `inventory_shipments/receive_items` events. Triggers
    when items on a shipment are received. Requires the
    `read_inventory_shipments_received_items` scope.

[Anchor to INVENTORY\_SHIPMENTS\_REMOVE\_ITEMS](/docs/api/admin-graphql/latest/enums/WebhookSubscriptionTopic#enums-INVENTORY_SHIPMENTS_REMOVE_ITEMS)INVENTORY\_SHIPMENTS\_REMOVE\_ITEMS
:   The webhook topic for `inventory_shipments/remove_items` events. Occurs
    whenever items are removed from a shipment. Requires the
    `read_inventory_shipments` scope.

[Anchor to INVENTORY\_SHIPMENTS\_UPDATE\_ITEM\_QUANTITIES](/docs/api/admin-graphql/latest/enums/WebhookSubscriptionTopic#enums-INVENTORY_SHIPMENTS_UPDATE_ITEM_QUANTITIES)INVENTORY\_SHIPMENTS\_UPDATE\_ITEM\_QUANTITIES
:   The webhook topic for `inventory_shipments/update_item_quantities` events.
    Occurs whenever quantities change on a shipment. Requires the
    `read_inventory_shipments` scope.

[Anchor to INVENTORY\_SHIPMENTS\_UPDATE\_TRACKING](/docs/api/admin-graphql/latest/enums/WebhookSubscriptionTopic#enums-INVENTORY_SHIPMENTS_UPDATE_TRACKING)INVENTORY\_SHIPMENTS\_UPDATE\_TRACKING
:   The webhook topic for `inventory_shipments/update_tracking` events. Triggers
    when tracking info on a shipment is updated. Requires the
    `read_inventory_shipments` scope.

[Anchor to INVENTORY\_TRANSFERS\_ADD\_ITEMS](/docs/api/admin-graphql/latest/enums/WebhookSubscriptionTopic#enums-INVENTORY_TRANSFERS_ADD_ITEMS)INVENTORY\_TRANSFERS\_ADD\_ITEMS
:   The webhook topic for `inventory_transfers/add_items` events. Occurs any time
    items are added to a transfer. Requires the `read_inventory_transfers` scope.

[Anchor to INVENTORY\_TRANSFERS\_CANCEL](/docs/api/admin-graphql/latest/enums/WebhookSubscriptionTopic#enums-INVENTORY_TRANSFERS_CANCEL)INVENTORY\_TRANSFERS\_CANCEL
:   The webhook topic for `inventory_transfers/cancel` events. Triggers when a
    transfer is canceled. Requires the `read_inventory_transfers` scope.

[Anchor to INVENTORY\_TRANSFERS\_COMPLETE](/docs/api/admin-graphql/latest/enums/WebhookSubscriptionTopic#enums-INVENTORY_TRANSFERS_COMPLETE)INVENTORY\_TRANSFERS\_COMPLETE
:   The webhook topic for `inventory_transfers/complete` events. Triggers when a
    transfer is completed. Requires the `read_inventory_transfers` scope.

[Anchor to INVENTORY\_TRANSFERS\_READY\_TO\_SHIP](/docs/api/admin-graphql/latest/enums/WebhookSubscriptionTopic#enums-INVENTORY_TRANSFERS_READY_TO_SHIP)INVENTORY\_TRANSFERS\_READY\_TO\_SHIP
:   The webhook topic for `inventory_transfers/ready_to_ship` events. Triggers
    when a transfer is marked as ready to ship. Requires the
    `read_inventory_transfers` scope.

[Anchor to INVENTORY\_TRANSFERS\_REMOVE\_ITEMS](/docs/api/admin-graphql/latest/enums/WebhookSubscriptionTopic#enums-INVENTORY_TRANSFERS_REMOVE_ITEMS)INVENTORY\_TRANSFERS\_REMOVE\_ITEMS
:   The webhook topic for `inventory_transfers/remove_items` events. Occurs any
    time items are removed from a transfer. Requires the
    `read_inventory_transfers` scope.

[Anchor to INVENTORY\_TRANSFERS\_UPDATE\_ITEM\_QUANTITIES](/docs/api/admin-graphql/latest/enums/WebhookSubscriptionTopic#enums-INVENTORY_TRANSFERS_UPDATE_ITEM_QUANTITIES)INVENTORY\_TRANSFERS\_UPDATE\_ITEM\_QUANTITIES
:   The webhook topic for `inventory_transfers/update_item_quantities` events.
    Occurs whenever the quantity of transfer line items changes. Requires the
    `read_inventory_transfers` scope.

[Anchor to INVENTORY\_TRANSFERS\_UPDATED](/docs/api/admin-graphql/latest/enums/WebhookSubscriptionTopic#enums-INVENTORY_TRANSFERS_UPDATED)INVENTORY\_TRANSFERS\_UPDATED
:   The webhook topic for `inventory_transfers/updated` events. Triggers when a
    shipment belonging to the transfer is created, edited, or removed. Re-fetch
    the transfer to get the latest state. Requires the `read_inventory_transfers` scope.

[Anchor to LOCALES\_CREATE](/docs/api/admin-graphql/latest/enums/WebhookSubscriptionTopic#enums-LOCALES_CREATE)LOCALES\_CREATE
:   The webhook topic for `locales/create` events. Occurs whenever a shop locale is created Requires the `read_locales` scope.

[Anchor to LOCALES\_DESTROY](/docs/api/admin-graphql/latest/enums/WebhookSubscriptionTopic#enums-LOCALES_DESTROY)LOCALES\_DESTROY
:   The webhook topic for `locales/destroy` events. Occurs whenever a shop locale
    is destroyed Requires the `read_locales` scope.

[Anchor to LOCALES\_UPDATE](/docs/api/admin-graphql/latest/enums/WebhookSubscriptionTopic#enums-LOCALES_UPDATE)LOCALES\_UPDATE
:   The webhook topic for `locales/update` events. Occurs whenever a shop locale
    is updated, such as published or unpublished Requires the `read_locales` scope.

[Anchor to LOCATIONS\_ACTIVATE](/docs/api/admin-graphql/latest/enums/WebhookSubscriptionTopic#enums-LOCATIONS_ACTIVATE)LOCATIONS\_ACTIVATE
:   The webhook topic for `locations/activate` events. Occurs whenever a
    deactivated location is re-activated. Requires the `read_locations` scope.

[Anchor to LOCATIONS\_CREATE](/docs/api/admin-graphql/latest/enums/WebhookSubscriptionTopic#enums-LOCATIONS_CREATE)LOCATIONS\_CREATE
:   The webhook topic for `locations/create` events. Occurs whenever a location is
    created. Requires the `read_locations` scope.

[Anchor to LOCATIONS\_DEACTIVATE](/docs/api/admin-graphql/latest/enums/WebhookSubscriptionTopic#enums-LOCATIONS_DEACTIVATE)LOCATIONS\_DEACTIVATE
:   The webhook topic for `locations/deactivate` events. Occurs whenever a
    location is deactivated. Requires the `read_locations` scope.

[Anchor to LOCATIONS\_DELETE](/docs/api/admin-graphql/latest/enums/WebhookSubscriptionTopic#enums-LOCATIONS_DELETE)LOCATIONS\_DELETE
:   The webhook topic for `locations/delete` events. Occurs whenever a location is
    deleted. Requires the `read_locations` scope.

[Anchor to LOCATIONS\_UPDATE](/docs/api/admin-graphql/latest/enums/WebhookSubscriptionTopic#enums-LOCATIONS_UPDATE)LOCATIONS\_UPDATE
:   The webhook topic for `locations/update` events. Occurs whenever a location is
    updated. Requires the `read_locations` scope.

[Anchor to MARKETS\_BACKUP\_REGION\_UPDATE](/docs/api/admin-graphql/latest/enums/WebhookSubscriptionTopic#enums-MARKETS_BACKUP_REGION_UPDATE)MARKETS\_BACKUP\_REGION\_UPDATE
:   The webhook topic for `markets_backup_region/update` events. Occurs when a
    backup region is updated. Requires the `read_markets` scope.

[Anchor to MARKETS\_CREATE](/docs/api/admin-graphql/latest/enums/WebhookSubscriptionTopic#enums-MARKETS_CREATE)MARKETS\_CREATE
:   The webhook topic for `markets/create` events. Occurs when a new market is created. Requires the `read_markets` scope.

[Anchor to MARKETS\_DELETE](/docs/api/admin-graphql/latest/enums/WebhookSubscriptionTopic#enums-MARKETS_DELETE)MARKETS\_DELETE
:   The webhook topic for `markets/delete` events. Occurs when a market is deleted. Requires the `read_markets` scope.

[Anchor to MARKETS\_UPDATE](/docs/api/admin-graphql/latest/enums/WebhookSubscriptionTopic#enums-MARKETS_UPDATE)MARKETS\_UPDATE
:   The webhook topic for `markets/update` events. Occurs when a market is updated. Requires the `read_markets` scope.

[Anchor to METAFIELD\_DEFINITIONS\_CREATE](/docs/api/admin-graphql/latest/enums/WebhookSubscriptionTopic#enums-METAFIELD_DEFINITIONS_CREATE)METAFIELD\_DEFINITIONS\_CREATE
:   The webhook topic for `metafield_definitions/create` events. Occurs when a
    metafield definition is created. Requires the `read_content` scope.

[Anchor to METAFIELD\_DEFINITIONS\_DELETE](/docs/api/admin-graphql/latest/enums/WebhookSubscriptionTopic#enums-METAFIELD_DEFINITIONS_DELETE)METAFIELD\_DEFINITIONS\_DELETE
:   The webhook topic for `metafield_definitions/delete` events. Occurs when a
    metafield definition is deleted. Requires the `read_content` scope.

[Anchor to METAFIELD\_DEFINITIONS\_UPDATE](/docs/api/admin-graphql/latest/enums/WebhookSubscriptionTopic#enums-METAFIELD_DEFINITIONS_UPDATE)METAFIELD\_DEFINITIONS\_UPDATE
:   The webhook topic for `metafield_definitions/update` events. Occurs when a
    metafield definition is updated. Requires the `read_content` scope.

[Anchor to METAOBJECTS\_CREATE](/docs/api/admin-graphql/latest/enums/WebhookSubscriptionTopic#enums-METAOBJECTS_CREATE)METAOBJECTS\_CREATE
:   The webhook topic for `metaobjects/create` events. Occurs when a metaobject is
    created. Requires the `read_metaobjects` scope.

[Anchor to METAOBJECTS\_DELETE](/docs/api/admin-graphql/latest/enums/WebhookSubscriptionTopic#enums-METAOBJECTS_DELETE)METAOBJECTS\_DELETE
:   The webhook topic for `metaobjects/delete` events. Occurs when a metaobject is
    deleted. Requires the `read_metaobjects` scope.

[Anchor to METAOBJECTS\_UPDATE](/docs/api/admin-graphql/latest/enums/WebhookSubscriptionTopic#enums-METAOBJECTS_UPDATE)METAOBJECTS\_UPDATE
:   The webhook topic for `metaobjects/update` events. Occurs when a metaobject is
    updated. Requires the `read_metaobjects` scope.

[Anchor to ORDER\_TRANSACTIONS\_CREATE](/docs/api/admin-graphql/latest/enums/WebhookSubscriptionTopic#enums-ORDER_TRANSACTIONS_CREATE)ORDER\_TRANSACTIONS\_CREATE
:   The webhook topic for `order_transactions/create` events. Occurs when a order
    transaction is created or when it's status is updated. Only occurs for
    transactions with a status of success, failure or error. Requires at least one
    of the following scopes: read\_orders, read\_marketplace\_orders,
    read\_buyer\_membership\_orders.

[Anchor to ORDERS\_CANCELLED](/docs/api/admin-graphql/latest/enums/WebhookSubscriptionTopic#enums-ORDERS_CANCELLED)ORDERS\_CANCELLED
:   The webhook topic for `orders/cancelled` events. Occurs whenever an order is
    cancelled. Requires at least one of the following scopes: read\_orders,
    read\_marketplace\_orders, read\_buyer\_membership\_orders.

[Anchor to ORDERS\_CREATE](/docs/api/admin-graphql/latest/enums/WebhookSubscriptionTopic#enums-ORDERS_CREATE)ORDERS\_CREATE
:   The webhook topic for `orders/create` events. Occurs whenever an order is
    created. Requires at least one of the following scopes: read\_orders,
    read\_marketplace\_orders.

[Anchor to ORDERS\_DELETE](/docs/api/admin-graphql/latest/enums/WebhookSubscriptionTopic#enums-ORDERS_DELETE)ORDERS\_DELETE
:   The webhook topic for `orders/delete` events. Occurs whenever an order is deleted. Requires the `read_orders` scope.

[Anchor to ORDERS\_EDITED](/docs/api/admin-graphql/latest/enums/WebhookSubscriptionTopic#enums-ORDERS_EDITED)ORDERS\_EDITED
:   The webhook topic for `orders/edited` events. Occurs whenever an order is
    edited. Requires at least one of the following scopes: read\_orders,
    read\_marketplace\_orders, read\_buyer\_membership\_orders.

[Anchor to ORDERS\_FULFILLED](/docs/api/admin-graphql/latest/enums/WebhookSubscriptionTopic#enums-ORDERS_FULFILLED)ORDERS\_FULFILLED
:   The webhook topic for `orders/fulfilled` events. Occurs whenever an order is
    fulfilled. Requires at least one of the following scopes: read\_orders,
    read\_marketplace\_orders.

[Anchor to ORDERS\_LINK\_REQUESTED](/docs/api/admin-graphql/latest/enums/WebhookSubscriptionTopic#enums-ORDERS_LINK_REQUESTED)ORDERS\_LINK\_REQUESTED
:   The webhook topic for `orders/link_requested` events. Occurs whenever a
    customer requests a new order link from the expired order status page.
    Requires at least one of the following scopes: read\_orders,
    read\_marketplace\_orders, read\_buyer\_membership\_orders.

[Anchor to ORDERS\_PAID](/docs/api/admin-graphql/latest/enums/WebhookSubscriptionTopic#enums-ORDERS_PAID)ORDERS\_PAID
:   The webhook topic for `orders/paid` events. Occurs whenever an order is paid.
    Requires at least one of the following scopes: read\_orders,
    read\_marketplace\_orders.

[Anchor to ORDERS\_PARTIALLY\_FULFILLED](/docs/api/admin-graphql/latest/enums/WebhookSubscriptionTopic#enums-ORDERS_PARTIALLY_FULFILLED)ORDERS\_PARTIALLY\_FULFILLED
:   The webhook topic for `orders/partially_fulfilled` events. Occurs whenever an
    order is partially fulfilled. Requires at least one of the following scopes:
    read\_orders, read\_marketplace\_orders.

[Anchor to ORDERS\_RISK\_ASSESSMENT\_CHANGED](/docs/api/admin-graphql/latest/enums/WebhookSubscriptionTopic#enums-ORDERS_RISK_ASSESSMENT_CHANGED)ORDERS\_RISK\_ASSESSMENT\_CHANGED
:   The webhook topic for `orders/risk_assessment_changed` events. Triggers when a
    new risk assessment is available on the order.
    This can be the first or a subsequent risk assessment.
    New risk assessments can be provided until the order is marked as fulfilled.
    Includes the risk level, risk facts, the provider and the order ID.
    When the provider is Shopify, that field is null.
    Does not include the risk recommendation for the order.
    The Shop ID is available in the headers.
    Requires the `read_orders` scope.

[Anchor to ORDERS\_SHOPIFY\_PROTECT\_ELIGIBILITY\_CHANGED](/docs/api/admin-graphql/latest/enums/WebhookSubscriptionTopic#enums-ORDERS_SHOPIFY_PROTECT_ELIGIBILITY_CHANGED)ORDERS\_SHOPIFY\_PROTECT\_ELIGIBILITY\_CHANGED
:   The webhook topic for `orders/shopify_protect_eligibility_changed` events.
    Occurs whenever Shopify Protect's eligibility for an order is changed.
    Requires the `read_orders` scope.

[Anchor to ORDERS\_UPDATED](/docs/api/admin-graphql/latest/enums/WebhookSubscriptionTopic#enums-ORDERS_UPDATED)ORDERS\_UPDATED
:   The webhook topic for `orders/updated` events. Occurs whenever an order is
    updated. Requires at least one of the following scopes: read\_orders,
    read\_marketplace\_orders, read\_buyer\_membership\_orders.

[Anchor to PAYMENT\_SCHEDULES\_DUE](/docs/api/admin-graphql/latest/enums/WebhookSubscriptionTopic#enums-PAYMENT_SCHEDULES_DUE)PAYMENT\_SCHEDULES\_DUE
:   The webhook topic for `payment_schedules/due` events. Occurs whenever payment
    schedules are due. Requires the `read_payment_terms` scope.

[Anchor to PAYMENT\_TERMS\_CREATE](/docs/api/admin-graphql/latest/enums/WebhookSubscriptionTopic#enums-PAYMENT_TERMS_CREATE)PAYMENT\_TERMS\_CREATE
:   The webhook topic for `payment_terms/create` events. Occurs whenever payment
    terms are created. Requires the `read_payment_terms` scope.

[Anchor to PAYMENT\_TERMS\_DELETE](/docs/api/admin-graphql/latest/enums/WebhookSubscriptionTopic#enums-PAYMENT_TERMS_DELETE)PAYMENT\_TERMS\_DELETE
:   The webhook topic for `payment_terms/delete` events. Occurs whenever payment
    terms are deleted. Requires the `read_payment_terms` scope.

[Anchor to PAYMENT\_TERMS\_UPDATE](/docs/api/admin-graphql/latest/enums/WebhookSubscriptionTopic#enums-PAYMENT_TERMS_UPDATE)PAYMENT\_TERMS\_UPDATE
:   The webhook topic for `payment_terms/update` events. Occurs whenever payment
    terms are updated. Requires the `read_payment_terms` scope.

[Anchor to PRODUCT\_FEEDS\_CREATE](/docs/api/admin-graphql/latest/enums/WebhookSubscriptionTopic#enums-PRODUCT_FEEDS_CREATE)PRODUCT\_FEEDS\_CREATE
:   The webhook topic for `product_feeds/create` events. Triggers when product
    feed is created Requires the `read_product_listings` scope.

[Anchor to PRODUCT\_FEEDS\_FULL\_SYNC](/docs/api/admin-graphql/latest/enums/WebhookSubscriptionTopic#enums-PRODUCT_FEEDS_FULL_SYNC)PRODUCT\_FEEDS\_FULL\_SYNC
:   The webhook topic for `product_feeds/full_sync` events. Triggers when a full
    sync for a product feed is performed Requires the `read_product_listings` scope.

[Anchor to PRODUCT\_FEEDS\_FULL\_SYNC\_FINISH](/docs/api/admin-graphql/latest/enums/WebhookSubscriptionTopic#enums-PRODUCT_FEEDS_FULL_SYNC_FINISH)PRODUCT\_FEEDS\_FULL\_SYNC\_FINISH
:   The webhook topic for `product_feeds/full_sync_finish` events. Triggers when a
    full sync finishes Requires the `read_product_listings` scope.

[Anchor to PRODUCT\_FEEDS\_INCREMENTAL\_SYNC](/docs/api/admin-graphql/latest/enums/WebhookSubscriptionTopic#enums-PRODUCT_FEEDS_INCREMENTAL_SYNC)PRODUCT\_FEEDS\_INCREMENTAL\_SYNC
:   The webhook topic for `product_feeds/incremental_sync` events. Occurs whenever
    a product publication is created, updated or removed for a product feed
    Requires the `read_product_listings` scope.

[Anchor to PRODUCT\_FEEDS\_UPDATE](/docs/api/admin-graphql/latest/enums/WebhookSubscriptionTopic#enums-PRODUCT_FEEDS_UPDATE)PRODUCT\_FEEDS\_UPDATE
:   The webhook topic for `product_feeds/update` events. Triggers when product
    feed is updated Requires the `read_product_listings` scope.

[Anchor to PRODUCT\_LISTINGS\_ADD](/docs/api/admin-graphql/latest/enums/WebhookSubscriptionTopic#enums-PRODUCT_LISTINGS_ADD)PRODUCT\_LISTINGS\_ADD
:   The webhook topic for `product_listings/add` events. Occurs whenever an active
    product is listed on a channel. Requires the `read_product_listings` scope.

[Anchor to PRODUCT\_LISTINGS\_REMOVE](/docs/api/admin-graphql/latest/enums/WebhookSubscriptionTopic#enums-PRODUCT_LISTINGS_REMOVE)PRODUCT\_LISTINGS\_REMOVE
:   The webhook topic for `product_listings/remove` events. Occurs whenever a
    product listing is removed from the channel. Requires the
    `read_product_listings` scope.

[Anchor to PRODUCT\_LISTINGS\_UPDATE](/docs/api/admin-graphql/latest/enums/WebhookSubscriptionTopic#enums-PRODUCT_LISTINGS_UPDATE)PRODUCT\_LISTINGS\_UPDATE
:   The webhook topic for `product_listings/update` events. Occurs whenever a
    product publication is updated. Requires the `read_product_listings` scope.

[Anchor to PRODUCT\_PUBLICATIONS\_CREATE](/docs/api/admin-graphql/latest/enums/WebhookSubscriptionTopic#enums-PRODUCT_PUBLICATIONS_CREATE)PRODUCT\_PUBLICATIONS\_CREATE
:   The webhook topic for `product_publications/create` events. Occurs whenever a
    product publication for an active product is created, or whenever an existing
    product publication is published on the app that is subscribed to this webhook
    topic. Note that a webhook is only emitted when there are publishing changes
    to the app that is subscribed to the topic (ie. no webhook will be emitted if
    there is a publishing change to the online store and the webhook subscriber of
    the topic is a third-party app). Requires the `read_publications` scope.

[Anchor to PRODUCT\_PUBLICATIONS\_DELETE](/docs/api/admin-graphql/latest/enums/WebhookSubscriptionTopic#enums-PRODUCT_PUBLICATIONS_DELETE)PRODUCT\_PUBLICATIONS\_DELETE
:   The webhook topic for `product_publications/delete` events. Occurs whenever a
    product publication for an active product is removed, or whenever an existing
    product publication is unpublished from the app that is subscribed to this
    webhook topic. Note that a webhook is only emitted when there are publishing
    changes to the app that is subscribed to the topic (ie. no webhook will be
    emitted if there is a publishing change to the online store and the webhook
    subscriber of the topic is a third-party app). Requires the
    `read_publications` scope.

[Anchor to PRODUCT\_PUBLICATIONS\_UPDATE](/docs/api/admin-graphql/latest/enums/WebhookSubscriptionTopic#enums-PRODUCT_PUBLICATIONS_UPDATE)PRODUCT\_PUBLICATIONS\_UPDATE
:   The webhook topic for `product_publications/update` events. Occurs whenever a
    product publication is updated from the app that is subscribed to this webhook
    topic. Note that a webhook is only emitted when there are publishing changes
    to the app that is subscribed to the topic (ie. no webhook will be emitted if
    there is a publishing change to the online store and the webhook subscriber of
    the topic is a third-party app). Requires the `read_publications` scope.

[Anchor to PRODUCTS\_CREATE](/docs/api/admin-graphql/latest/enums/WebhookSubscriptionTopic#enums-PRODUCTS_CREATE)PRODUCTS\_CREATE
:   The webhook topic for `products/create` events. Occurs whenever a product is created. Requires the `read_products` scope.

[Anchor to PRODUCTS\_DELETE](/docs/api/admin-graphql/latest/enums/WebhookSubscriptionTopic#enums-PRODUCTS_DELETE)PRODUCTS\_DELETE
:   The webhook topic for `products/delete` events. Occurs whenever a product is deleted. Requires the `read_products` scope.

[Anchor to PRODUCTS\_UPDATE](/docs/api/admin-graphql/latest/enums/WebhookSubscriptionTopic#enums-PRODUCTS_UPDATE)PRODUCTS\_UPDATE
:   The webhook topic for `products/update` events. Occurs whenever a product is
    updated, ordered, or variants are added, removed or updated. Requires the
    `read_products` scope.

[Anchor to PROFILES\_CREATE](/docs/api/admin-graphql/latest/enums/WebhookSubscriptionTopic#enums-PROFILES_CREATE)PROFILES\_CREATE
:   The webhook topic for `profiles/create` events. Occurs whenever a delivery
    profile is created Requires at least one of the following scopes:
    read\_shipping, read\_assigned\_shipping.

[Anchor to PROFILES\_DELETE](/docs/api/admin-graphql/latest/enums/WebhookSubscriptionTopic#enums-PROFILES_DELETE)PROFILES\_DELETE
:   The webhook topic for `profiles/delete` events. Occurs whenever a delivery
    profile is deleted Requires at least one of the following scopes:
    read\_shipping, read\_assigned\_shipping.

[Anchor to PROFILES\_UPDATE](/docs/api/admin-graphql/latest/enums/WebhookSubscriptionTopic#enums-PROFILES_UPDATE)PROFILES\_UPDATE
:   The webhook topic for `profiles/update` events. Occurs whenever a delivery
    profile is updated Requires at least one of the following scopes:
    read\_shipping, read\_assigned\_shipping.

[Anchor to REFUNDS\_CREATE](/docs/api/admin-graphql/latest/enums/WebhookSubscriptionTopic#enums-REFUNDS_CREATE)REFUNDS\_CREATE
:   The webhook topic for `refunds/create` events. Occurs whenever a new refund is
    created without errors on an order, independent from the movement of money.
    Requires at least one of the following scopes: read\_orders,
    read\_marketplace\_orders, read\_buyer\_membership\_orders.

[Anchor to RETURNS\_APPROVE](/docs/api/admin-graphql/latest/enums/WebhookSubscriptionTopic#enums-RETURNS_APPROVE)RETURNS\_APPROVE
:   The webhook topic for `returns/approve` events. Occurs whenever a return is
    approved. This means `Return.status` is `OPEN`. Requires at least one of the
    following scopes: read\_returns, read\_marketplace\_returns,
    read\_buyer\_membership\_orders.

[Anchor to RETURNS\_CANCEL](/docs/api/admin-graphql/latest/enums/WebhookSubscriptionTopic#enums-RETURNS_CANCEL)RETURNS\_CANCEL
:   The webhook topic for `returns/cancel` events. Occurs whenever a return is
    canceled. Requires at least one of the following scopes: read\_orders,
    read\_marketplace\_orders, read\_returns, read\_marketplace\_returns,
    read\_buyer\_membership\_orders.

[Anchor to RETURNS\_CLOSE](/docs/api/admin-graphql/latest/enums/WebhookSubscriptionTopic#enums-RETURNS_CLOSE)RETURNS\_CLOSE
:   The webhook topic for `returns/close` events. Occurs whenever a return is
    closed. Requires at least one of the following scopes: read\_orders,
    read\_marketplace\_orders, read\_returns, read\_marketplace\_returns,
    read\_buyer\_membership\_orders.

[Anchor to RETURNS\_DECLINE](/docs/api/admin-graphql/latest/enums/WebhookSubscriptionTopic#enums-RETURNS_DECLINE)RETURNS\_DECLINE
:   The webhook topic for `returns/decline` events. Occurs whenever a return is
    declined. This means `Return.status` is `DECLINED`. Requires at least one of
    the following scopes: read\_returns, read\_marketplace\_returns,
    read\_buyer\_membership\_orders.

[Anchor to RETURNS\_PROCESS](/docs/api/admin-graphql/latest/enums/WebhookSubscriptionTopic#enums-RETURNS_PROCESS)RETURNS\_PROCESS
:   The webhook topic for `returns/process` events. Occurs whenever a return is
    processed. Requires at least one of the following scopes: read\_returns,
    read\_marketplace\_returns, read\_buyer\_membership\_orders.

[Anchor to RETURNS\_REOPEN](/docs/api/admin-graphql/latest/enums/WebhookSubscriptionTopic#enums-RETURNS_REOPEN)RETURNS\_REOPEN
:   The webhook topic for `returns/reopen` events. Occurs whenever a closed return
    is reopened. Requires at least one of the following scopes: read\_orders,
    read\_marketplace\_orders, read\_returns, read\_marketplace\_returns,
    read\_buyer\_membership\_orders.

[Anchor to RETURNS\_REQUEST](/docs/api/admin-graphql/latest/enums/WebhookSubscriptionTopic#enums-RETURNS_REQUEST)RETURNS\_REQUEST
:   The webhook topic for `returns/request` events. Occurs whenever a return is
    requested. This means `Return.status` is `REQUESTED`. Requires at least one of
    the following scopes: read\_returns, read\_marketplace\_returns,
    read\_buyer\_membership\_orders.

[Anchor to RETURNS\_UPDATE](/docs/api/admin-graphql/latest/enums/WebhookSubscriptionTopic#enums-RETURNS_UPDATE)RETURNS\_UPDATE
:   The webhook topic for `returns/update` events. Occurs whenever a return is
    updated. Requires at least one of the following scopes: read\_returns,
    read\_marketplace\_returns, read\_buyer\_membership\_orders.

[Anchor to REVERSE\_DELIVERIES\_ATTACH\_DELIVERABLE](/docs/api/admin-graphql/latest/enums/WebhookSubscriptionTopic#enums-REVERSE_DELIVERIES_ATTACH_DELIVERABLE)REVERSE\_DELIVERIES\_ATTACH\_DELIVERABLE
:   The webhook topic for `reverse_deliveries/attach_deliverable` events. Occurs
    whenever a deliverable is attached to a reverse delivery.
    This occurs when a reverse delivery is created or updated with delivery metadata.
    Metadata includes the delivery method, label, and tracking information associated with a reverse delivery.
    Requires at least one of the following scopes: read\_returns, read\_marketplace\_returns.

[Anchor to REVERSE\_FULFILLMENT\_ORDERS\_DISPOSE](/docs/api/admin-graphql/latest/enums/WebhookSubscriptionTopic#enums-REVERSE_FULFILLMENT_ORDERS_DISPOSE)REVERSE\_FULFILLMENT\_ORDERS\_DISPOSE
:   The webhook topic for `reverse_fulfillment_orders/dispose` events. Occurs
    whenever a disposition is made on a reverse fulfillment order.
    This includes dispositions made on reverse deliveries that are associated with the reverse fulfillment order.
    Requires at least one of the following scopes: read\_returns, read\_marketplace\_returns.

[Anchor to SCHEDULED\_PRODUCT\_LISTINGS\_ADD](/docs/api/admin-graphql/latest/enums/WebhookSubscriptionTopic#enums-SCHEDULED_PRODUCT_LISTINGS_ADD)SCHEDULED\_PRODUCT\_LISTINGS\_ADD
:   The webhook topic for `scheduled_product_listings/add` events. Occurs whenever
    a product is scheduled to be published. Requires the `read_product_listings` scope.

[Anchor to SCHEDULED\_PRODUCT\_LISTINGS\_REMOVE](/docs/api/admin-graphql/latest/enums/WebhookSubscriptionTopic#enums-SCHEDULED_PRODUCT_LISTINGS_REMOVE)SCHEDULED\_PRODUCT\_LISTINGS\_REMOVE
:   The webhook topic for `scheduled_product_listings/remove` events. Occurs
    whenever a product is no longer scheduled to be published. Requires the
    `read_product_listings` scope.

[Anchor to SCHEDULED\_PRODUCT\_LISTINGS\_UPDATE](/docs/api/admin-graphql/latest/enums/WebhookSubscriptionTopic#enums-SCHEDULED_PRODUCT_LISTINGS_UPDATE)SCHEDULED\_PRODUCT\_LISTINGS\_UPDATE
:   The webhook topic for `scheduled_product_listings/update` events. Occurs
    whenever a product's scheduled availability date changes. Requires the
    `read_product_listings` scope.

[Anchor to SEGMENTS\_CREATE](/docs/api/admin-graphql/latest/enums/WebhookSubscriptionTopic#enums-SEGMENTS_CREATE)SEGMENTS\_CREATE
:   The webhook topic for `segments/create` events. Occurs whenever a segment is created. Requires the `read_customers` scope.

[Anchor to SEGMENTS\_DELETE](/docs/api/admin-graphql/latest/enums/WebhookSubscriptionTopic#enums-SEGMENTS_DELETE)SEGMENTS\_DELETE
:   The webhook topic for `segments/delete` events. Occurs whenever a segment is deleted. Requires the `read_customers` scope.

[Anchor to SEGMENTS\_UPDATE](/docs/api/admin-graphql/latest/enums/WebhookSubscriptionTopic#enums-SEGMENTS_UPDATE)SEGMENTS\_UPDATE
:   The webhook topic for `segments/update` events. Occurs whenever a segment is updated. Requires the `read_customers` scope.

[Anchor to SELLING\_PLAN\_GROUPS\_CREATE](/docs/api/admin-graphql/latest/enums/WebhookSubscriptionTopic#enums-SELLING_PLAN_GROUPS_CREATE)SELLING\_PLAN\_GROUPS\_CREATE
:   The webhook topic for `selling_plan_groups/create` events. Notifies when a
    SellingPlanGroup is created. Requires the `read_products` scope.

[Anchor to SELLING\_PLAN\_GROUPS\_DELETE](/docs/api/admin-graphql/latest/enums/WebhookSubscriptionTopic#enums-SELLING_PLAN_GROUPS_DELETE)SELLING\_PLAN\_GROUPS\_DELETE
:   The webhook topic for `selling_plan_groups/delete` events. Notifies when a
    SellingPlanGroup is deleted. Requires the `read_products` scope.

[Anchor to SELLING\_PLAN\_GROUPS\_UPDATE](/docs/api/admin-graphql/latest/enums/WebhookSubscriptionTopic#enums-SELLING_PLAN_GROUPS_UPDATE)SELLING\_PLAN\_GROUPS\_UPDATE
:   The webhook topic for `selling_plan_groups/update` events. Notifies when a
    SellingPlanGroup is updated. Requires the `read_products` scope.

[Anchor to SHIPPING\_ADDRESSES\_CREATE](/docs/api/admin-graphql/latest/enums/WebhookSubscriptionTopic#enums-SHIPPING_ADDRESSES_CREATE)SHIPPING\_ADDRESSES\_CREATE
:   The webhook topic for `shipping_addresses/create` events. Occurs whenever a
    shipping address is created. Requires the `read_shipping` scope.

[Anchor to SHIPPING\_ADDRESSES\_UPDATE](/docs/api/admin-graphql/latest/enums/WebhookSubscriptionTopic#enums-SHIPPING_ADDRESSES_UPDATE)SHIPPING\_ADDRESSES\_UPDATE
:   The webhook topic for `shipping_addresses/update` events. Occurs whenever a
    shipping address is updated. Requires the `read_shipping` scope.

[Anchor to SHOP\_UPDATE](/docs/api/admin-graphql/latest/enums/WebhookSubscriptionTopic#enums-SHOP_UPDATE)SHOP\_UPDATE
:   The webhook topic for `shop/update` events. Occurs whenever a shop is updated.

[Anchor to SUBSCRIPTION\_BILLING\_ATTEMPTS\_CHALLENGED](/docs/api/admin-graphql/latest/enums/WebhookSubscriptionTopic#enums-SUBSCRIPTION_BILLING_ATTEMPTS_CHALLENGED)SUBSCRIPTION\_BILLING\_ATTEMPTS\_CHALLENGED
:   The webhook topic for `subscription_billing_attempts/challenged` events.
    Occurs when the financial instutition challenges the subscripttion billing
    attempt charge as per 3D Secure. Requires the
    `read_own_subscription_contracts` scope.

[Anchor to SUBSCRIPTION\_BILLING\_ATTEMPTS\_FAILURE](/docs/api/admin-graphql/latest/enums/WebhookSubscriptionTopic#enums-SUBSCRIPTION_BILLING_ATTEMPTS_FAILURE)SUBSCRIPTION\_BILLING\_ATTEMPTS\_FAILURE
:   The webhook topic for `subscription_billing_attempts/failure` events. Occurs
    whenever a subscription billing attempt fails. Requires the
    `read_own_subscription_contracts` scope.

[Anchor to SUBSCRIPTION\_BILLING\_ATTEMPTS\_SUCCESS](/docs/api/admin-graphql/latest/enums/WebhookSubscriptionTopic#enums-SUBSCRIPTION_BILLING_ATTEMPTS_SUCCESS)SUBSCRIPTION\_BILLING\_ATTEMPTS\_SUCCESS
:   The webhook topic for `subscription_billing_attempts/success` events. Occurs
    whenever a subscription billing attempt succeeds. Requires the
    `read_own_subscription_contracts` scope.

[Anchor to SUBSCRIPTION\_BILLING\_CYCLE\_EDITS\_CREATE](/docs/api/admin-graphql/latest/enums/WebhookSubscriptionTopic#enums-SUBSCRIPTION_BILLING_CYCLE_EDITS_CREATE)SUBSCRIPTION\_BILLING\_CYCLE\_EDITS\_CREATE
:   The webhook topic for `subscription_billing_cycle_edits/create` events. Occurs
    whenever a subscription contract billing cycle is edited. Requires the
    `read_own_subscription_contracts` scope.

[Anchor to SUBSCRIPTION\_BILLING\_CYCLE\_EDITS\_DELETE](/docs/api/admin-graphql/latest/enums/WebhookSubscriptionTopic#enums-SUBSCRIPTION_BILLING_CYCLE_EDITS_DELETE)SUBSCRIPTION\_BILLING\_CYCLE\_EDITS\_DELETE
:   The webhook topic for `subscription_billing_cycle_edits/delete` events. Occurs
    whenever a subscription contract billing cycle edit is deleted. Requires the
    `read_own_subscription_contracts` scope.

[Anchor to SUBSCRIPTION\_BILLING\_CYCLE\_EDITS\_UPDATE](/docs/api/admin-graphql/latest/enums/WebhookSubscriptionTopic#enums-SUBSCRIPTION_BILLING_CYCLE_EDITS_UPDATE)SUBSCRIPTION\_BILLING\_CYCLE\_EDITS\_UPDATE
:   The webhook topic for `subscription_billing_cycle_edits/update` events. Occurs
    whenever a subscription contract billing cycle edit is updated. Requires the
    `read_own_subscription_contracts` scope.

[Anchor to SUBSCRIPTION\_BILLING\_CYCLES\_SKIP](/docs/api/admin-graphql/latest/enums/WebhookSubscriptionTopic#enums-SUBSCRIPTION_BILLING_CYCLES_SKIP)SUBSCRIPTION\_BILLING\_CYCLES\_SKIP
:   The webhook topic for `subscription_billing_cycles/skip` events. Occurs
    whenever a subscription contract billing cycle is skipped. Requires the
    `read_own_subscription_contracts` scope.

[Anchor to SUBSCRIPTION\_BILLING\_CYCLES\_UNSKIP](/docs/api/admin-graphql/latest/enums/WebhookSubscriptionTopic#enums-SUBSCRIPTION_BILLING_CYCLES_UNSKIP)SUBSCRIPTION\_BILLING\_CYCLES\_UNSKIP
:   The webhook topic for `subscription_billing_cycles/unskip` events. Occurs
    whenever a subscription contract billing cycle is unskipped. Requires the
    `read_own_subscription_contracts` scope.

[Anchor to SUBSCRIPTION\_CONTRACTS\_ACTIVATE](/docs/api/admin-graphql/latest/enums/WebhookSubscriptionTopic#enums-SUBSCRIPTION_CONTRACTS_ACTIVATE)SUBSCRIPTION\_CONTRACTS\_ACTIVATE
:   The webhook topic for `subscription_contracts/activate` events. Occurs when a
    subscription contract is activated. Requires the
    `read_own_subscription_contracts` scope.

[Anchor to SUBSCRIPTION\_CONTRACTS\_CANCEL](/docs/api/admin-graphql/latest/enums/WebhookSubscriptionTopic#enums-SUBSCRIPTION_CONTRACTS_CANCEL)SUBSCRIPTION\_CONTRACTS\_CANCEL
:   The webhook topic for `subscription_contracts/cancel` events. Occurs when a
    subscription contract is canceled. Requires the
    `read_own_subscription_contracts` scope.

[Anchor to SUBSCRIPTION\_CONTRACTS\_CREATE](/docs/api/admin-graphql/latest/enums/WebhookSubscriptionTopic#enums-SUBSCRIPTION_CONTRACTS_CREATE)SUBSCRIPTION\_CONTRACTS\_CREATE
:   The webhook topic for `subscription_contracts/create` events. Occurs whenever
    a subscription contract is created. Requires the
    `read_own_subscription_contracts` scope.

[Anchor to SUBSCRIPTION\_CONTRACTS\_EXPIRE](/docs/api/admin-graphql/latest/enums/WebhookSubscriptionTopic#enums-SUBSCRIPTION_CONTRACTS_EXPIRE)SUBSCRIPTION\_CONTRACTS\_EXPIRE
:   The webhook topic for `subscription_contracts/expire` events. Occurs when a
    subscription contract expires. Requires the `read_own_subscription_contracts` scope.

[Anchor to SUBSCRIPTION\_CONTRACTS\_FAIL](/docs/api/admin-graphql/latest/enums/WebhookSubscriptionTopic#enums-SUBSCRIPTION_CONTRACTS_FAIL)SUBSCRIPTION\_CONTRACTS\_FAIL
:   The webhook topic for `subscription_contracts/fail` events. Occurs when a
    subscription contract is failed. Requires the
    `read_own_subscription_contracts` scope.

[Anchor to SUBSCRIPTION\_CONTRACTS\_PAUSE](/docs/api/admin-graphql/latest/enums/WebhookSubscriptionTopic#enums-SUBSCRIPTION_CONTRACTS_PAUSE)SUBSCRIPTION\_CONTRACTS\_PAUSE
:   The webhook topic for `subscription_contracts/pause` events. Occurs when a
    subscription contract is paused. Requires the
    `read_own_subscription_contracts` scope.

[Anchor to SUBSCRIPTION\_CONTRACTS\_UPDATE](/docs/api/admin-graphql/latest/enums/WebhookSubscriptionTopic#enums-SUBSCRIPTION_CONTRACTS_UPDATE)SUBSCRIPTION\_CONTRACTS\_UPDATE
:   The webhook topic for `subscription_contracts/update` events. Occurs whenever
    a subscription contract is updated. Requires the
    `read_own_subscription_contracts` scope.

[Anchor to TAX\_SERVICES\_CREATE](/docs/api/admin-graphql/latest/enums/WebhookSubscriptionTopic#enums-TAX_SERVICES_CREATE)TAX\_SERVICES\_CREATE
:   The webhook topic for `tax_services/create` events. Occurs whenever a tax
    service is created. Requires the `read_taxes` scope.

[Anchor to TAX\_SERVICES\_UPDATE](/docs/api/admin-graphql/latest/enums/WebhookSubscriptionTopic#enums-TAX_SERVICES_UPDATE)TAX\_SERVICES\_UPDATE
:   The webhook topic for `tax_services/update` events. Occurs whenver a tax
    service is updated. Requires the `read_taxes` scope.

[Anchor to TENDER\_TRANSACTIONS\_CREATE](/docs/api/admin-graphql/latest/enums/WebhookSubscriptionTopic#enums-TENDER_TRANSACTIONS_CREATE)TENDER\_TRANSACTIONS\_CREATE
:   The webhook topic for `tender_transactions/create` events. Occurs when a
    tender transaction is created. Requires the `read_orders` scope.

[Anchor to THEMES\_CREATE](/docs/api/admin-graphql/latest/enums/WebhookSubscriptionTopic#enums-THEMES_CREATE)THEMES\_CREATE
:   The webhook topic for `themes/create` events. Occurs whenever a theme is
    created. Does not occur when theme files are created. Requires the
    `read_themes` scope.

[Anchor to THEMES\_DELETE](/docs/api/admin-graphql/latest/enums/WebhookSubscriptionTopic#enums-THEMES_DELETE)THEMES\_DELETE
:   The webhook topic for `themes/delete` events. Occurs whenever a theme is
    deleted. Does not occur when theme files are deleted. Requires the
    `read_themes` scope.

[Anchor to THEMES\_PUBLISH](/docs/api/admin-graphql/latest/enums/WebhookSubscriptionTopic#enums-THEMES_PUBLISH)THEMES\_PUBLISH
:   The webhook topic for `themes/publish` events. Occurs whenever a theme with
    the main or mobile (deprecated) role is published. Requires the `read_themes` scope.

[Anchor to THEMES\_UPDATE](/docs/api/admin-graphql/latest/enums/WebhookSubscriptionTopic#enums-THEMES_UPDATE)THEMES\_UPDATE
:   The webhook topic for `themes/update` events. Occurs whenever a theme is
    updated. Does not occur when theme files are updated. Requires the
    `read_themes` scope.

[Anchor to VARIANTS\_IN\_STOCK](/docs/api/admin-graphql/latest/enums/WebhookSubscriptionTopic#enums-VARIANTS_IN_STOCK)VARIANTS\_IN\_STOCK
:   The webhook topic for `variants/in_stock` events. Occurs whenever a variant
    becomes in stock. Online channels receive this webhook only when the variant
    becomes in stock online. Requires the `read_products` scope.

[Anchor to VARIANTS\_OUT\_OF\_STOCK](/docs/api/admin-graphql/latest/enums/WebhookSubscriptionTopic#enums-VARIANTS_OUT_OF_STOCK)VARIANTS\_OUT\_OF\_STOCK
:   The webhook topic for `variants/out_of_stock` events. Occurs whenever a
    variant becomes out of stock. Online channels receive this webhook only when
    the variant becomes out of stock online. Requires the `read_products` scope.

---

Was this section helpful?

## [Anchor to Fields](/docs/api/admin-graphql/latest/enums/WebhookSubscriptionTopic#fields)Fields

[Anchor to WebhookSubscription.topic](/docs/api/admin-graphql/latest/enums/WebhookSubscriptionTopic#reference-WebhookSubscription.topic)[WebhookSubscription.topic](/docs/api/admin-graphql/latest/objects/WebhookSubscription#field-WebhookSubscription.fields.topic) •OBJECT
:   A webhook subscription is a persisted data object created by an app using the REST Admin API or GraphQL Admin API.
    It describes the topic that the app wants to receive, and a destination where
    Shopify should send webhooks of the specified topic.
    When an event for a given topic occurs, the webhook subscription sends a relevant payload to the destination.
    Learn more about the [webhooks system](https://shopify.dev/apps/webhooks).

[Anchor to QueryRoot.webhookSubscriptions(topics)](/docs/api/admin-graphql/latest/enums/WebhookSubscriptionTopic#reference-QueryRoot.webhookSubscriptions(topics))[QueryRoot.webhookSubscriptions(topics)](/docs/api/admin-graphql/latest/objects/QueryRoot#field-QueryRoot.fields.webhookSubscriptions.arguments.topics) •ARGUMENT
:   The schema's entry-point for queries. This acts as the public, top-level API from which all queries must start.

[Anchor to eventBridgeWebhookSubscriptionCreate.topic](/docs/api/admin-graphql/latest/enums/WebhookSubscriptionTopic#reference-eventBridgeWebhookSubscriptionCreate.topic)[eventBridgeWebhookSubscriptionCreate.topic](/docs/api/admin-graphql/latest/mutations/eventBridgeWebhookSubscriptionCreate#arguments-topic) •ARGUMENT

[Anchor to pubSubWebhookSubscriptionCreate.topic](/docs/api/admin-graphql/latest/enums/WebhookSubscriptionTopic#reference-pubSubWebhookSubscriptionCreate.topic)[pubSubWebhookSubscriptionCreate.topic](/docs/api/admin-graphql/latest/mutations/pubSubWebhookSubscriptionCreate#arguments-topic) •ARGUMENT

[Anchor to webhookSubscriptionCreate.topic](/docs/api/admin-graphql/latest/enums/WebhookSubscriptionTopic#reference-webhookSubscriptionCreate.topic)[webhookSubscriptionCreate.topic](/docs/api/admin-graphql/latest/mutations/webhookSubscriptionCreate#arguments-topic) •ARGUMENT

[Anchor to webhookSubscriptions.topics](/docs/api/admin-graphql/latest/enums/WebhookSubscriptionTopic#reference-webhookSubscriptions.topics)[webhookSubscriptions.topics](/docs/api/admin-graphql/latest/queries/webhookSubscriptions#arguments-topics) •ARGUMENT

---

Was this section helpful?
