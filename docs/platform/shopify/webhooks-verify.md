---
title: "Webhooks: verify deliveries"
source: "https://shopify.dev/docs/apps/build/webhooks/verify-deliveries"
final_url: "https://shopify.dev/docs/apps/build/webhooks/verify-deliveries"
platform: "shopify"
fetched_at: "2026-09-11T09:20:10Z"
last_checked_at: "2026-09-11T10:17:58Z"
previous_fetched_at: ""
http_status: "200"
format: "html-converted"
sha256: "ed7530f451cff9960d8c9e1afc791540f175c09efa546b2b87274db565ac6831"
---

Each delivery includes an HMAC signature to confirm it came from Shopify, and a delivery ID you can use to detect duplicates.
Verify both before processing.
If you're delivering over HTTPS, see [HTTPS delivery considerations](#https-delivery-considerations) for additional requirements.

---

## [Anchor to HMAC verification](/docs/apps/build/webhooks/verify-deliveries#hmac-verification)HMAC verification

Each HTTPS delivery includes a base64-encoded HMAC signature in the [`X-Shopify-Hmac-SHA256` header](/docs/apps/build/webhooks/delivery-structure#headers), generated using your app's client secret and the raw request body.
Verify this signature before processing to confirm the delivery came from Shopify.
HMAC verification applies to HTTPS deliveries only. Google Cloud Pub/Sub and Amazon EventBridge deliveries don't require it.

If you're using the [React Router template](/docs/api/shopify-app-react-router/latest/guide-webhooks#endpoints), verification is handled automatically before your handler runs:

1

2

3

4

5

6

7

8

9

import { authenticate } from "../shopify.server";

export const action = async ({ request }) => {

const { shop, session, topic } = await authenticate.webhook(request);

console.log(`Received ${topic} webhook for ${shop}`);

return new Response();

};

Always verify HMAC before trusting payload contents. Skip verification only in development with mock tools.
If you [rotate your app's client secret](/docs/apps/build/authentication-authorization/manage-credentials#rotate-your-client-secret), it can take up to an hour for the HMAC digest to be generated using the new secret.

### [Anchor to Manual verification](/docs/apps/build/webhooks/verify-deliveries#manual-verification)Manual verification

To validate manually, compute HMAC-SHA256 of the raw request body using your app's client secret as the key, then compare it to the decoded header value.
Reject any delivery where the signatures don't match.

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

17

18

19

const express = require('express');

const crypto = require('crypto');

const app = express();

const appClientSecret = process.env.CLIENT\_SECRET;

app.use(express.raw({ type: '\*/\*' }));

app.post('\*', (req, res) => {

const shopifyHmac = req.headers['x-shopify-hmac-sha256'];

const calculatedHmacDigest = crypto.createHmac('sha256', appClientSecret).update(req.body).digest('base64');

const hmacValid = crypto.timingSafeEqual(Buffer.from(calculatedHmacDigest, 'base64'), Buffer.from(shopifyHmac, 'base64'));

if (hmacValid) {

res.send('HMAC validation successful.');

} else {

res.status(401).send('HMAC validation failed.');

}

});

Or use the [ShopifyApp library](/docs/api/shopify-app-react-router/latest/entrypoints/shopifyapp) to handle header processing, stringifying, and payload parsing:

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

app.post('/webhooks', express.text({type: '\*/\*'}), async (req, res) => {

const {valid, topic, domain} = await shopify.webhooks.validate({

rawBody: req.body, // is a string

rawRequest: req,

rawResponse: res,

});

if (!valid) {

// This is not a valid request!

res.send(400); // Bad Request

}

// Run my webhook-processing code here

});

For more details, refer to the library documentation for [webhooks](https://github.com/Shopify/shopify-app-js/blob/main/packages/apps/shopify-api/docs/guides/webhooks.md) and [validation](https://github.com/Shopify/shopify-app-js/blob/main/packages/apps/shopify-api/docs/reference/webhooks/validate.md).

When validating manually, watch for these common issues:

- **Raw body parsing**: HMAC verification requires the raw request body. If you're using a body parser middleware like `express.json()`, it parses the body before your verification code runs. Capture the raw body before it's parsed.
- **Middleware order**: Place your webhook verification middleware before any body parsing middleware in your app.
- **Encoding**: Ensure your encoding is set correctly.

---

## [Anchor to Ignoring duplicates](/docs/apps/build/webhooks/verify-deliveries#ignoring-duplicates)Ignoring duplicates

Shopify minimizes duplicate deliveries, but your app might receive the same webhook more than once, for example after a network timeout or a retry.

Process webhooks using idempotent operations so that receiving the same webhook twice doesn't produce a different outcome.
If your processing isn't idempotent, use the `X-Shopify-Webhook-Id` header to detect and skip duplicates:

1. Extract `X-Shopify-Webhook-Id` from the request headers.
2. Check your persistent store for that ID.
3. If it exists, skip processing and return a success response.
4. If it's new, process the delivery and save the ID.

Note

If you have more than one subscription for the same topic, you'll receive a separate delivery per subscription. Each has a different `X-Shopify-Webhook-Id` but shares the same `X-Shopify-Event-Id`. Use `X-Shopify-Webhook-Id` to deduplicate individual deliveries. Use `X-Shopify-Event-Id` to correlate deliveries that originated from the same merchant action.

**Note:**

If you have more than one subscription for the same topic, you'll receive a separate delivery per subscription. Each has a different `X-Shopify-Webhook-Id` but shares the same `X-Shopify-Event-Id`. Use `X-Shopify-Webhook-Id` to deduplicate individual deliveries. Use `X-Shopify-Event-Id` to correlate deliveries that originated from the same merchant action.

---

## [Anchor to HTTPS delivery considerations](/docs/apps/build/webhooks/verify-deliveries#https-delivery-considerations)HTTPS delivery considerations

The following applies when using HTTPS delivery. Cloud-based event buses (Google Pub/Sub and Amazon EventBridge) handle these concerns for you.
Shopify sends an HTTP POST request to your URI and verifies SSL certificates on delivery.

During development, your CloudFlare tunnel URL changes each time you run `shopify app dev`. Use a relative path for your URI to avoid updating your subscription on each restart: `uri = "/webhooks"`.

### [Anchor to Respond with a 200 OK quickly](/docs/apps/build/webhooks/verify-deliveries#respond-with-a-200-ok-quickly)Respond with a 200 OK quickly

Your system acknowledges receipt by sending Shopify a `200 OK` response. Any response outside the 200 range, including 3XX codes, is treated as an error. Shopify has a one-second connection timeout and a five-second timeout for the entire request.

Shopify's delivery system uses [HTTP Keep-Alive](https://developer.mozilla.org/en-US/docs/Web/HTTP/Headers/Keep-Alive) to reuse connections to the same host. Ensure `Keep-Alive` is enabled on your endpoint to reduce overhead from concurrent requests.

### [Anchor to Queue webhooks to handle traffic bursts](/docs/apps/build/webhooks/verify-deliveries#queue-webhooks-to-handle-traffic-bursts)Queue webhooks to handle traffic bursts

Queuing is a useful pattern for handling bursts of traffic and for ensuring you respond within five seconds. Install a package like [Better Queue](https://www.npmjs.com/package/better-queue) to store payloads and process them asynchronously. A common practice is to also build a reconciliation job that periodically retrieves data you might have missed using Shopify APIs.

### [Anchor to Retries and failures](/docs/apps/build/webhooks/verify-deliveries#retries-and-failures)Retries and failures

If Shopify receives no response or an error, it retries 8 times over the next 4 hours. After 8 consecutive failures, the subscription is automatically deleted if it was configured using the Admin API. Warning emails are sent to the app's emergency developer email address. See [Troubleshoot webhooks](/docs/apps/build/webhooks/troubleshoot) for more information.

---

## [Anchor to Next steps](/docs/apps/build/webhooks/verify-deliveries#next-steps)Next steps

- [Troubleshoot webhooks](/docs/apps/build/webhooks/troubleshoot): Diagnose delivery failures and inspect logs.
- [Webhooks reference](/docs/api/webhooks): Full list of topics, payloads, and required scopes.

---

Was this page helpful?
