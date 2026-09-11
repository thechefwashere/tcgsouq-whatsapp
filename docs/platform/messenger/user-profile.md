---
title: "Messenger: user profile (PSID fields)"
source: "https://developers.facebook.com/docs/messenger-platform/identity/user-profile"
final_url: "https://developers.facebook.com/documentation/business-messaging/messenger-platform/identity/user-profile"
platform: "messenger"
fetched_at: "2026-09-11T10:07:06Z"
last_checked_at: "2026-09-11T10:13:18Z"
previous_fetched_at: ""
http_status: "200"
format: "markdown-served"
sha256: "57af1d1d69a2cc9154d3f8cf8071e2d0bbdd44146a3cdda8571edd2311015e8e"
---

# User Profile API



The User Profile API allows you to use a Page-scoped ID (PSID) to retrieve user profile information that can be used to personalize the experience of people interacting with your Messenger.

## Requirements
* To retrieve a user&#039;s profile information, you need to have Advanced Access for the [Business Asset User Profile Access](https://developers.facebook.com/docs/graph-api/changelog/version8.0#baupa) feature. Some fields require [additional permissions](#fields) for access.

## Limitations
Though a PSID may be valid, in some cases it may not be able to be used to retrieve a person&#039;s profile information. For example, PSIDs associated with Instant Games Pages are not accessible via the User Profile API.

### User Opt-in &#123;#optin&#125;

The following events will authorize your Messenger bot to access a person&#039;s profile information:

- The person starts the conversation via [a welcome screen](https://developers.facebook.com/documentation/business-messaging/messenger-platform/discovery/welcome-screen) and tapped the &quot;Get Started&quot; button.
- The person starts the conversation by clicking a &quot;Send to Messenger&quot; button.
- The person starts the conversation by sending a message.
- The person starts the conversation by accepting a Page&#039;s message request.
- Your Messenger bot uses the [`askPermission()` function](https://developers.facebook.com/documentation/business-messaging/messenger-platform/webview/permissions) of the Messenger Extensions SDK in the webview to ask for the `user_profile` permission.
- For [Business apps](https://developers.facebook.com/docs/development/create-an-app/app-dashboard/app-types#business), the [Business Asset User Profile Access](https://developers.facebook.com/docs/apps/features-reference#business-asset-user-profile-access) feature is additionally required, and can be applied for via [App Review](https://developers.facebook.com/docs/app-review).

Some entry points allow apps to initiate a conversation without granting the app authorization to access the person&#039;s public profile. In those cases, the app will be granted permission to access the person&#039;s profile after the person replied to the initial message. Notable situations where a person may initiate a conversation with the app, but not authorize profile permission include the following:

- Conversations started via the [Checkbox Plugin](https://developers.facebook.com/documentation/business-messaging/messenger-platform/discovery) where the person did not respond on Messenger.
- Interactions with [Ads that Click to Messenger](https://developers.facebook.com/docs/messenger-platform/guides/ads) before the person has replied on Messenger

### Profile Unavailable &#123;#profile_unavailable&#125;

Currently, the User Profile API does not support retrieving profile information for Messenger accounts that were created using a phone number.

In this case, the API will return the error code `2018218` along with the message &#039;No profile available for this user.&#039;

## Available Profile Fields &#123;#fields&#125;

Apps that have received [App Review approval](https://developers.facebook.com/docs/app-review) for the required feature and permission may retrieve the following fields for users who have made this information public and have opted-in to your Page.

| Field Name | Description | Feature or Permission Required for Access |
| --- | --- | --- |
| `id` | The user&#039;s PSID | [Business Asset User Profile Access](https://developers.facebook.com/docs/apps/features-reference/business-asset-user-profile-access) feature |
| `name` | The user&#039;s first and last name | [Business Asset User Profile Access](https://developers.facebook.com/docs/apps/features-reference/business-asset-user-profile-access) feature |
| `first_name` | First name | [Business Asset User Profile Access](https://developers.facebook.com/docs/apps/features-reference/business-asset-user-profile-access) feature |
| `last_name` | Last name | [Business Asset User Profile Access](https://developers.facebook.com/docs/apps/features-reference/business-asset-user-profile-access) feature |
| `profile_pic` | URL to the Profile picture. The URL will expire. | [Business Asset User Profile Access](https://developers.facebook.com/docs/apps/features-reference/business-asset-user-profile-access) feature |
| `locale` | Locale of the user on Facebook. For supported locale codes, see [Supported Locales](https://developers.facebook.com/documentation/business-messaging/messenger-platform/messenger-profile/supported-locales). | [`pages_user_locale` permission](https://developers.facebook.com/docs/permissions/reference/pages_user_locale) |
| `timezone` | Timezone, number relative to GMT | [`pages_user_timezone` permission](https://developers.facebook.com/docs/permissions/reference/pages_user_timezone) |
| `gender` | Gender | [`pages_user_gender` permission](https://developers.facebook.com/docs/permissions/reference/pages_user_gender) |

### Requesting feature access to user fields for the Page

1. Go to _Page Settings &gt; Advanced Messaging_
2. Under &#039;Info About People&#039; select the field and click the &#039;Request&#039; button.

## Retrieving a Person&#039;s Profile &#123;#request&#125;

To use the User Profile API, send a `GET` request with the [profile fields](#fields) you want for the person:

```curl
curl -X GET &quot;https://graph.facebook.com/&lt;PSID&gt;?fields=first_name,last_name,profile_pic&amp;access_token=&lt;PAGE_ACCESS_TOKEN&gt;&quot;
```


If the app is able to access the person&#039;s profile, the User Profile API will return a JSON string with the requested fields from the person&#039;s profile.

```curl
&#123;
  &quot;first_name&quot;: &quot;Peter&quot;,
  &quot;last_name&quot;: &quot;Chang&quot;,
  &quot;profile_pic&quot;: &quot;https://fbcdn-profile-a.akamaihd.net/hprofile-ak-xpf1/v/t1.0-1/p200x200/13055603_10105219398495383_8237637584159975445_n.jpg?oh=1d241d4b6d4dac50eaf9bb73288ea192&amp;oe=57AF5C03&amp;__gda__=1470213755_ab17c8c8e3a0a447fed3f272fa2179ce&quot;,
  &quot;locale&quot;: &quot;en_US&quot;,
  &quot;timezone&quot;: -7,
  &quot;gender&quot;: &quot;male&quot;,
&#125;
```


If the app is unable to access the person&#039;s profile, an empty object is returned.

## See Also

* [Messenger Platform Error Codes](https://developers.facebook.com/documentation/business-messaging/messenger-platform/error-codes)
