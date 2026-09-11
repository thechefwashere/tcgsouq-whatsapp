---
title: "Trusted Web Activities overview"
source: "https://developer.chrome.com/docs/android/trusted-web-activity"
final_url: "https://developer.chrome.com/docs/android/trusted-web-activity"
platform: "android-play"
fetched_at: "2026-09-11T10:16:59Z"
last_checked_at: "2026-09-11T10:17:58Z"
previous_fetched_at: ""
http_status: "200"
format: "html-converted"
sha256: "da3267982208cffa4b360c168d8353d9b9cb23b9487f95d57219a20965803393"
---

# Overview Stay organized with collections Save and categorize content based on your preferences.

Pete LePage

André Cipriani Bandarra

**Trusted Web Activity** is a new way to open *your* web-app content
such as *your* Progressive Web App (PWA) from *your* Android app using a protocol based on Custom
Tabs.

*Looking for the code?*

- [android-browser-helper library on GitHub](https://github.com/GoogleChrome/android-browser-helper)
- [Trusted Web Activity demos](https://github.com/GoogleChrome/android-browser-helper/tree/master/demos)
- [Bubblewrap, a NodeJs library / CLI to generate and build Trusted Web Activity projects](https://github.com/GoogleChromeLabs/bubblewrap)

There are a few things that make Trusted Web Activity different from other
ways to open web content from your Android app:

1. Content in a Trusted Web activity is **trusted** -- the app and the site it
   opens are expected to come from the same developer. (This is verified using
   [Digital Asset Links](https://developers.google.com/digital-asset-links/v1/getting-started).)
2. The content rendered in a Trusted Web Activity comes from the **web**: they're
   rendered by the user's browser, in exactly the same way as a user would see
   it in their browser except they are run fullscreen. Web content should be
   accessible and useful in the browser first.
3. Browsers are also updated independent of Android and your app -- Chrome, for
   example, is available back to Android Jelly Bean. That saves on APK size and
   ensures you can use a modern web runtime. (Note that since Lollipop, WebView
   has also been updated independent of Android, but there are a [significant number](https://developer.android.com/about/dashboards/index.html) of
   pre-Lollipop Android users.)
4. The host app doesn't have direct access to web content in a Trusted Web
   Activity or any other kind of web state, like cookies and `localStorage`.
   Nevertheless, you can coordinate with the web content by passing data to and
   from the page in URLs (e.g. through query parameters and
   [intent URIs](/docs/multidevice/android/intents).)
5. Transitions between web and native content are between **activities**. Each
   activity (i.e. screen) of your app is either completely provided by the web,
   or by an Android activity

To make it easier to test, there are currently no qualifications for content
opened in the preview of Trusted Web activities. You can expect, however, that
Trusted Web activities will need to meet the same
[Add to Home Screen](https://web.dev/customize-install#criteria)
requirements. You can audit your site for these requirements using the
[Lighthouse](https://web.dev/measure/) "*user can be prompted to Add to Home
screen*" audit.

Today, if the user's version of Chrome doesn't support Trusted Web activities,
Chrome will fall back to a simple toolbar using a Custom Tab. It
is also possible for other browsers to implement the same protocol that Trusted
Web activities use. While the host app has the final say on what browser gets
opened, we recommend the same policy as for Custom Tabs: use the user's default
browser, so long as that browser provides the required capabilities.

## Where to go next

If you are looking for quickly building an Android app that just starts and opens your PWA,
checkout out the [Quick Start Guide](/docs/android/trusted-web-activity/quick-start).

If integrating Trusted Web Activity into an existing Android App, the [Integration Guide](/docs/android/trusted-web-activity/integration-guide)
is a good place to get started.
