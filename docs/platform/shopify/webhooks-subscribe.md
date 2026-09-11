---
title: "Webhooks: subscribe"
source: "https://shopify.dev/docs/apps/build/webhooks/subscribe"
final_url: "https://shopify.dev/docs/apps/build/webhooks/subscribe"
platform: "shopify"
fetched_at: "2026-09-11T09:20:10Z"
last_checked_at: "2026-09-11T10:17:58Z"
previous_fetched_at: ""
http_status: "200"
format: "html-converted"
sha256: "fc65e51001fa54ddb22fd348a3fe5c3afb601d023a6e6f25402623405abd0d26"
---

A webhook subscription tells Shopify which events your app is interested in and where to deliver them.

This page covers the subscription configuration options, including how to choose between subscription types and delivery methods.
To shape the content of each delivery, see [Delivery structure](/docs/apps/build/webhooks/delivery-structure) and [Delivery filtering](/docs/apps/build/webhooks/delivery-filtering).

---

## [Anchor to Requirements](/docs/apps/build/webhooks/subscribe#requirements)Requirements

Each topic you subscribe to requires a corresponding [access scope](/docs/api/usage/access-scopes).
See the [Webhooks reference](/docs/api/webhooks) for the full list of topics and their required scopes.

If your app is distributed through the Shopify App Store, it must be subscribed to Shopify's [mandatory compliance topics](/docs/apps/build/privacy-law-compliance).
You can create mandatory compliance webhook subscriptions in Dev Dashboard or by updating your [app configuration file](/docs/apps/build/cli-for-apps/app-configuration#app-configuration-file-example).

---

## [Anchor to Versioning](/docs/apps/build/webhooks/subscribe#versioning)Versioning

Like most Shopify APIs, webhooks are [versioned](/docs/api/usage/versioning). Shopify recommends updating to the latest stable API version each quarter.
The `api_version` field in `[webhooks]` controls the GraphQL Admin API version used to serialize payloads for all [app-specific subscriptions](#app-specific-subscriptions):

1

2

[webhooks]

api\_version = "2026-07"

For [shop-specific subscriptions](#shop-specific-subscriptions) created using the GraphQL Admin API, the version is determined by the request URL.

Each delivery includes the API version that serialized its payload. For HTTPS deliveries, check the [`X-Shopify-API-Version` header](/docs/apps/build/webhooks/delivery-structure#headers). For Google Cloud Pub/Sub or Amazon EventBridge, the version appears in the message payload instead.

Before updating `api_version`, test the new version against your handler code using the CLI:

1

shopify app webhook trigger --api-version=<new-version> --address=<destination> --topic=<topic-name>

Pass with the flags shown above, or run the command with no parameters and follow the prompts.
Your existing subscriptions will continue using the earlier version until you update and deploy.

### [Anchor to Update the API version](/docs/apps/build/webhooks/subscribe#update-the-api-version)Update the API version

#### App configuration file

1. Set `webhooks.api_version` to the new version in `shopify.app.toml`.
2. Save the file. If `app dev` is running, the version updates automatically for your dev store.
3. Run `shopify app deploy` to release the change to production.

#### Dev Dashboard

1. From your [Dev Dashboard](https://dev.shopify.com/dashboard), go to **Apps**.
2. Click on your app.
3. Click **Versions** → **Create a version**.
4. In the **Webhooks API Version** field, select the newer API version.
5. Click **Release**.

1. Set `webhooks.api_version` to the new version in `shopify.app.toml`.
2. Save the file. If `app dev` is running, the version updates automatically for your dev store.
3. Run `shopify app deploy` to release the change to production.

---

## [Anchor to Subscription types](/docs/apps/build/webhooks/subscribe#subscription-types)Subscription types

Shopify supports two ways to configure webhook subscriptions:

- **[App-specific subscriptions](#app-specific-subscriptions)**: (Recommended) Defined in `shopify.app.toml` and applied uniformly across every shop that installs your app.
- **[Shop-specific subscriptions](#shop-specific-subscriptions)**: Created using GraphQL Admin API; configuration can differ per shop.

Choose app-specific subscriptions unless your topics, delivery URIs, or filters need to vary between shops.
Use the table below to compare the capabilities and behavior of these two options:

|  | App-specific | Shop-specific |
| --- | --- | --- |
| **Compliance topics** | Supported. See [Privacy law compliance](/docs/apps/build/compliance/privacy-law-compliance#subscribe-to-compliance-webhooks). | Can be configured in your app configuration file. **Cannot** be subscribed to using the Admin API. |
| **Differentiating between methods** | Available in the **Subscription Method** field in **Logs** | Available in the **Subscription Method** field in **Logs** |
| **Identifying your subscriptions** | No ID, denoted **config-managed** | Available as the **Subscription ID** field in **Logs**. [Query by subscription ID](/docs/api/admin-graphql/latest/queries/webhookSubscription). |
| **Interface for management** | Your app configuration file | GraphQL Admin API |
| **Metafield namespaces** | Does not support `metafieldNamespaces` | `metafieldNamespaces` can be used as an input field ([example](/docs/api/admin-graphql/latest/mutations/webhookSubscriptionCreate#argument-webhooksubscription)). |
| **Scopes** | Requires scopes in your app configuration file | Scopes can be configured in your app configuration file or in your Dev Dashboard. They **cannot** be set using the Admin API. |
| **[Topics](/docs/api/webhooks)** | Supports every topic except `product_feeds/full_sync`, `product_feeds/full_sync_finish`, and `product_feeds/incremental_sync`. | Supports every topic. |
| **[Troubleshooting](/docs/apps/build/webhooks/troubleshoot)** | Failing subscriptions will **not** be deleted by Shopify. | Failing subscriptions will be deleted by Shopify. |
| **Viewing subscriptions** | Available under **Subscriptions** in your app's Dev Dashboard > **Versions** > **Configuration** | Query the GraphQL Admin API ([example](/docs/api/admin-graphql/latest/queries/webhookSubscriptions)). |

Shopify recommends using Google Pub/Sub as a cloud-based solution for delivering webhooks. You can also use Amazon EventBridge. If you prefer to build your own webhooks infrastructure, you can deliver through HTTPS, but there are [extra considerations to take into account](/docs/apps/build/webhooks/verify-deliveries#https-delivery-considerations).

If you have shop-specific subscriptions and are migrating to app-specific subscriptions, remove existing subscriptions to the same topics first to avoid conflicts and duplicate notifications.
See [Migrate to app-specific subscriptions](#migrate-to-app-specific-subscriptions).

---

## [Anchor to App-specific subscriptions](/docs/apps/build/webhooks/subscribe#app-specific-subscriptions)App-specific subscriptions

You can subscribe your app to webhook topics using your app configuration file, rather than using the Admin API.
Use this to configure and manage your subscriptions across all shops where your app is installed.
Shopify recommends subscribing to webhooks using this approach.

1

2

3

4

5

6

[webhooks]

api\_version = "2026-07"

[[webhooks.subscriptions]]

topics = ["products/create"]

uri = "https://your-app.example.com/webhooks/products"

1

2

3

4

5

6

7

8

9

10

11

12

13

14

15

16

{

"id": 9554194432293,

"title": "T-Shirt",

"status": "active",

"vendor": "My Store",

"product\_type": "Shirts",

"variants": [

{

"id": 123456789,

"title": "Default Title",

"price": "29.99",

"sku": "TSHIRT-001"

}

],

"tags": "cotton, comfortable"

}

##### shopify.app.toml

```
[webhooks]
api_version = "2026-07"

[[webhooks.subscriptions]]
topics = ["products/create"]
uri = "https://your-app.example.com/webhooks/products"
```

##### {} Response

```
{
  "id": 9554194432293,
  "title": "T-Shirt",
  "status": "active",
  "vendor": "My Store",
  "product_type": "Shirts",
  "variants": [
    {
      "id": 123456789,
      "title": "Default Title",
      "price": "29.99",
      "sku": "TSHIRT-001"
    }
  ],
  "tags": "cotton, comfortable"
}
```

### [Anchor to Subscription fields](/docs/apps/build/webhooks/subscribe#subscription-fields)Subscription fields

Each webhook subscription is defined by a `[[webhooks.subscriptions]]` entry in your `shopify.app.toml` file.
Every subscription requires the following fields:

| Field | Purpose |
| --- | --- |
| `topics` | One or more topic names to subscribe to (for example `products/create`). |
| `uri` | Delivery destination. HTTPS URL, AWS EventBridge ARN, or Google Pub/Sub URI. |

Additional optional fields are available for [filtering deliveries](/docs/apps/build/webhooks/delivery-filtering), [defining their response structure](/docs/apps/build/webhooks/delivery-structure), identifying subscriptions, and subscribing to compliance topics:

| Field | Purpose |
| --- | --- |
| `include_fields` | Fields to include in the payload. If omitted, the full payload is sent. See [Delivery filtering](/docs/apps/build/webhooks/delivery-filtering). |
| `filter` | Filter expression to gate deliveries. See [Delivery filtering](/docs/apps/build/webhooks/delivery-filtering). |
| `name` | Subscription name. Shopify echoes this in the [`X-Shopify-Name` header](/docs/apps/build/webhooks/delivery-structure#headers). Use to label and differentiate subscriptions to the same topic. Alphanumeric, `-`, `_`, up to 50 characters. |
| `compliance_topics` | The compliance topics to subscribe to for managing requests to view or erase customer personal information. Valid options are `customers/redact`, `customers/data_request`, and `shop/redact`. These topics are required for all apps distributed through the Shopify App Store. See [Privacy law compliance](/docs/apps/build/compliance/privacy-law-compliance#subscribe-to-compliance-webhooks). |

### [Anchor to Migrate to app-specific subscriptions](/docs/apps/build/webhooks/subscribe#migrate-to-app-specific-subscriptions)Migrate to app-specific subscriptions

If you have shop-specific subscriptions already, and are migrating your app to app-specific subscriptions, then make sure you first remove any existing webhook subscriptions to the same topics. This avoids potential conflicts and duplicate notifications.

1. Check the list of existing shop-specific webhook topics your app is subscribed to by using the [GraphQL Admin API `webhookSubscriptions` query](/docs/api/admin-graphql/latest/queries/webhookSubscriptions).
2. Delete the relevant queries, subscription, and handler code from your app.
3. Deploy a new version of your app by running `shopify app deploy`. You can check that your subscriptions have been deleted by checking the **Versions** page for your app in the Dev Dashboard.
4. Configure your app to subscribe to app-specific subscriptions. Refer to the [create a subscription](/docs/apps/build/webhooks/get-started) tutorial to get started.

---

## [Anchor to Shop-specific subscriptions](/docs/apps/build/webhooks/subscribe#shop-specific-subscriptions)Shop-specific subscriptions

To subscribe to webhook topics where the configuration depends on the shop your app is installed on, use the GraphQL Admin API.
For the available input fields, see [`WebhookSubscriptionInput`](/docs/api/admin-graphql/latest/input-objects/WebhookSubscriptionInput).

#### React Router template

Shopify recommends that you use the Shopify CLI and React Router template when subscribing to webhooks using the GraphQL Admin API.
The template abstracts away the actual GraphQL mutation you would otherwise have to write.

In `app/shopify.server.ts`, add your subscription to the `webhooks` config and register it in the `afterAuth` hook:

1

2

3

4

5

6

7

8

9

10

11

12

13

14

const shopify = shopifyApp({

webhooks: {

ORDERS\_CREATED: {

deliveryMethod: DeliveryMethod.PubSub,

pubSubProject: "<GCP-PROJECT>",

pubSubTopic: "<PUB\_SUB\_TOPIC>",

},

},

hooks: {

afterAuth: async ({ session }) => {

shopify.registerWebhooks({ session });

},

},

});

1

2

3

4

5

6

7

8

9

10

11

12

13

const shopify = shopifyApp({

webhooks: {

ORDERS\_CREATED: {

deliveryMethod: DeliveryMethod.EventBridge,

arn: "<ARN>",

},

},

hooks: {

afterAuth: async ({ session }) => {

shopify.registerWebhooks({ session });

},

},

});

##### Google Pub/Sub

```
const shopify = shopifyApp({
  webhooks: {
    ORDERS_CREATED: {
      deliveryMethod: DeliveryMethod.PubSub,
      pubSubProject: "<GCP-PROJECT>",
      pubSubTopic: "<PUB_SUB_TOPIC>",
    },
  },
  hooks: {
    afterAuth: async ({ session }) => {
      shopify.registerWebhooks({ session });
    },
  },
});
```

##### Amazon EventBridge

```
const shopify = shopifyApp({
  webhooks: {
    ORDERS_CREATED: {
      deliveryMethod: DeliveryMethod.EventBridge,
      arn: "<ARN>",
    },
  },
  hooks: {
    afterAuth: async ({ session }) => {
      shopify.registerWebhooks({ session });
    },
  },
});
```

  

If you're using Amazon EventBridge, set `arn` to the ARN that you retrieved when you associated your event bus during setup.

#### GraphQL Admin API

Use the [`webhookSubscriptionCreate`](/docs/api/admin-graphql/latest/mutations/webhookSubscriptionCreate) mutation. Specify the topic using GraphQL enum screaming case syntax (for example, `ORDERS_CREATE`).

**Request**: `POST /admin/api/2026-07/graphql.json`

1

2

3

4

5

6

7

8

9

10

11

12

13

14

15

16

mutation webhookSubscriptionCreate($topic: WebhookSubscriptionTopic!, $webhookSubscription: WebhookSubscriptionInput!) {

webhookSubscriptionCreate(topic: $topic, webhookSubscription: $webhookSubscription) {

userErrors {

field

message

}

webhookSubscription {

id

format

includeFields

metafieldNamespaces

topic

uri

}

}

}

For Google Pub/Sub, set `uri` to `pubsub://{project-id}:{topic-id}`. For Amazon EventBridge, set `uri` to the ARN from your EventBridge console under **Partner Event Sources**.

Add this code wherever you process your after-authentication hooks. This is the equivalent of `app/shopify.server.ts` in the React Router template.

You can also test with [example GraphQL queries](/docs/api/admin-graphql/latest/queries/webhookSubscriptions#section-examples) using the [GraphiQL](/docs/api/usage/api-exploration/admin-graphiql-explorer) interface by pressing `g` in the console where your app is running. You must include values for the variables to execute the mutation.

Shopify recommends that you use the Shopify CLI and React Router template when subscribing to webhooks using the GraphQL Admin API.
The template abstracts away the actual GraphQL mutation you would otherwise have to write.

In `app/shopify.server.ts`, add your subscription to the `webhooks` config and register it in the `afterAuth` hook:

1

2

3

4

5

6

7

8

9

10

11

12

13

14

const shopify = shopifyApp({

webhooks: {

ORDERS\_CREATED: {

deliveryMethod: DeliveryMethod.PubSub,

pubSubProject: "<GCP-PROJECT>",

pubSubTopic: "<PUB\_SUB\_TOPIC>",

},

},

hooks: {

afterAuth: async ({ session }) => {

shopify.registerWebhooks({ session });

},

},

});

1

2

3

4

5

6

7

8

9

10

11

12

13

const shopify = shopifyApp({

webhooks: {

ORDERS\_CREATED: {

deliveryMethod: DeliveryMethod.EventBridge,

arn: "<ARN>",

},

},

hooks: {

afterAuth: async ({ session }) => {

shopify.registerWebhooks({ session });

},

},

});

##### Google Pub/Sub

```
const shopify = shopifyApp({
  webhooks: {
    ORDERS_CREATED: {
      deliveryMethod: DeliveryMethod.PubSub,
      pubSubProject: "<GCP-PROJECT>",
      pubSubTopic: "<PUB_SUB_TOPIC>",
    },
  },
  hooks: {
    afterAuth: async ({ session }) => {
      shopify.registerWebhooks({ session });
    },
  },
});
```

##### Amazon EventBridge

```
const shopify = shopifyApp({
  webhooks: {
    ORDERS_CREATED: {
      deliveryMethod: DeliveryMethod.EventBridge,
      arn: "<ARN>",
    },
  },
  hooks: {
    afterAuth: async ({ session }) => {
      shopify.registerWebhooks({ session });
    },
  },
});
```

  

If you're using Amazon EventBridge, set `arn` to the ARN that you retrieved when you associated your event bus during setup.

When using Google Cloud Pub/Sub or Amazon EventBridge, deliveries include additional fields beyond the sample payloads in the [Webhooks reference](/docs/api/webhooks). HMAC verification is not required for cloud event bus deliveries.

### [Anchor to Custom apps](/docs/apps/build/webhooks/subscribe#custom-apps)Custom apps

Webhooks are available for all custom apps to use. However, custom apps created in the Shopify admin cannot take advantage of the tooling available through the Shopify CLI, including subscribing to webhook topics using the app configuration file.

This means that webhook subscriptions must be set up and configured using the GraphQL Admin API.

1. Create an app in the Shopify Admin and install it on your test shop to get your Admin API Access token.
2. Configure your Admin API scopes by selecting the scopes that you'll need for each webhook topic that you intend to subscribe to. Learn more about which topics require which Shopify scopes in the [Webhooks reference](/docs/api/webhooks).
3. Subscribe to webhook topics [using the Admin API](#shop-specific-subscriptions) and your Admin API access token.

---

## [Anchor to Topics](/docs/apps/build/webhooks/subscribe#topics)Topics

A topic identifies both the resource and the action that qualifies a delivery.
For example, `products/update` fires when an existing product changes; `products/create` fires when a new one is created.
You can list multiple topics in a single subscription to route qualifying events from each to the same `uri`.

See the [Webhooks reference](/docs/api/webhooks) for the full list of supported topics and their required scopes.

Try Events

Events is in developer preview for a subset of topics. If your topic is supported, you can run an Events subscription alongside this webhook in the same `shopify.app.toml`. Check the [Events reference](/docs/api/events) for supported topics.

**Try Events:**

Events is in developer preview for a subset of topics. If your topic is supported, you can run an Events subscription alongside this webhook in the same `shopify.app.toml`. Check the [Events reference](/docs/api/events) for supported topics.

---

## [Anchor to Test your subscriptions](/docs/apps/build/webhooks/subscribe#test-your-subscriptions)Test your subscriptions

Use the Shopify CLI [`webhook trigger`](/docs/api/shopify-cli/app/app-webhook-trigger) command to test delivery. Pass flags directly or run with no parameters and follow the prompts:

1

shopify app webhook trigger --api-version=<version> --address=<destination> --topic=<topic-name>

For the `--address` flag, use the appropriate format for your delivery method:

| Delivery method | `--address` value |
| --- | --- |
| Amazon EventBridge | Your ARN from the EventBridge console under **Partner Event Sources** > **Select your event source** > **Partner event source ARN** |
| HTTPS | Your endpoint URL |
| Google Pub/Sub | `pubsub://{project-id}:{topic-id}` — your GCP project ID and Pub/Sub topic ID |

---

## [Anchor to Example](/docs/apps/build/webhooks/subscribe#example)Example

The following subscription listens for new product creations and delivers to a single endpoint.
It uses no `filter` or `include_fields`, so every qualifying creation fires a delivery with the full product payload.

1

2

3

4

5

6

[webhooks]

api\_version = "2026-07"

[[webhooks.subscriptions]]

topics = ["products/create"]

uri = "https://your-app.example.com/webhooks/products"

1

2

3

4

5

6

7

8

9

10

11

12

13

14

15

16

{

"id": 9554194432293,

"title": "T-Shirt",

"status": "active",

"vendor": "My Store",

"product\_type": "Shirts",

"variants": [

{

"id": 123456789,

"title": "Default Title",

"price": "29.99",

"sku": "TSHIRT-001"

}

],

"tags": "cotton, comfortable"

}

##### shopify.app.toml

```
[webhooks]
api_version = "2026-07"

[[webhooks.subscriptions]]
topics = ["products/create"]
uri = "https://your-app.example.com/webhooks/products"
```

##### {} Response

```
{
  "id": 9554194432293,
  "title": "T-Shirt",
  "status": "active",
  "vendor": "My Store",
  "product_type": "Shirts",
  "variants": [
    {
      "id": 123456789,
      "title": "Default Title",
      "price": "29.99",
      "sku": "TSHIRT-001"
    }
  ],
  "tags": "cotton, comfortable"
}
```

---

## [Anchor to Next steps](/docs/apps/build/webhooks/subscribe#next-steps)Next steps

- [Delivery filtering](/docs/apps/build/webhooks/delivery-filtering): Gate deliveries with `filter` expressions.
- [Delivery structure](/docs/apps/build/webhooks/delivery-structure): Shape the payload with `include_fields`.

---

Was this page helpful?
