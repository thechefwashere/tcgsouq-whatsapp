---
title: "Messenger and Instagram marketing messages (opt-in recurring notifications)"
source: "https://developers.facebook.com/docs/messenger-platform/marketing-messages"
final_url: "https://developers.facebook.com/docs/messenger-platform/marketing-messages"
platform: "messenger"
fetched_at: "2026-09-11T10:17:58Z"
last_checked_at: "2026-09-11T10:17:58Z"
previous_fetched_at: "2026-09-11T10:13:18Z"
http_status: "200"
format: "html-converted"
sha256: "ffe02fe68dbf3db84e820b2035fb7a86cb58fb3323d21cbc79d191027eae292d"
---

# Marketing Messages

(Also known as Recurring Notifications)

This document shows you how to request permission from a person to send marketing messages (also known as Recurring Notifications), about the specific requirements and limitations for sending requests, and how to create and send marketing messages permissions requests.

#### Upcoming Changes

Marketing messages (also known as Recurring Notifications) on Messenger will be deprecated on February 10, 2026.

Starting September 1, 2025, marketing messages (also known as Recurring Notifications) will have the following restrictions:

1. Marketing messages (also known as Recurring Notifications) access will be limited to existing Partners and end-clients. No new integrations will be allowed.
2. The subscription\_token message sending cooldown will change from allowing one send per subscriber every 24 hours to one send every 48 hours.

  

#### Migration Suggestions

