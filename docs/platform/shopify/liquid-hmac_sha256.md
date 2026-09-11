---
title: "Liquid hmac_sha256 filter"
source: "https://shopify.dev/docs/api/liquid/filters/hmac_sha256"
final_url: "https://shopify.dev/docs/api/liquid/filters/hmac_sha256"
platform: "shopify"
fetched_at: "2026-09-11T09:20:10Z"
last_checked_at: "2026-09-11T10:13:18Z"
previous_fetched_at: ""
http_status: "200"
format: "html-converted"
sha256: "315c7e93db111ec36f3cceff7a7184d293a463e014736a44d8c5e101011d066f"
---

1

string | hmac\_sha256: string

returns [string](/docs/api/liquid/basics#string)

Converts a string into an SHA-256 hash using a hash message authentication code (HMAC).

The secret key for the message is supplied as a parameter to the filter.

1

2

3

{%- assign secret\_potion = 'Polyjuice' | hmac\_sha256: 'Polina' -%}

My secret potion: {{ secret\_potion }}

##### Code

```
{%- assign secret_potion = 'Polyjuice' | hmac_sha256: 'Polina' -%}

My secret potion: {{ secret_potion }}
```

## Output

1

My secret potion: 8e0d5d65cff1242a4af66c8f4a32854fd5fb80edcc8aabe9b302b29c7c71dc20

##### Output

```
My secret potion: 8e0d5d65cff1242a4af66c8f4a32854fd5fb80edcc8aabe9b302b29c7c71dc20
```

Was this page helpful?
