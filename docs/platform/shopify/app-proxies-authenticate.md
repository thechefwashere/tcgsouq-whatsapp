---
title: "Authenticate app proxy requests"
source: "https://shopify.dev/docs/apps/build/online-store/app-proxies/authenticate-app-proxies"
final_url: "https://shopify.dev/docs/apps/build/online-store/app-proxies/authenticate-app-proxies"
platform: "shopify"
fetched_at: "2026-09-11T09:20:10Z"
last_checked_at: "2026-09-11T10:17:58Z"
previous_fetched_at: ""
http_status: "200"
format: "html-converted"
sha256: "7d571f9fcb6b5f559608bfe360fa45f74a8613e201717c0fd51ee643c16c6037"
---

# Use request.query\_string in rails

query\_string = "extra=1&extra=2&shop={shop}.myshopify.com&logged\_in\_customer\_id=1&path\_prefix=%2Fapps%2Fawesome\_reviews&timestamp=1317327555&signature=4c68c8624d737112c91818c11017d24d334b524cb5c2b8ba08daa056f7395ddb"

query\_hash = Rack::Utils.parse\_query(query\_string)

# => {

# "extra" => ["1", "2"],

# "shop" => "{shop}.myshopify.com",

# "logged\_in\_customer\_id" => 1,

# "path\_prefix" => "/apps/awesome\_reviews",

# "timestamp" => "1317327555",

# "signature" => "4c68c8624d737112c91818c11017d24d334b524cb5c2b8ba08daa056f7395ddb",

# }

# Remove and save the "signature" entry

signature = query\_hash.delete("signature")

sorted\_params = query\_hash.collect{ |k, v| "#{k}=#{Array(v).join(',')}" }.sort.join

# => "extra=1,2logged\_in\_customer\_id=1path\_prefix=/apps/awesome\_reviewsshop={shop}.myshopify.comtimestamp=1317327555"

calculated\_signature = OpenSSL::HMAC.hexdigest(OpenSSL::Digest.new('sha256'), SHARED\_SECRET, sorted\_params)

raise 'Invalid signature' unless ActiveSupport::SecurityUtils.secure\_compare(signature, calculated\_signature)

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

20

21

22

23

24

25

require 'openssl'

require 'rack/utils'

SHARED\_SECRET = 'hush'

# Use request.query\_string in rails

query\_string = "extra=1&extra=2&shop={shop}.myshopify.com&logged\_in\_customer\_id=&path\_prefix=%2Fapps%2Fawesome\_reviews&timestamp=1317327555&signature=e072b6d7e6622d85912a5214b860d3100dc1e73d9bc29f43796ac8c9ff8093cb"

query\_hash = Rack::Utils.parse\_query(query\_string)

# => {

# "extra" => ["1", "2"],

# "shop" => "{shop}.myshopify.com",

# "logged\_in\_customer\_id" => "",

# "path\_prefix" => "/apps/awesome\_reviews",

# "timestamp" => "1317327555",

# "signature" => "e072b6d7e6622d85912a5214b860d3100dc1e73d9bc29f43796ac8c9ff8093cb",

# }

# Remove and save the "signature" entry

signature = query\_hash.delete("signature")

sorted\_params = query\_hash.collect{ |k, v| "#{k}=#{Array(v).join(',')}" }.sort.join

# => "extra=1,2logged\_in\_customer\_id=path\_prefix=/apps/awesome\_reviewsshop={shop}.myshopify.comtimestamp=1317327555"

calculated\_signature = OpenSSL::HMAC.hexdigest(OpenSSL::Digest.new('sha256'), SHARED\_SECRET, sorted\_params)

raise 'Invalid signature' unless ActiveSupport::SecurityUtils.secure\_compare(signature, calculated\_signature)

##### Customer logged in

```
require 'openssl'
require 'rack/utils'
SHARED_SECRET = 'hush'

# Use request.query_string in rails
query_string = "extra=1&extra=2&shop={shop}.myshopify.com&logged_in_customer_id=1&path_prefix=%2Fapps%2Fawesome_reviews&timestamp=1317327555&signature=4c68c8624d737112c91818c11017d24d334b524cb5c2b8ba08daa056f7395ddb"

query_hash = Rack::Utils.parse_query(query_string)
# => {
#   "extra" => ["1", "2"],
#   "shop" => "{shop}.myshopify.com",
#   "logged_in_customer_id" => 1,
#   "path_prefix" => "/apps/awesome_reviews",
#   "timestamp" => "1317327555",
#   "signature" => "4c68c8624d737112c91818c11017d24d334b524cb5c2b8ba08daa056f7395ddb",
# }

# Remove and save the "signature" entry
signature = query_hash.delete("signature")

sorted_params = query_hash.collect{ |k, v| "#{k}=#{Array(v).join(',')}" }.sort.join
# => "extra=1,2logged_in_customer_id=1path_prefix=/apps/awesome_reviewsshop={shop}.myshopify.comtimestamp=1317327555"

calculated_signature = OpenSSL::HMAC.hexdigest(OpenSSL::Digest.new('sha256'), SHARED_SECRET, sorted_params)
raise 'Invalid signature' unless ActiveSupport::SecurityUtils.secure_compare(signature, calculated_signature)
```

##### Anonymous customer

```
require 'openssl'
require 'rack/utils'
SHARED_SECRET = 'hush'

# Use request.query_string in rails
query_string = "extra=1&extra=2&shop={shop}.myshopify.com&logged_in_customer_id=&path_prefix=%2Fapps%2Fawesome_reviews&timestamp=1317327555&signature=e072b6d7e6622d85912a5214b860d3100dc1e73d9bc29f43796ac8c9ff8093cb"

query_hash = Rack::Utils.parse_query(query_string)
# => {
#   "extra" => ["1", "2"],
#   "shop" => "{shop}.myshopify.com",
#   "logged_in_customer_id" => "",
#   "path_prefix" => "/apps/awesome_reviews",
#   "timestamp" => "1317327555",
#   "signature" => "e072b6d7e6622d85912a5214b860d3100dc1e73d9bc29f43796ac8c9ff8093cb",
# }

# Remove and save the "signature" entry
signature = query_hash.delete("signature")

sorted_params = query_hash.collect{ |k, v| "#{k}=#{Array(v).join(',')}" }.sort.join
# => "extra=1,2logged_in_customer_id=path_prefix=/apps/awesome_reviewsshop={shop}.myshopify.comtimestamp=1317327555"

calculated_signature = OpenSSL::HMAC.hexdigest(OpenSSL::Digest.new('sha256'), SHARED_SECRET, sorted_params)
raise 'Invalid signature' unless ActiveSupport::SecurityUtils.secure_compare(signature, calculated_signature)
```

Caution

The signature check only guarantees that the request hasn't been tampered with.
The app must also verify that the `logged_in_customer_id` query parameter matches the customer that's associated with the requested data. This ensures that the app returns only data owned by the authenticated user.

**Caution:**

The signature check only guarantees that the request hasn't been tampered with.
The app must also verify that the `logged_in_customer_id` query parameter matches the customer that's associated with the requested data. This ensures that the app returns only data owned by the authenticated user.

---

Was this page helpful?
