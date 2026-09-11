---
title: "TWA quick start (Bubblewrap)"
source: "https://developer.chrome.com/docs/android/trusted-web-activity/quick-start"
final_url: "https://developer.chrome.com/docs/android/trusted-web-activity/quick-start"
platform: "android-play"
fetched_at: "2026-09-11T10:16:59Z"
last_checked_at: "2026-09-11T10:16:59Z"
previous_fetched_at: ""
http_status: "200"
format: "html-converted"
sha256: "79e45b04d10ee65dcc6f9a4333f816aae1248bdc5347d5ce6ac65e688da4cef4"
---

# Quick start to Trusted Web Activities Stay organized with collections Save and categorize content based on your preferences.

Peter Conn

Trusted Web Activities can be challenging to set up, especially if you just want
to display your website. This guide teaches you how to create a small project
that uses Trusted Web Activities.

By the end of this guide, you'll:

- Have used [Bubblewrap](https://github.com/GoogleChromeLabs/bubblewrap) to
  build an application that uses a Trusted Web Activity and passes verification.
- Understand when your signing keys are used.
- Be able to determine the signature your Android Application is being built with.
- Know how to create a basic [Digital Asset Links](https://developers.google.com/digital-asset-links/v1/getting-started) file.

To follow this guide, you need:

- [Node.js](https://nodejs.org/) 10 or higher.
- An Android phone or emulator, connected and set up for development.
  [Enable USB debugging](https://developer.android.com/studio/debug/dev-options.html#enable)
  if you're using a physical phone.
- A mobile browser that supports Trusted Web Activity.
- A website you'd like to view in the Trusted Web Activity.

You can use a Trusted Web Activity for your Android App to launch a full screen
browser tab, without any browser UI. This capability is restricted to websites
that you own. You prove ownership by setting up [Digital Asset Links](#creating-your-asset-link-file).

When you launch a Trusted Web Activity, the browser verifies the Digital Asset
Links. If verification fails, the browser falls back to displaying your website
as a [Custom Tab](/docs/android/custom-tabs).

## Install and configure Bubblewrap

[Bubblewrap](https://github.com/GoogleChromeLabs/bubblewrap) is a set of
libraries and a command line tool (CLI) for Node.js that helps developers
generate, build and run Progressive Web Apps inside Android applications,
using Trusted Web Activity.

Install the CLI by running this command:

```
npm i -g @bubblewrap/cli
```

### Setting up the Environment

When running Bubblewrap for the first time, it offers to automatically download
and install the required external dependencies. We recommend allowing automatic
downloads, as it helps make sure dependencies are configured correctly. Check
the [Bubblewrap documentation](https://github.com/GoogleChromeLabs/bubblewrap/blob/main/packages/cli/README.md) to use an existing Java Development Kit (JDK)
or Android command line tools installation.

## Initialize and build project

Initialize an Android project that wraps a PWA:

```
bubblewrap init --manifest=https://my-twa.com/manifest.json
```

Bubblewrap reads the [Web Manifest](https://developer.mozilla.org/docs/Web/Manifest),
asks developers to confirm values to be used in the Android project, and
generates the project using those values.

Once the project has been generated, generate an APK by running:

```
bubblewrap build
```

## Run

The build step outputs a file called `app-release-signed.apk`. This file can be
installed on a development device for testing or uploaded to the Play Store for
release.

Bubblewrap provides a command to install and test the application on a local
device. With the development device connected to the computer run:

```
bubblewrap install
```

Alternatively, the [adb](https://developer.android.com/studio/command-line/adb#move)
tool can be used.

```
adb install app-release-signed.apk
```

The application should now be available on the device launcher.

When opening the application, you'll notice that your website is launched as a
Custom Tab, not a Trusted Web Activity. This is because we haven't set up our
Digital Asset Links validation yet.

### Graphical User Interface (GUI) alternatives for Bubblewrap

[PWA Builder](https://www.pwabuilder.com/) provides a GUI interface that uses
the Bubblewrap library to power the generation of Trusted Web Activity projects.
Find instructions on
[how to use PWA Builder to create an Android App that opens your PWA](https://www.davrous.com/2020/02/07/publishing-your-pwa-in-the-play-store-in-a-couple-of-minutes-using-pwa-builder/).

### Signing keys

Digital Asset Links take into account the key that an APK has been signed with and a common cause for verification failing is to use the wrong signature. (Remember, failing verification means you'll launch your website as a Custom Tab with browser UI at the top of the page.) When Bubblewrap builds the application, an APK will be created with a key setup during the `init` step. However, when you publish your app in Google Play, another key may be created for you, depending on how you choose to handle signing keys. Learn more on [signing keys and how they relate to Bubblewrap and Google Play](/docs/android/trusted-web-activity/android-for-web-devs#upload-vs-signing-key).

## Setting up your asset link file

Digital Asset Links consist essentially of a file on your website that points to your app and some
metadata in your app that points to your website.

After creating your `assetlinks.json` file, upload it to your website at `.well-known/assetlinks.json` relative to the root) so that your app can be verified properly by the browser. Check out a [deep dive on Digital Asset Links](/docs/android/trusted-web-activity/android-for-web-devs#digital-asset-links) for more information on how it relates to your signing key.

## Checking your browser

A Trusted Web Activity will try to adhere to the user's default choice of browser.
If the user's default browser supports Trusted Web Activities, it will be launched.
Failing that, if any installed browser supports Trusted Web Activities, it will be chosen.
Finally, the default behavior is to fall back to a Custom Tabs mode.

This means that if you're debugging something to do with Trusted Web Activities, you should
make sure you're using the browser you think that you are.
You can use the following command to check which browser is being used:

```
> adb logcat -v brief | grep -e TWAProviderPicker
D/TWAProviderPicker(17168): Found TWA provider, finishing search: com.google.android.apps.chrome
```

## Next steps

Hopefully, if you've followed this guide, you have a working Trusted Web
Activity and enough knowledge to debug if verification fails.
If not, have a look at more [Android concepts for web developers](/docs/android/trusted-web-activity/android-for-web-devs).

For your next steps, [create an icon for your app](https://developer.android.com/studio/write/image-asset-studio#launcher).
Once that's done, you can consider deploying your app to the Play Store.
