---
title: "Message Template API reference (create, list, delete)"
source: "https://developers.facebook.com/documentation/business-messaging/whatsapp/reference/whatsapp-business-account/message-template-api"
final_url: "https://developers.facebook.com/documentation/business-messaging/whatsapp/reference/whatsapp-business-account/message-template-api"
platform: "whatsapp-cloud-api"
fetched_at: "2026-09-11T10:07:06Z"
last_checked_at: "2026-09-11T10:13:18Z"
previous_fetched_at: ""
http_status: "200"
format: "markdown-served"
sha256: "85a5d8ded696ed9e583c6ec79e160fa31ac1d1c0809b1b69762a85673c6834ac"
---

## Base URL

| URL | Description |
|-----|-------------|
| https://graph.facebook.com | Production Graph API server |

## APIs

| Method | Endpoint |
|--------|----------|
| DELETE | [/&#123;Version&#125;/&#123;WABA-ID&#125;/message_templates](#delete-version-waba-id-message-templates) |
| GET | [/&#123;Version&#125;/&#123;TEMPLATE_ID&#125;](#get-version-template-id) |
| GET | [/&#123;Version&#125;/&#123;WABA-ID&#125;/message_templates](#get-version-waba-id-message-templates) |
| POST | [/&#123;Version&#125;/&#123;TEMPLATE_ID&#125;](#post-version-template-id) |
| POST | [/&#123;Version&#125;/&#123;WABA-ID&#125;/message_templates](#post-version-waba-id-message-templates) |

&lt;jumplink id=&quot;delete-version-waba-id-message-templates&quot;&gt;&lt;/jumplink&gt;
## DELETE /&#123;Version&#125;/&#123;WABA-ID&#125;/message_templates

Delete Message Templates

Delete message templates from a WhatsApp Business Account. Can delete by name
(all languages), by specific template ID, or by multiple template IDs.


### Header Parameters

| Name | Type | Required | Description |
|------|------|----------|-------------|
| User-Agent | string |  | The user agent string identifying the client software making the request. |
| Authorization | string | ✓ | Bearer token for API authentication. This should be a valid access token obtained through the appropriate OAuth flow or system user token. |

### Path Parameters

| Name | Type | Required | Description |
|------|------|----------|-------------|
| Version | string | ✓ | Graph API version |
| WABA-ID | string | ✓ | WhatsApp Business Account ID |

### Query Parameters

| Name | Type | Required | Description |
|------|------|----------|-------------|
| name | string |  | Template name to delete (deletes all languages if hsm_id not specified) |
| hsm_id | string |  | Specific template ID to delete (used with name for single-language deletion) |
| hsm_ids | string |  | JSON array of template IDs to delete (max 100) |

### Responses

**200**

Templates deleted successfully

**Content Type**: `application/json`

**Schema**: [SuccessResponse](#successresponse)

**Example**:\n```json\n&#123;
    &quot;success&quot;: true
&#125;\n```

**400**

Bad Request

**Content Type**: `application/json`

**Schema**: [GraphAPIError](#graphapierror)

**Example**:\n```json\n&#123;
    &quot;error&quot;: &#123;
        &quot;message&quot;: &quot;Invalid parameter&quot;,
        &quot;type&quot;: &quot;OAuthException&quot;,
        &quot;code&quot;: 100,
        &quot;fbtrace_id&quot;: &quot;AXsgnV2Cm3ZMGF3dF_cfYIn&quot;
    &#125;
&#125;\n```

**401**

Unauthorized

**Content Type**: `application/json`

**Schema**: [GraphAPIError](#graphapierror)

**Example**:\n```json\n&#123;
    &quot;error&quot;: &#123;
        &quot;message&quot;: &quot;Invalid OAuth access token&quot;,
        &quot;type&quot;: &quot;OAuthException&quot;,
        &quot;code&quot;: 190,
        &quot;fbtrace_id&quot;: &quot;AXsgnV2Cm3ZMGF3dF_cfYIn&quot;
    &#125;
&#125;\n```

**500**

Internal Server Error

**Content Type**: `application/json`

**Schema**: [GraphAPIError](#graphapierror)

**Example**:\n```json\n&#123;
    &quot;error&quot;: &#123;
        &quot;message&quot;: &quot;An unexpected error occurred&quot;,
        &quot;type&quot;: &quot;GraphMethodException&quot;,
        &quot;code&quot;: 2,
        &quot;fbtrace_id&quot;: &quot;AXsgnV2Cm3ZMGF3dF_cfYIn&quot;,
        &quot;is_transient&quot;: true
    &#125;
&#125;\n```


&lt;jumplink id=&quot;get-version-template-id&quot;&gt;&lt;/jumplink&gt;
## GET /&#123;Version&#125;/&#123;TEMPLATE_ID&#125;

Get Message Template by ID

Retrieve a specific message template by its ID with all available fields.


### Header Parameters

| Name | Type | Required | Description |
|------|------|----------|-------------|
| User-Agent | string |  | The user agent string identifying the client software making the request. |
| Authorization | string | ✓ | Bearer token for API authentication. This should be a valid access token obtained through the appropriate OAuth flow or system user token. |

### Path Parameters

| Name | Type | Required | Description |
|------|------|----------|-------------|
| Version | string | ✓ | Graph API version |
| TEMPLATE_ID | string | ✓ | Message template ID |

### Query Parameters

| Name | Type | Required | Description |
|------|------|----------|-------------|
| fields | string |  | Comma-separated list of fields to include in the response. Available fields: id, ad_account_id, ad_adset_id, ad_campaign_id, ad_id, bid_spec, category, components, correct_category, cta_url_link_tracking_opted_out, degrees_of_freedom_spec, display_format, health_status, is_primary_device_delivery_only, is_sms_fallback_enabled, language, last_updated_time, library_template_name, message_send_ttl_seconds, name, parameter_format, previous_category, quality_score, rejected_reason, source, status, sub_category |

### Responses

**200**

Successfully retrieved message template

**Content Type**: `application/json`

**Schema**: [MessageTemplate](#messagetemplate)

**400**

Bad Request

**Content Type**: `application/json`

**Schema**: [GraphAPIError](#graphapierror)

**Example**:\n```json\n&#123;
    &quot;error&quot;: &#123;
        &quot;message&quot;: &quot;Invalid parameter&quot;,
        &quot;type&quot;: &quot;OAuthException&quot;,
        &quot;code&quot;: 100,
        &quot;fbtrace_id&quot;: &quot;AXsgnV2Cm3ZMGF3dF_cfYIn&quot;
    &#125;
&#125;\n```

**401**

Unauthorized

**Content Type**: `application/json`

**Schema**: [GraphAPIError](#graphapierror)

**Example**:\n```json\n&#123;
    &quot;error&quot;: &#123;
        &quot;message&quot;: &quot;Invalid OAuth access token&quot;,
        &quot;type&quot;: &quot;OAuthException&quot;,
        &quot;code&quot;: 190,
        &quot;fbtrace_id&quot;: &quot;AXsgnV2Cm3ZMGF3dF_cfYIn&quot;
    &#125;
&#125;\n```

**404**

Not Found

**Content Type**: `application/json`

**Schema**: [GraphAPIError](#graphapierror)

**Example**:\n```json\n&#123;
    &quot;error&quot;: &#123;
        &quot;message&quot;: &quot;Template not found&quot;,
        &quot;type&quot;: &quot;GraphMethodException&quot;,
        &quot;code&quot;: 803,
        &quot;fbtrace_id&quot;: &quot;AXsgnV2Cm3ZMGF3dF_cfYIn&quot;
    &#125;
&#125;\n```

**500**

Internal Server Error

**Content Type**: `application/json`

**Schema**: [GraphAPIError](#graphapierror)

**Example**:\n```json\n&#123;
    &quot;error&quot;: &#123;
        &quot;message&quot;: &quot;An unexpected error occurred&quot;,
        &quot;type&quot;: &quot;GraphMethodException&quot;,
        &quot;code&quot;: 2,
        &quot;fbtrace_id&quot;: &quot;AXsgnV2Cm3ZMGF3dF_cfYIn&quot;,
        &quot;is_transient&quot;: true
    &#125;
&#125;\n```


&lt;jumplink id=&quot;get-version-waba-id-message-templates&quot;&gt;&lt;/jumplink&gt;
## GET /&#123;Version&#125;/&#123;WABA-ID&#125;/message_templates

List Message Templates

Retrieve message templates for a WhatsApp Business Account. Returns paginated
results with template details including status, category, components, and quality scores.


### Header Parameters

| Name | Type | Required | Description |
|------|------|----------|-------------|
| User-Agent | string |  | The user agent string identifying the client software making the request. |
| Authorization | string | ✓ | Bearer token for API authentication. This should be a valid access token obtained through the appropriate OAuth flow or system user token. |

### Path Parameters

| Name | Type | Required | Description |
|------|------|----------|-------------|
| Version | string | ✓ | Graph API version |
| WABA-ID | string | ✓ | WhatsApp Business Account ID |

### Query Parameters

| Name | Type | Required | Description |
|------|------|----------|-------------|
| fields | string |  | Comma-separated list of fields to include in the response. Available fields: id, ad_account_id, ad_adset_id, ad_campaign_id, ad_id, bid_spec, category, components, correct_category, cta_url_link_tracking_opted_out, degrees_of_freedom_spec, display_format, health_status, is_primary_device_delivery_only, is_sms_fallback_enabled, language, last_updated_time, library_template_name, message_send_ttl_seconds, name, parameter_format, previous_category, quality_score, rejected_reason, source, status, sub_category |
| limit | integer [min: 1] |  | Maximum number of templates to return per page |
| after | string |  | Cursor for next page of results |
| before | string |  | Cursor for previous page of results |

### Responses

**200**

Successfully retrieved message templates

**Content Type**: `application/json`

**Schema**: [MessageTemplatesResponse](#messagetemplatesresponse)

**400**

Bad Request

**Content Type**: `application/json`

**Schema**: [GraphAPIError](#graphapierror)

**Example**:\n```json\n&#123;
    &quot;error&quot;: &#123;
        &quot;message&quot;: &quot;Invalid parameter&quot;,
        &quot;type&quot;: &quot;OAuthException&quot;,
        &quot;code&quot;: 100,
        &quot;fbtrace_id&quot;: &quot;AXsgnV2Cm3ZMGF3dF_cfYIn&quot;
    &#125;
&#125;\n```

**401**

Unauthorized

**Content Type**: `application/json`

**Schema**: [GraphAPIError](#graphapierror)

**Example**:\n```json\n&#123;
    &quot;error&quot;: &#123;
        &quot;message&quot;: &quot;Invalid OAuth access token&quot;,
        &quot;type&quot;: &quot;OAuthException&quot;,
        &quot;code&quot;: 190,
        &quot;fbtrace_id&quot;: &quot;AXsgnV2Cm3ZMGF3dF_cfYIn&quot;
    &#125;
&#125;\n```

**403**

Forbidden

**Content Type**: `application/json`

**Schema**: [GraphAPIError](#graphapierror)

**Example**:\n```json\n&#123;
    &quot;error&quot;: &#123;
        &quot;message&quot;: &quot;Insufficient permissions to access templates&quot;,
        &quot;type&quot;: &quot;OAuthException&quot;,
        &quot;code&quot;: 200,
        &quot;fbtrace_id&quot;: &quot;AXsgnV2Cm3ZMGF3dF_cfYIn&quot;
    &#125;
&#125;\n```

**404**

Not Found

**Content Type**: `application/json`

**Schema**: [GraphAPIError](#graphapierror)

**Example**:\n```json\n&#123;
    &quot;error&quot;: &#123;
        &quot;message&quot;: &quot;WhatsApp Business Account not found&quot;,
        &quot;type&quot;: &quot;GraphMethodException&quot;,
        &quot;code&quot;: 803,
        &quot;fbtrace_id&quot;: &quot;AXsgnV2Cm3ZMGF3dF_cfYIn&quot;
    &#125;
&#125;\n```

**500**

Internal Server Error

**Content Type**: `application/json`

**Schema**: [GraphAPIError](#graphapierror)

**Example**:\n```json\n&#123;
    &quot;error&quot;: &#123;
        &quot;message&quot;: &quot;An unexpected error occurred&quot;,
        &quot;type&quot;: &quot;GraphMethodException&quot;,
        &quot;code&quot;: 2,
        &quot;fbtrace_id&quot;: &quot;AXsgnV2Cm3ZMGF3dF_cfYIn&quot;,
        &quot;is_transient&quot;: true
    &#125;
&#125;\n```


&lt;jumplink id=&quot;post-version-template-id&quot;&gt;&lt;/jumplink&gt;
## POST /&#123;Version&#125;/&#123;TEMPLATE_ID&#125;

Edit Message Template

Update an existing message template. Only approved or rejected templates can be edited.


### Header Parameters

| Name | Type | Required | Description |
|------|------|----------|-------------|
| User-Agent | string |  | The user agent string identifying the client software making the request. |
| Authorization | string | ✓ | Bearer token for API authentication. This should be a valid access token obtained through the appropriate OAuth flow or system user token. |

### Path Parameters

| Name | Type | Required | Description |
|------|------|----------|-------------|
| Version | string | ✓ | Graph API version |
| TEMPLATE_ID | string | ✓ | Message template ID to edit |

### Request Body (Required)

**Content Type**: `application/json`

**Schema**: object

| Property | Type | Required | Description |
|----------|------|----------|-------------|
| components | array of object |  | Updated template components |
| category | [WhatsAppBusinessHSMTag](#whatsappbusinesshsmtag) |  |  |
| parameter_format | [BusinessMessagingHSMParameterFormat](#businessmessaginghsmparameterformat) |  |  |
| allow_category_change | boolean |  | Allow Meta to reassign the template category |
| cta_url_link_tracking_opted_out | boolean |  | Opt out of CTA URL link tracking |
| message_send_ttl_seconds | integer |  | Time-to-live for messages using this template |
| sub_category | [WhatsAppBusinessHSMTagSubCategory](#whatsappbusinesshsmtagsubcategory) |  |  |
| display_format | [WhatsAppBusinessMessageDisplayFormat](#whatsappbusinessmessagedisplayformat) |  |  |
| is_primary_device_delivery_only | boolean |  | Restrict to primary device delivery only |

### Responses

**200**

Template updated successfully

**Content Type**: `application/json`

**Schema**: [SuccessResponse](#successresponse)

**Example**:\n```json\n&#123;
    &quot;success&quot;: true
&#125;\n```

**400**

Bad Request

**Content Type**: `application/json`

**Schema**: [GraphAPIError](#graphapierror)

**Example**:\n```json\n&#123;
    &quot;error&quot;: &#123;
        &quot;message&quot;: &quot;Invalid parameter&quot;,
        &quot;type&quot;: &quot;OAuthException&quot;,
        &quot;code&quot;: 100,
        &quot;fbtrace_id&quot;: &quot;AXsgnV2Cm3ZMGF3dF_cfYIn&quot;
    &#125;
&#125;\n```

**401**

Unauthorized

**Content Type**: `application/json`

**Schema**: [GraphAPIError](#graphapierror)

**Example**:\n```json\n&#123;
    &quot;error&quot;: &#123;
        &quot;message&quot;: &quot;Invalid OAuth access token&quot;,
        &quot;type&quot;: &quot;OAuthException&quot;,
        &quot;code&quot;: 190,
        &quot;fbtrace_id&quot;: &quot;AXsgnV2Cm3ZMGF3dF_cfYIn&quot;
    &#125;
&#125;\n```

**500**

Internal Server Error

**Content Type**: `application/json`

**Schema**: [GraphAPIError](#graphapierror)

**Example**:\n```json\n&#123;
    &quot;error&quot;: &#123;
        &quot;message&quot;: &quot;An unexpected error occurred&quot;,
        &quot;type&quot;: &quot;GraphMethodException&quot;,
        &quot;code&quot;: 2,
        &quot;fbtrace_id&quot;: &quot;AXsgnV2Cm3ZMGF3dF_cfYIn&quot;,
        &quot;is_transient&quot;: true
    &#125;
&#125;\n```


&lt;jumplink id=&quot;post-version-waba-id-message-templates&quot;&gt;&lt;/jumplink&gt;
## POST /&#123;Version&#125;/&#123;WABA-ID&#125;/message_templates

Create Message Template

Create a new message template for a WhatsApp Business Account. Templates must be
approved before they can be used to send messages.


### Header Parameters

| Name | Type | Required | Description |
|------|------|----------|-------------|
| User-Agent | string |  | The user agent string identifying the client software making the request. |
| Authorization | string | ✓ | Bearer token for API authentication. This should be a valid access token obtained through the appropriate OAuth flow or system user token. |

### Path Parameters

| Name | Type | Required | Description |
|------|------|----------|-------------|
| Version | string | ✓ | Graph API version |
| WABA-ID | string | ✓ | WhatsApp Business Account ID |

### Request Body (Required)

**Content Type**: `application/json`

**Schema**: object

| Property | Type | Required | Description |
|----------|------|----------|-------------|
| name | string | ✓ | Template name (lowercase alphanumeric and underscores only) |
| language | string | ✓ | Template language code |
| category | [WhatsAppBusinessHSMTag](#whatsappbusinesshsmtag) | ✓ |  |
| parameter_format | [BusinessMessagingHSMParameterFormat](#businessmessaginghsmparameterformat) |  |  |
| components | array of object |  | Template components |
| allow_category_change | boolean |  | Allow Meta to reassign the template category |
| cta_url_link_tracking_opted_out | boolean |  | Opt out of CTA URL link tracking |
| message_send_ttl_seconds | integer |  | Time-to-live for messages using this template |
| sub_category | [WhatsAppBusinessHSMTagSubCategory](#whatsappbusinesshsmtagsubcategory) |  |  |
| display_format | [WhatsAppBusinessMessageDisplayFormat](#whatsappbusinessmessagedisplayformat) |  |  |
| library_template_name | string |  | Name of the library template to clone |
| library_template_button_inputs | array of object |  | Button inputs for library template cloning |
| library_template_body_inputs | object |  | Body inputs for library template cloning |
| is_primary_device_delivery_only | boolean |  | Restrict to primary device delivery only |
| send_type | [WhatsAppBusinessMarketingMessagesHSMSendType](#whatsappbusinessmarketingmessageshsmsendtype) |  |  |

### Responses

**200**

Template created successfully

**Content Type**: `application/json`

**Schema**: [CreateTemplateResponse](#createtemplateresponse)

**400**

Bad Request

**Content Type**: `application/json`

**Schema**: [GraphAPIError](#graphapierror)

**Example**:\n```json\n&#123;
    &quot;error&quot;: &#123;
        &quot;message&quot;: &quot;Invalid parameter: name must contain only lowercase alphanumeric characters and underscores&quot;,
        &quot;type&quot;: &quot;OAuthException&quot;,
        &quot;code&quot;: 100,
        &quot;fbtrace_id&quot;: &quot;AXsgnV2Cm3ZMGF3dF_cfYIn&quot;
    &#125;
&#125;\n```

**401**

Unauthorized

**Content Type**: `application/json`

**Schema**: [GraphAPIError](#graphapierror)

**Example**:\n```json\n&#123;
    &quot;error&quot;: &#123;
        &quot;message&quot;: &quot;Invalid OAuth access token&quot;,
        &quot;type&quot;: &quot;OAuthException&quot;,
        &quot;code&quot;: 190,
        &quot;fbtrace_id&quot;: &quot;AXsgnV2Cm3ZMGF3dF_cfYIn&quot;
    &#125;
&#125;\n```

**403**

Forbidden

**Content Type**: `application/json`

**Schema**: [GraphAPIError](#graphapierror)

**Example**:\n```json\n&#123;
    &quot;error&quot;: &#123;
        &quot;message&quot;: &quot;Insufficient permissions to create templates&quot;,
        &quot;type&quot;: &quot;OAuthException&quot;,
        &quot;code&quot;: 200,
        &quot;fbtrace_id&quot;: &quot;AXsgnV2Cm3ZMGF3dF_cfYIn&quot;
    &#125;
&#125;\n```

**500**

Internal Server Error

**Content Type**: `application/json`

**Schema**: [GraphAPIError](#graphapierror)

**Example**:\n```json\n&#123;
    &quot;error&quot;: &#123;
        &quot;message&quot;: &quot;An unexpected error occurred&quot;,
        &quot;type&quot;: &quot;GraphMethodException&quot;,
        &quot;code&quot;: 2,
        &quot;fbtrace_id&quot;: &quot;AXsgnV2Cm3ZMGF3dF_cfYIn&quot;,
        &quot;is_transient&quot;: true
    &#125;
&#125;\n```


# Components

## Schemas

&lt;jumplink id=&quot;messagetemplate&quot;&gt;&lt;/jumplink&gt;
### MessageTemplate

WhatsApp Business message template (HSM)

| Property | Type | Required | Description |
|----------|------|----------|-------------|
| id | string |  | Unique identifier for the message template |
| ad_account_id | string |  | Associated ad account ID for click-to-WhatsApp ad templates |
| ad_adset_id | string |  | Associated ad set ID |
| ad_campaign_id | string |  | Associated ad campaign ID |
| ad_id | string |  | Associated ad group ID |
| bid_spec | [Bid_spec](#object-bid_spec-1) |  | Bid specification for marketing message templates |
| category | [WhatsAppBusinessHSMTag](#whatsappbusinesshsmtag) |  |  |
| components | array of [Components](#object-components-4) |  | Template components (header, body, footer, buttons) |
| correct_category | [WhatsAppBusinessHSMTag](#whatsappbusinesshsmtag) |  |  |
| cta_url_link_tracking_opted_out | boolean |  | Whether CTA URL link tracking is opted out |
| degrees_of_freedom_spec | object |  | Marketing message creative degrees of freedom specification |
| display_format | [WhatsAppBusinessMessageDisplayFormat](#whatsappbusinessmessagedisplayformat) |  |  |
| health_status | [Health_status](#object-health_status-5) |  | Health status information for the template |
| is_primary_device_delivery_only | boolean |  | Whether this template is restricted to primary device delivery only |
| is_sms_fallback_enabled | boolean |  | Whether SMS fallback is enabled for this template |
| language | string |  | Language code of the template |
| last_updated_time | integer (int64) |  | Unix timestamp when the template was last updated |
| library_template_name | string |  | Name of the library template this was created from |
| message_send_ttl_seconds | integer (int64) |  | Time-to-live in seconds for messages sent using this template |
| name | string |  | Name of the template |
| parameter_format | [BusinessMessagingHSMParameterFormat](#businessmessaginghsmparameterformat) |  |  |
| previous_category | [WhatsAppBusinessHSMTag](#whatsappbusinesshsmtag) |  |  |
| quality_score | [Quality_score](#object-quality_score-6) |  | Quality score information for the template |
| rejected_reason | [WhatsAppBusinessHSMRejectionReason](#whatsappbusinesshsmrejectionreason) |  |  |
| source | [WhatsAppBusinessHSMSource](#whatsappbusinesshsmsource) |  |  |
| status | [WhatsAppBusinessHSMStatus](#whatsappbusinesshsmstatus) |  |  |
| sub_category | [WhatsAppBusinessHSMTagSubCategory](#whatsappbusinesshsmtagsubcategory) |  |  |

&lt;jumplink id=&quot;whatsappbusinesshsmtag&quot;&gt;&lt;/jumplink&gt;
### WhatsAppBusinessHSMTag

Template category

**Type**: string

**Enum Values**: &quot;AUTHENTICATION&quot;, &quot;FREE_SERVICE&quot;, &quot;MARKETING&quot;, &quot;UTILITY&quot;

&lt;jumplink id=&quot;whatsappbusinesshsmstatus&quot;&gt;&lt;/jumplink&gt;
### WhatsAppBusinessHSMStatus

Current status of the message template

**Type**: string

**Enum Values**: &quot;APPROVED&quot;, &quot;ARCHIVED&quot;, &quot;DELETED&quot;, &quot;DISABLED&quot;, &quot;IN_APPEAL&quot;, &quot;LIMIT_EXCEEDED&quot;, &quot;PAUSED&quot;, &quot;PENDING&quot;, &quot;PENDING_DELETION&quot;, &quot;REJECTED&quot;

&lt;jumplink id=&quot;whatsappbusinesshsmtagsubcategory&quot;&gt;&lt;/jumplink&gt;
### WhatsAppBusinessHSMTagSubCategory

Template sub-category for utility templates

**Type**: string

**Enum Values**: &quot;BOOKING_STATUS&quot;, &quot;CALL_PERMISSIONS_REQUEST&quot;, &quot;FLIGHT_DELAY_AND_GATE_CHANGE_ALERT&quot;, &quot;FRAUD_ALERT&quot;, &quot;ORDER_DETAILS&quot;, &quot;ORDER_STATUS&quot;, &quot;RICH_ORDER_STATUS&quot;

&lt;jumplink id=&quot;businessmessaginghsmparameterformat&quot;&gt;&lt;/jumplink&gt;
### BusinessMessagingHSMParameterFormat

Parameter format for the template

**Type**: string

**Enum Values**: &quot;NAMED&quot;, &quot;POSITIONAL&quot;

&lt;jumplink id=&quot;whatsappbusinesshsmqualityscore&quot;&gt;&lt;/jumplink&gt;
### WhatsAppBusinessHSMQualityScore

Quality score rating for the template

**Type**: string

**Enum Values**: &quot;GREEN&quot;, &quot;RED&quot;, &quot;UNKNOWN&quot;, &quot;YELLOW&quot;

&lt;jumplink id=&quot;whatsappbusinesshsmrejectionreason&quot;&gt;&lt;/jumplink&gt;
### WhatsAppBusinessHSMRejectionReason

Reason the template was rejected

**Type**: string

**Enum Values**: &quot;ABUSIVE_CONTENT&quot;, &quot;CATEGORY_NOT_AVAILABLE&quot;, &quot;INCORRECT_CATEGORY&quot;, &quot;INVALID_FORMAT&quot;, &quot;NONE&quot;, &quot;PROMOTIONAL&quot;, &quot;SCAM&quot;, &quot;TAG_CONTENT_MISMATCH&quot;

&lt;jumplink id=&quot;whatsappbusinesshsmsource&quot;&gt;&lt;/jumplink&gt;
### WhatsAppBusinessHSMSource

How the template was created

**Type**: string

**Enum Values**: &quot;auto_generated&quot;, &quot;manual&quot;

&lt;jumplink id=&quot;whatsappbusinessmessagedisplayformat&quot;&gt;&lt;/jumplink&gt;
### WhatsAppBusinessMessageDisplayFormat

Display format for the template

**Type**: string

**Enum Values**: &quot;ORDER_DETAILS&quot;

&lt;jumplink id=&quot;whatsappbusinessmarketingmessageshsmsendtype&quot;&gt;&lt;/jumplink&gt;
### WhatsAppBusinessMarketingMessagesHSMSendType

Send type for marketing message templates

**Type**: string

**Enum Values**: &quot;campaign&quot;, &quot;direct&quot;

&lt;jumplink id=&quot;messagetemplatesresponse&quot;&gt;&lt;/jumplink&gt;
### MessageTemplatesResponse

Response containing list of message templates with pagination

| Property | Type | Required | Description |
|----------|------|----------|-------------|
| data | array of [MessageTemplate](#messagetemplate) |  | Array of message templates |
| paging | [CursorPaging](#cursorpaging) |  |  |

&lt;jumplink id=&quot;cursorpaging&quot;&gt;&lt;/jumplink&gt;
### CursorPaging

Cursor-based pagination information

| Property | Type | Required | Description |
|----------|------|----------|-------------|
| cursors | [Cursors](#object-cursors-7) |  |  |
| next | string |  | URL for the next page of results |
| previous | string |  | URL for the previous page of results |

&lt;jumplink id=&quot;successresponse&quot;&gt;&lt;/jumplink&gt;
### SuccessResponse

Generic success response

| Property | Type | Required | Description |
|----------|------|----------|-------------|
| success | boolean |  | Whether the operation was successful |

&lt;jumplink id=&quot;createtemplateresponse&quot;&gt;&lt;/jumplink&gt;
### CreateTemplateResponse

Response after creating a message template

| Property | Type | Required | Description |
|----------|------|----------|-------------|
| id | string |  | ID of the created template |
| status | [WhatsAppBusinessHSMStatus](#whatsappbusinesshsmstatus) |  |  |
| category | [WhatsAppBusinessHSMTag](#whatsappbusinesshsmtag) |  |  |

&lt;jumplink id=&quot;graphapierror&quot;&gt;&lt;/jumplink&gt;
### GraphAPIError

Standard Graph API error response

| Property | Type | Required | Description |
|----------|------|----------|-------------|
| error | [Error](#object-error-8) | ✓ |  |

## Inline Object Definitions

&lt;jumplink id=&quot;object-bid_spec-1&quot;&gt;&lt;/jumplink&gt;
### Bid_spec

Bid specification for marketing message templates

| Property | Type | Required | Description |
|----------|------|----------|-------------|
| bid_strategy | string |  | Bid strategy for the template |
| bid_amount | integer |  | Bid amount in currency minor units |

&lt;jumplink id=&quot;object-buttons-2&quot;&gt;&lt;/jumplink&gt;
### Buttons

| Property | Type | Required | Description |
|----------|------|----------|-------------|
| type | One of &quot;CATALOG&quot;, &quot;COPY_CODE&quot;, &quot;FLOW&quot;, &quot;MPM&quot;, &quot;OTP&quot;, &quot;PHONE_NUMBER&quot;, &quot;QUICK_REPLY&quot;, &quot;URL&quot; |  | Button type |
| text | string |  | Button label text |
| url | string |  | URL for URL buttons |
| phone_number | string |  | Phone number for call buttons |
| otp_type | One of &quot;COPY_CODE&quot;, &quot;ONE_TAP&quot;, &quot;ZERO_TAP&quot; |  | OTP button type for authentication templates |
| autofill_text | string |  | Autofill button text for one-tap OTP buttons |
| package_name | string |  | Android package name for one-tap OTP buttons |
| signature_hash | string |  | Android app signature hash for one-tap OTP buttons |
| flow_id | string |  | Flow ID for flow buttons |
| flow_name | string |  | Flow name for flow buttons (alternative to flow_id) |
| flow_json | string |  | Inline flow JSON definition for flow buttons |
| flow_action | One of &quot;data_exchange&quot;, &quot;navigate&quot; |  | Flow action type |
| navigate_screen | string |  | Screen ID to navigate to for flow buttons |

&lt;jumplink id=&quot;object-example-3&quot;&gt;&lt;/jumplink&gt;
### Example

Example values for template parameters

| Property | Type | Required | Description |
|----------|------|----------|-------------|
| header_text | array of string |  | Example values for header text parameters |
| header_handle | array of string |  | Media handle IDs for header media examples |
| body_text | array of array of string |  | Example values for body text parameters |

&lt;jumplink id=&quot;object-components-4&quot;&gt;&lt;/jumplink&gt;
### Components

| Property | Type | Required | Description |
|----------|------|----------|-------------|
| type | One of &quot;BODY&quot;, &quot;BUTTONS&quot;, &quot;CAROUSEL&quot;, &quot;FOOTER&quot;, &quot;HEADER&quot;, &quot;LIMITED_TIME_OFFER&quot; |  | Component type |
| text | string |  | Text content of the component |
| format | One of &quot;DOCUMENT&quot;, &quot;IMAGE&quot;, &quot;LOCATION&quot;, &quot;TEXT&quot;, &quot;VIDEO&quot; |  | Format of the header component |
| buttons | array of [Buttons](#object-buttons-2) |  | Button components |
| add_security_recommendation | boolean |  | Whether to add security recommendation text to authentication templates |
| code_expiration_minutes | integer |  | OTP code expiration time in minutes for authentication templates |
| example | [Example](#object-example-3) |  | Example values for template parameters |

&lt;jumplink id=&quot;object-health_status-5&quot;&gt;&lt;/jumplink&gt;
### Health_status

Health status information for the template

| Property | Type | Required | Description |
|----------|------|----------|-------------|
| can_send_message | string |  | Whether messages can be sent using this template |

&lt;jumplink id=&quot;object-quality_score-6&quot;&gt;&lt;/jumplink&gt;
### Quality_score

Quality score information for the template

| Property | Type | Required | Description |
|----------|------|----------|-------------|
| score | [WhatsAppBusinessHSMQualityScore](#whatsappbusinesshsmqualityscore) |  |  |
| reason | string |  | Reason for the current quality score |
| reasons | array of string |  | List of reasons affecting the quality score |
| date | integer (int64) |  | Unix timestamp of the quality score evaluation |

&lt;jumplink id=&quot;object-cursors-7&quot;&gt;&lt;/jumplink&gt;
### Cursors

| Property | Type | Required | Description |
|----------|------|----------|-------------|
| before | string |  | Cursor pointing to the start of the page |
| after | string |  | Cursor pointing to the end of the page |

&lt;jumplink id=&quot;object-error-8&quot;&gt;&lt;/jumplink&gt;
### Error

| Property | Type | Required | Description |
|----------|------|----------|-------------|
| message | string | ✓ | Human-readable error message |
| type | string | ✓ | Error category type |
| code | integer | ✓ | Numeric error code |
| error_subcode | integer |  | More specific error subcode |
| fbtrace_id | string |  | Unique identifier for debugging |
| is_transient | boolean |  | Whether this error is temporary |
| error_user_title | string |  | User-friendly error title |
| error_user_msg | string |  | User-friendly error message |

## Authentication

| Scheme | Type | Location |
|--------|------|----------|
| bearerAuth | HTTP Bearer | Header: `Authorization` |

### Usage Examples

- **bearerAuth**: Include `Authorization: Bearer your-token-here` in request headers

### Global Authentication Requirements

All endpoints require: bearerAuth
