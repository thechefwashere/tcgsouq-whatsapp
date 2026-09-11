---
title: "Changelog: legacy customer accounts deprecated"
source: "https://shopify.dev/changelog/legacy-customer-accounts-are-deprecated"
final_url: "https://shopify.dev/changelog/legacy-customer-accounts-are-deprecated"
platform: "shopify"
fetched_at: "2026-09-11T09:20:10Z"
last_checked_at: "2026-09-11T10:17:58Z"
previous_fetched_at: ""
http_status: "200"
format: "html-converted"
sha256: "700f9e741aaca48f422b0b55029d0a32c5437e2474b661c71fef0cc5a75c9012"
---

Legacy customer accounts are no longer available to new stores and existing stores not using it. Shopify will stop providing feature updates and technical support for this older version.

A final sunset date for legacy customer accounts will be announced later in 2026. We strongly recommend that merchants [upgrade](https://help.shopify.com/en/manual/customers/customer-accounts/upgrade) their customer accounts ahead of the deadline.

## If you build themes

Theme developers should no longer include legacy customer account liquid files. Any store that is on legacy customer accounts, that upgrades to a theme without the legacy files, will automatically be upgraded to the latest version of customer accounts.

Simplify customer account implementation across your themes with our new [shopify-account web component](https://shopify.dev/docs/storefronts/themes/customer-engagement/account-component) that automatically redirects to the latest version of customer accounts.

## If you build apps

Developers can use Shopify Extensions to develop apps that customize and extend customer accounts in a way that does not require customizing liquid templates. If your app relies on legacy customer account liquid pages, it won’t work for merchants on the latest version of customer accounts.

With [customer account UI extensions](https://shopify.dev/docs/api/customer-account-ui-extensions/latest), you can enhance native pages like order status, order list, profile, and even build unique full-page experiences. [800+ apps](https://apps.shopify.com/extensions/customer-account) have already made the switch. [Build your first customer account extension](https://shopify.dev/docs/apps/build/customer-accounts) now and put your app in front of over 70% of Shopify merchants (and growing) already using customer accounts.

## If you build custom storefronts

Use the [Customer Account API](https://shopify.dev/docs/api/customer/latest) as your source for customer-scoped data and authenticated customer actions in order to create the most secure customer experiences.

If you build custom storefronts or apps that currently use Storefront API customer-scoped mutations, we recommend switching to the Customer Account API as soon as possible.

Was this page helpful?