Starting July 1, 2025, Partners worldwide can integrate with the new [**Marketing Messages on Messenger API**](https://developers.facebook.com/docs/marketing-messages-on-messenger). Partners and end-clients should migrate to the new [**Marketing Messages on Messenger API**](https://developers.facebook.com/docs/marketing-messages-on-messenger) in 2025.

## Overview

Marketing Messages allows a Facebook Page or Instagram Professional Account to send messages outside the standard messaging window for people who have given you permission to do so. Marketing Messages allow you to build relationships with people who are interested in you or your business.

Marketing Messages is a new, optional premium feature that we intend to charge for in the future. We currently charge businesses to send messages from the WhatsApp Business API and listen to customer feedback to guide decisions on our pricing model. We will inform customers and partners of any changes to the free trial with ample advance notice.

### Requirements

- You must comply with all applicable [Developer Policies](https://developers.facebook.com/devpolicy) when using Marketing Messages or other Messenger Platform features
- You may only send a request for a user to opt in to Marketing Messages within the [standard messaging window](https://developers.facebook.com/docs/messenger-platform/policy/policy-overview#standard_messaging). A user’s action of opting in to Marketing Messages does not open the standard messaging window
- Your app and/or messaging experience must not receive excessive negative feedback from users. Messaging capabilities may be restricted or removed if we determine your app’s messaging experience has received excessive rates of negative feedback from users
- You must not use Marketing Messages, including opt in requests, to spam users. This includes sending duplicate opt in requests at high frequencies to the same user or users and other types of spam as defined by our [Developer Policies](https://developers.facebook.com/devpolicy)
- You must respect the limitations we have placed on the functionality of Messenger Platform and Marketing Messages in order to maintain the scope of service we are providing you

### Limitations

- You can only send one opt in request per week with the same, specific title to a person. This includes the default value of "Updates and promotions".
- Do not send duplicate opt in requests to a person. A duplicate opt in request is defined as having the same `title` for notifications from a Facebook Page or the same `title` and `image_url` for notifications from an Instagram Professional account
- You can only send in opt in requests during the standard messaging window
- If a person opts in to marketing messages, this action does not open a standard messaging window
- You can only see if a person has opted in to receiving marketing messages but not the statuses for pending opt in requests
- If a person has chosen to stop receiving marketing messages, your notifications will no longer be delivered to that person and you will receive an error
- A person can block, mute, or report your messaging
- For marketing message sent from an Instagram Professional account, generally, up to 10 opt in requests for different titles can be sent per user over a 7 day period. A sub-limit of up to 5 opt in requests may be sent to a user in a day. However, you should consider whether users are likely to find each opt-in request relevant and valuable before sending.

These requirements and limitations are subject to change as we are always striving for the best user and business experience.

### Best Practices

You should send people relevant, valuable Marketing Messages, in order to create a high-quality user experience by doing the following:

- Your opt in request, including the title and image, encompasses the types of Marketing Messages users can expect to receive, such as order updates, product recommendations, or certain offers
- When sending more than one opt in request to a user, each opt in request should clearly state the different, specific types of Marketing Messages the user can expect to receive

Marketing Messages should be relevant and tailored to [use cases](https://developers.facebook.com/docs/messenger-platform/send-messages/recurring-notifications/use-cases) that a user is likely to find valuable.

Users can provide feedback on your messaging experience, including blocking your messaging, which may result in restrictions on your use of Marketing Messages. You should regularly review your opt in requests and Marketing Messages to see if they meet the best practices above.

### Message sending cooldown

There is a **24-hour** subscription\_token message sending cooldown. This means marketing messages sent using the same subscription\_token **require** a 24-hour interval between sends.

Starting September 1, 2025, the subscription\_token message sending cooldown will change from allowing one send per subscriber every 24 hours to one send every 48 hours.

*Applies to notification message tokens created before February 2, 2023.*

- After a person opts in, you can send the person messages on a **daily**, **weekly**, or **monthly** cadence depending on which cadence the person selected during opt in.

## Request Permission to Send Marketing Messages

A person must give permission, **opt in**, to receive marketing messages from your Facebook Page or Instagram Professional account. The Messenger Platform offers multiple ways for you to get opt in. You can build opt in requests into the following messaging experiences:

- [Ads That Click to Messenger](https://developers.facebook.com/docs/messenger-platform/discovery/ctm-ads) – when a person clicks your ad
- [Checkbox Plugin](https://developers.facebook.com/docs/messenger-platform/discovery/checkbox-plugin) – when a person clicks the checkbox in a from and submits the form
- [`m.me` Links](https://developers.facebook.com/docs/messenger-platform/discovery/m-me-links) – when a person clicks your `m.me` link on your website, emails, social media posts, and more
- [Private Replies](https://developers.facebook.com/docs/messenger-platform/discovery/private-replies) – when a person publishes a visitor post or comment to your business' Facebook Page
- [QR Codes](https://developers.facebook.com/docs/messenger-platform/discovery/m-me-links#qr-codes) – when a person scans your QR Code on digital and print surfaces (supported by `m.me` Links)
- [Send to Messenger Plugin](https://developers.facebook.com/docs/messenger-platform/discovery/send-to-messenger-plugin) – when a person inititates a conversation using a list of predefined CTA buttons or text

### Sample Opt In Request

To send a marketing message opt in request, send a `POST` request to the `/PAGE-ID/messages` endpoint with the message template type set to `notification_messages`. The Page ID is the ID for your Facebook Page or the Facebook Page linked to your Instagram Professional account.

**Note:** The `title` parameter is required for marketing messages that contain a carousel from your
[Facebook Page](https://developers.facebook.com/docs/messenger-platform/send-messages/template/product#carousel)
or
[Instagram Professional account](https://developers.facebook.com/docs/messenger-platform/instagram/features/product-template/#carousel).

```
curl -X POST -H "Content-Type: application/json" -d '{
  "recipient":{
    "id":"PSID-OR-IGSID"
  },
  "message":{
    "attachment":{
      "type":"template", 
      "payload":{
         "template_type":"notification_messages", 
         "notification_messages_timezone": "UTC",
         "title":"TITLE",
         "image_url":"IMAGE-URL",
         "payload": "ADDITIONAL-WEBHOOK-INFORMATION",
      }
    }
  }
}' "https://graph.facebook.com/LATEST-API-VERSION/PAGE-ID/messages?access_token=PAGE-ACCESS-TOKEN"
```

On success, your app receives the following JSON response which includes a IDs for the recipient and the message.

```
{ 
        "recipient": {
          "id":"PSID-OR-IGSID",
          "message_id":"MESSAGE-ID",
}
```

#### Message Attachment Object Reference

A `message` `attachment` JSON object must be included in the `POST` request to the `/PAGE-ID/messages` endpoint for a marketing message opt in request.

Property | Description || `type` *enum { `template` }* | **Required.** Value must be `template` |
| `payload` *object* | Contents of the marketing message including template type, title, message frequency, message options and more, for this marketing message opt in request |
| `elements` *array* | **Required for carousel.** An array containing element objects that describe the opt in. Each element object must contain `payload` and `notification_messages_frequency`, and can include a custom `title`, `image_url`, and `notification_messages_reoptin`. A minimum of 1 and a maximum of 5 elements is supported. |
| `image_aspect_ratio` *enum { `HORIZONTAL`, `SQUARE` }* | Aspect ratio for the image.   - `SQUARE` – render square image (1:1). Image will be cropped if needed - `HORIZONTAL` – render horizontal image (1.91:1). Image will be cropped if needed |
| `image_url` *string* | The URL for the image to display in the template |
| ~~`notification_messages_frequency`~~ *enum { `DAILY, WEEKLY, MONTHLY` }* | **Deprecated for tokens created after February 2, 2023. Defaults to DAILY.** Message frequency for this marketing message opt in request.   - **DAILY** – Opt in to receive one notification per 24 hour period - **WEEKLY** – Opt in to receive one notification per 7 day period - **MONTHLY**  – Opt in to receive one notification per 1 month period |
| `notification_messages_cta_text` *enum { `ALLOW, GET, GET_UPDATES, OPT_IN, SIGN_UP` }* | Text that appears on call to action button   - **ALLOW** – set optin message button text to “Allow messages” - **GET**  – set optin message button text to “Get messages” - **GET\_UPDATES**  – set optin message button text to “Get updates”, this is also default if notification\_messages\_cta\_text is not set - **OPT\_IN** – set optin message button text to “Opt in to messages” - **SIGN\_UP**  – set optin message button text to “Sign up for messages” |
| `notification_messages_timezone` *string* | Timezone for the person receiving the message |
| `payload` *string* | **Required.** The type of marketing message, such as promotional messaging or product release messaging, for this marketing message opt in request |
| `template_type` *enum { `notification_messages` }* | **Required.** Value must be `notification_messages` |
| `title` *string* | The title to display in the template, can not exceed 65 characters. If no value is assigned, the value defaults to "Updates and promotions" |

## Notification Message Tokens

When a person opts in, your business will receive a `messaging_optin` webhooks notification with a **notification message token** and information such as message title and timezone of the person who opted in. The notification message token allows you to send marketing messages to the person.

### Opt In Webhook Notification

```
{
  "sender": {
    "id": "PSID",
  },
  "recipient": {
    "id": "PAGE-ID",
  },
  "timestamp": "TIMESTAMP",
  "optin": {
    "type": "notification_messages", 
      "payload": "ADDITIONAL-WEBHOOK-INFORMATION",
      "notification_messages_token": "NOTIFICATION-MESSAGES-TOKEN", 
      "notification_messages_timezone": "TIMEZONE-ID",
      "token_expiry_timestamp": "TIMESTAMP",
      "user_token_status": "TOKEN-STATUS"  
      "notification_messages_status": "MESSAGE-STATUS", 
      "title": "TITLE-FOR-THE-NOTIFICATION"
    }
}
```

**The following content only applies to notification message tokens with a weekly or monthly frequency created before February 2, 2023.**

Notification message tokens are generated per recurring frequency. For example, if a person has opted in to both daily and weekly marketing messages, two separate notification message tokens are generated. If the user opted-in to daily, weekly, and monthly Marketing Messages, then three separate notification message tokens will be generated.

marketing message Frequency | Description || Weekly | You can only send one message once every calendar week. A week is defined as from Monday at 12:00am until Sunday at 11:59pm in the time zone set by the Page. |
| Monthly | You can only send one message once every calendar month. A month is defined as from the first day of the month at 12:00am until the last day of the month at 11:59pm in the time zone set by the Page. |

Token expiration dates will be extended for people who choose to stay opted in to receiving marketing messages. People can opt out at any time.

### Opt In Followup Messages

Once a person has opted in to receiving marketing messages, you can send up to three followup messages. These messages must be sent within two minutes of the first followup message. The second and third followup messages can not exceed 250 characters. These followup messages can be sent outside the standard 24 hour messaging window.

To send a followup message, send a `POST` request to the `/PAGE-ID/messages` endpoint with the `recipient` object containing the notification message token and `message` object containing the text of the followup messages. The syntax for the API requests for all three followup message is the same.

#### Sample Request

*Formatted for readability.*

```
curl -X POST -H "Content-Type: application/json" -d 
    '{ 
        "recipient":{ 
            "notification_messages_token":"NOTIFICATION-MESSAGE-TOKEN" 
        }, 
        "message":{ 
            "text":FOLLOWUP-MESSAGE-TEXT-HERE, 
        } 
    }' 
"https://graph.facebook.com/LATEST-API-VERSION/PAGE-ID/messages?access_token=TOKEN"
```

### Get a List of Tokens

To get a list of all valid notification message tokens send a `GET` request to the `/PAGE-ID/notification_message_tokens` endpoint.

#### Sample Request

*Formatted for readability.*

```
curl -i -X GET "https://graph.facebook.com/API-VERSION-NUMBER/PAGE-ID/notification_message_tokens
    ?access_token=PAGE-ACCESS-TOKEN"
```

A list of up to 25 tokens is returned by default and are ordered by updated time. To read more you can add the `limit` parameter. Currently, there is a limit of 100 tokens that can be returned. You can use the `after` parameter for pagination however the `before` parameter is not available.

On success, your app will receive the following JSON response including the token, the recepient ID either an Instagram-scoped ID or Page-scoped ID, the time when the token was created, the title for the notification, and the time at which you can send the next marketing message to that recipient.

```
{
  "data":[
    {
      "notification_messages_token":"NOTIFICATION-MESSAGE-TOKEN-ID-1",
      "recipient_id":"PAGE-OR-INSTAGRAM-SCOPED-ID-1",
      "notification_messages_reoptin":"RE-OPT-IN-STATUS",
      "creation_timestamp":TIMESTAMP,
      "token_expiry_timestamp":UNIX-TIMESTAMP-EXPIRATION-DATE,
      "user_token_status":"TOKEN-STATUS",
      "topic_title":"NOTIFICATION-TITLE",
      "notification_messages_timezone":"TIMEZONE-ID",
      "next_eligible_time": TIMESTAMP
    },
...
    {
      "notification_messages_token":"NOTIFICATION-MESSAGE-TOKEN-ID-25",
      "recipient_id":"PAGE-OR-INSTAGRAM-SCOPED-ID-25",
      "notification_messages_reoptin":"RE-OPT-IN-STATUS",
      "creation_timestamp":TIMESTAMP,
      "token_expiry_timestamp":UNIX-TIMESTAMP-EXPIRATION-DATE,
      "user_token_status":"TOKEN-STATUS",
      "topic_title":"NOTIFICATION-TITLE",
      "notification_messages_timezone":"TIMEZONE-ID",
      "next_eligible_time": TIMESTAMP
    }
  ],
  "paging":{"cursors":{"before":"QVFIU...","after":"QVFIU..."},"next":"https:\/\/graph.facebook.com\/LATEST-API-VERSION\/PAGE-ID\/notification_message_tokens?access_token=PAGE-ACCESS-TOKEN"}
}
```

### Get Token Information

While we recommend using the `messaging_optin` webhook to gather marketing message information, you can send a `GET` request to the token endpoint where your token is appended to `notification_messages_`, `notification_messages_NOTIFICATION-MESSAGES-TOKEN`, to get token information.

#### Sample Request

*Formatted for readability.*

```
curl -i -X GET "https://graph.facebook.com/LATEST-API-VERSION/notification_messages_NOTIFICATION-MESSAGES-TOKEN
    ?access_token=PAGE-ACCESS-TOKEN"
```

On success, your app will receive the following JSON response which includes the notification messages token, the ID for the person receiving the message, and other token information. You will use the notification messages token and recipient's ID send marketing messages.

```
{
  "notification_messages_token": "NOTIFICATION-MESSAGES-TOKEN",
  "recipient_id": "PAGE-OR-INSTAGRAM-SCOPED-ID",
  "creation_timestamp": "TIMESTAMP",
  "token_expiry_timestamp": "TIMESTAMP",
  "user_token_status": "REFRESHED",
  "notification_messages_reoptin": "ENABLED",
  "notification_messages_timezone": "TIMEZONE-ID"
  "next_eligible_time": TIMESTAMP
}
```

These API calls will count against your app's rate limit.

## Send a marketing message

### Before You Start

You will need:

- The notification message token of the person who has opted in to receiving notifications
- The ID for your business' Facebook Page
- A Page access token requested from a person who can perform the `MESSAGING` task on the Page
- The `pages_messaging` permission, using Facebook Login
- Any assets to include in the marketing message
- The `messaging_referrals` webhook subscription for your app

To send a marketing message, send a `POST` request to the `/PAGE-ID/messages` endpoint with the recipient `NOTIFICATION-MESSAGES-TOKEN` value and message information in the message attachment.

### Limitations

- You can **only send one message per day per notification message token**. If you are sending multiple messages be sure to delay subsequent messages by 24 hours or you will receive an [error](https://developers.facebook.com/docs/messenger-platform/error-codes#error-codes-for-recurring-notifications). (Does not apply to [Opt In Followup messages](#opt-in-followup-messages).)

### Recommendations

- We strongly recommend referring to a recipient's timezone when sending marketing messages to ensure messages are recieved at an appropriate time for the recipient.

#### Sample Request

```
curl -X POST -H "Content-Type: application/json" -d '{
  "recipient":{
    "notification_messages_token": "NOTIFICATION-MESSAGES-TOKEN"
  },
  "message":{
    "attachment":{
      "type":"template",
      "payload":{
        "template_type":"generic",
        "elements":[
           {
            "title":"Welcome!",
            "image_url":"https://raw.githubusercontent.com/fbsamples/original-coast-clothing/main/public/styles/male-work.jpg",
            "subtitle":"We have the right hat for everyone.",
            "default_action": {
              "type": "web_url",
              "url": "https://www.originalcoastclothing.com/",
              "webview_height_ratio": "tall"
            },
            "buttons":[
              {
                "type":"web_url",
                "url":"https://www.originalcoastclothing.com/",
                "title":"View Website"
              },{
                "type":"postback",
                "title":"Start Chatting",
                "payload":"ADDITIONAL-WEBHOOK-INFORMATION"
              }              
            ]      
          }
        ]
      }
    }
  }
}' "https://graph.facebook.com/LATEST-API-VERSION/PAGE-ID/messages?access_token=PAGE-ACCESS-TOKEN"
```

Upon success your app will receive the following response:

```
{ 
  "recipient": "PAGE-OR-INSTAGRAM-SCOPED-ID",
  "message_id": "MESSAGE-ID"      
}
```

## Test Marketing Messages

You can test your marketing messages at any time.

### Before You Start

You will need:

- A person, the **tester**, to receive the notification. This person must have a role on the app.

### Test Opt Ins

You can test your marketing messages at any time by following these steps.

- **Step 1.** Send your tester a message with a marketing message opt in template.
- **Step 2.** Make sure the tester clicks the opt in button, such as **Receive 50% off sales messages**, in the conversation.
- **Step 3.** Send the first marketing message to your tester
- **Step 4.** Send another marketing message immediately after the first with the `developer_action` parameter set to `ENABLE_FOLLOWUP_MESSAGE`.
- **Step 5.** Send another marketing message to the tester, this is your test message.

#### Sample Request

*Formatted for readability.*

```
curl -X POST "https://graph.facebook.com/LATEST-API-VERSION/PAGE-ID/notification_messages_dev_support
    ?recipient={
        "notification_messages_token": "NOTIFICATION-MESSAGES-TOKEN"
    }
    &developer_action=ENABLE_FOLLOWUP_MESSAGE
    &access_token=PAGE-ACCESS-TOKEN"
```

On success, your app will receive the following JSON response containing `success` set to `true`.

```
{ "success": true }
```

To test re-opt ins, repeat the steps with the `developer_action` parameter set to `SEND_RE_OPTIN` in Step 4.

## Next Steps

- [Messaging Opt In Webhooks Notification](https://developers.facebook.com/docs/messenger-platform/reference/webhook-events/messaging_optins/)
- Visit the
  [Message Types overview](https://developers.facebook.com/docs/messenger-platform/reference/send-api) to learn about the different types of messages you can send.

## See Also

- The
  [Page Messages Reference](https://developers.facebook.com/docs/graph-api/reference/page/messages/) for more information on available fields for recurring messages.
- [A list of available Time Zones](https://scontent-ord5-2.xx.fbcdn.net/v/t39.8562-6/280309067_562342355463455_3557336671492726983_n.pdf)
- [Error Codes for Messenger Platform](https://developers.facebook.com/docs/messenger-platform/error-codes)

### Developer Support

- Use the [Meta Status tool](https://metastatus.com/) to check for the status and outages of Meta business products.
- Use the [Meta Developer Support tool](/support) to report bugs and view reported bugs, get help with Ads or Business Manager, and more.
