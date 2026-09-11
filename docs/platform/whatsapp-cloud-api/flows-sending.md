---
title: "Flows: sending a flow"
source: "https://developers.facebook.com/docs/whatsapp/flows/guides/sendingaflow/"
final_url: "https://developers.facebook.com/documentation/business-messaging/whatsapp/flows/guides/sendingaflow"
platform: "whatsapp-cloud-api"
fetched_at: "2026-09-11T09:20:10Z"
last_checked_at: "2026-09-11T10:13:18Z"
previous_fetched_at: ""
http_status: "200"
format: "markdown-served"
sha256: "e2d37c0b536973cc934cc481f227096febe93f209920b41116f9736f24d248d6"
---

# Sending a Flow




This guide describes the ways to send a Flow to users.

## Prerequisites
You will need to [verify your business](https://developers.facebook.com/docs/development/release/business-verification) and maintain a [high message quality](https://developers.facebook.com/documentation/business-messaging/whatsapp/messages/send-messages#message-quality).

## Postman collection &#123;#postman&#125;

All the API requests mentioned below are documented in the [Flows API postman collection](https://www.postman.com/meta/workspace/whatsapp-business-platform/documentation/24926895-7bf51205-92ed-49d1-af4a-0130cf84b6f6) which you can use to make API requests and generate code in different languages.

## Business initiated messages &#123;#templatemessages&#125;

To send a business initiated message with a Flow, you can create and send a [message template](https://developers.facebook.com/documentation/business-messaging/whatsapp/templates/overview) with a WhatsApp Flow attached to it. A new button type called FLOW is available. Use this type to specify the Flow to be sent with the message template.

To send a Flow message template you need to:

1. Create a message template with a Flow
2. Send a message template with a Flow

### Create a message template with a Flow

You can quickly build a Flow in the [playground](https://developers.facebook.com/documentation/business-messaging/whatsapp/flows/playground) and pass the Flow JSON in the message template creation request. Or you can specify the ID or name of an already published Flow.

Below is an example request to create a message template with a Flow, [see this page for full reference](https://developers.facebook.com/documentation/business-messaging/whatsapp/reference/whatsapp-business-account/message-template-api#post-version-waba-id-message-templates):

#### Sample request

#### Sample request

Message templates can be created and sent in [these languages](https://developers.facebook.com/documentation/business-messaging/whatsapp/templates/supported-languages).

#### Sample Response

```curl
&#123;
  &quot;id&quot;: &quot;&lt;TEMPLATE_ID&gt;&quot;,
  &quot;status&quot;: &quot;PENDING&quot;,
  &quot;category&quot;: &quot;MARKETING&quot;
&#125;
```

#### Sample response

```curl
&#123;
  &quot;id&quot;: &quot;&lt;template-id&gt;&quot;,
  &quot;status&quot;: &quot;PENDING&quot;,
  &quot;category&quot;: &quot;MARKETING&quot;
&#125;
```

### Send template with flow
**Note:** Ensure that your template passes all required reviews so that `status` is `APPROVED` instead of `PENDING`.

Now you can send a message template with a Flow using the request below
#### Sample request

```curl
curl -X  POST \
 &#039;https://graph.facebook.com/v16.0/FROM_PHONE_NUMBER_ID/messages&#039; \
 -H &#039;Authorization: Bearer ACCESS_TOKEN&#039; \
 -H &#039;Content-Type: application/json&#039; \
 -d &#039;&#123;
  &quot;messaging_product&quot;: &quot;whatsapp&quot;,
  &quot;recipient_type&quot;: &quot;individual&quot;,
  &quot;to&quot;: &quot;PHONE_NUMBER&quot;,
  &quot;type&quot;: &quot;template&quot;,
  &quot;template&quot;: &#123;
    &quot;name&quot;: &quot;TEMPLATE_NAME&quot;,
    &quot;language&quot;: &#123;
      &quot;code&quot;: &quot;LANGUAGE_AND_LOCALE_CODE&quot;
    &#125;,
    &quot;components&quot;: [
      &#123;
        &quot;type&quot;: &quot;button&quot;,
        &quot;sub_type&quot;: &quot;flow&quot;,
        &quot;index&quot;: &quot;0&quot;,
        &quot;parameters&quot;: [
          &#123;
            &quot;type&quot;: &quot;action&quot;,
            &quot;action&quot;: &#123;
              &quot;flow_token&quot;: &quot;FLOW_TOKEN&quot;,   //optional, default is &quot;unused&quot;
              &quot;flow_action_data&quot;: &#123;
                 ...
              &#125;   // optional, json object with the data payload for the first screen
            &#125;
          &#125;
        ]
      &#125;
    ]
  &#125;
&#125;&#039;
```

####  Sample response

```curl
&#123;
  &quot;messaging_product&quot;: &quot;whatsapp&quot;,
  &quot;contacts&quot;: [
    &#123;
      &quot;input&quot;: &quot;&lt;phone-number&gt;&quot;,
      &quot;wa_id&quot;: &quot;&lt;phone-number&gt;&quot;
    &#125;
  ],
  &quot;messages&quot;: [
    &#123;
      &quot;id&quot;: &quot;&lt;message-id&gt;&quot;
    &#125;
  ]
&#125;
```

## User-initiated conversations &#123;#userinitiated&#125;

After you create a Flow, you can send it. You can send a Message with a Flow in a user-initiated conversation using a Message with a Call To Action (CTA). You send this message through the Cloud API with information specific to the Flow. Tapping the CTA button triggers the Flow.

**Warning:** Read more about [message types, limits, and timing](https://developers.facebook.com/documentation/business-messaging/whatsapp/messages/send-messages).

As mentioned earlier, a message with a Flow is not much different from other types of messages. A Flow message uses the existing APIs, which are described on the following pages:

* [Cloud API Interactive Messages](https://developers.facebook.com/documentation/business-messaging/whatsapp/reference/whatsapp-business-phone-number/message-api#interactive-object) documentation page describes how to send Interactive Messages with the Cloud API.

To send a message with a Flow, you can use a new type of the Interactive Object named `flow` with the following properties.

### Interactive message parameters &#123;#interactive-parameters&#125;

| Property | Type | Description |
| --- | --- | --- |
| `interactive.type` | String | Value must be `flow` |
| `interactive.action.name` | String | Value must be `flow` |
| `interactive.action.parameters.flow_message_version` | String | Value must be `3`. |
| `interactive.action.parameters.flow_id` | String | Unique ID of the Flow provided by WhatsApp.&lt;br&gt;&lt;br&gt;Cannot be used with the `flow_name` parameter. Only one of these parameters is required. |
| `interactive.action.parameters.flow_name` | String | The name of the Flow that you created. Changing the Flow name will require updating this parameter to match the new name.&lt;br&gt;&lt;br&gt;Cannot be used with the `flow_id` parameter. Only one of these parameters is required. |
| `interactive.action.parameters.flow_cta` | String | Text on the CTA button. For example: &quot;Signup&quot;&lt;br&gt;&lt;br&gt;CTA text length is advised to be 30 characters or less (no emoji). |
| `interactive.action.parameters.mode` | String | The Flow can be in either `draft` or `published` mode. `published` is the default value for this field. |
| `interactive.action.parameters.flow_token` | String | Flow token that is generated by the business to serve as an identifier. |
| `interactive.action.parameters.flow_action` | String | `navigate` or `data_exchange`. Default value is `navigate` |
| `interactive.action.parameters.flow_action_payload` | String |  |
| `interactive.action.parameters.flow_action_payload.screen` | String | The `id` of the first screen. |
| `interactive.action.parameters.flow_action_payload.data` | String | Optional. The input data for the first screen of the Flow. Must be a non-empty object. |

*In case you edited published flow and now it is in the draft state, use &quot;mode=draft&quot; to send the current draft flow version, or &quot;mode=published&quot; (default value) to send the last published flow version.

**See Flow JSON reference for [entry screen](https://developers.facebook.com/documentation/business-messaging/whatsapp/flows/guides/flowjson#routing-rules) details.**

**Cloud API Sample Request (with all parameters)**

```curl
curl -X  POST \
 &#039;https://graph.facebook.com/v18.0/FROM_PHONE_NUMBER/messages&#039; \
 -H &#039;Authorization: Bearer ACCESS_TOKEN&#039; \
 -H &#039;Content-Type: application/json&#039; \
 -d &#039;&#123;
  &quot;recipient_type&quot;: &quot;individual&quot;,
  &quot;messaging_product&quot;: &quot;whatsapp&quot;,
  &quot;to&quot;: &quot;whatsapp-id&quot;,
  &quot;type&quot;: &quot;interactive&quot;,
  &quot;interactive&quot;: &#123;
    &quot;type&quot;: &quot;flow&quot;,
    &quot;header&quot;: &#123;
      &quot;type&quot;: &quot;text&quot;,
      &quot;text&quot;: &quot;Flow message header&quot;
    &#125;,
    &quot;body&quot;: &#123;
      &quot;text&quot;: &quot;Flow message body&quot;
    &#125;,
    &quot;footer&quot;: &#123;
      &quot;text&quot;: &quot;Flow message footer&quot;
    &#125;,
    &quot;action&quot;: &#123;
      &quot;name&quot;: &quot;flow&quot;,
      &quot;parameters&quot;: &#123;
        &quot;flow_message_version&quot;: &quot;3&quot;,
        &quot;flow_token&quot;: &quot;AQAAAAACS5FpgQ_cAAAAAD0QI3s.&quot;,

        &quot;flow_name&quot;: &quot;appointment_booking_v1&quot;,
        //or
        &quot;flow_id&quot;: &quot;123456&quot;,

        &quot;flow_cta&quot;: &quot;Book!&quot;,
        &quot;flow_action&quot;: &quot;navigate&quot;,
        &quot;flow_action_payload&quot;: &#123;
          &quot;screen&quot;: &quot;&lt;SCREEN_NAME&gt;&quot;,
          &quot;data&quot;: &quot;&#123;\&quot;product_name\&quot;:\&quot;name\&quot;,\&quot;product_description\&quot;:\&quot;description\&quot;,\&quot;product_price\&quot;:100&#125;&quot;
        &#125;
      &#125;
    &#125;
  &#125;
&#125;&#039;
```

**Sample Response**

```json
&#123;
  &quot;contacts&quot;: [
    &#123;
      &quot;Input&quot;: &quot;+447385946746&quot;,
      &quot;wa_id&quot;: &quot;47385946746&quot;
    &#125;
  ],
  &quot;messages&quot;: [
    &#123;
      &quot;id&quot;: &quot;gHTRETHRTHTRTH-av4Y&quot;
    &#125;
  ],
  &quot;meta&quot;: &#123;
    &quot;api_status&quot;: &quot;stable&quot;,
    &quot;version&quot;: &quot;2.44.0.27&quot;
  &#125;
&#125;
```
