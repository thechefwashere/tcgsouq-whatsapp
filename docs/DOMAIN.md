# Domain — what this repo needs from tcgsouq.com

Canonical record: `thechefwashere/tcgsouq-social` → `docs/domain/`. Read **`CHARTER.md`**
first — it holds the two-domain decision and the rules every repo follows (R1–R9). `README.md`
has the host map and live state, `RUNBOOK.md` the registrar steps.

State as of 17 Sep 2026: `tcgsouq.com` is at Porkbun with the delegation switched (20:55
UTC), and Google Workspace is live on it — so the zone is ours and records can be added.
What is listed below waits on its own host side, not on DNS.

## Hostnames this repo owns

| Host | Serves | Points at | Waiting on |
|---|---|---|---|
| `inbox.tcgsouq.com` | the WhatsApp inbox PWA | Railway | the Railway service existing |

Meta's webhook needs an HTTPS URL, not a hostname of its own: it lives on a path under the
hub, so there is no separate webhook record to create.

## Three things that will bite

- **Railway custom domains need a CNAME *and* a TXT challenge**, both printed per-domain in the
  Railway dashboard. The CNAME alone returns 404. Hobby allows 2 custom domains per service.
- **The inbox is a PWA, so its origin is permanent.** A service worker, push subscriptions and
  the iOS Home Screen install are all bound to the exact origin. Moving `inbox.` later means
  every installed copy re-installs and every push subscription is re-issued. Pick the hostname
  before the first install, not after.
- **An Android TWA wrapper, if it ever happens, needs `assetlinks.json`** served at
  `https://inbox.tcgsouq.com/.well-known/assetlinks.json` — an HTTPS fetch from the app's own
  origin, which is another reason not to move it.

## Shared login with the hub

The plan's original topology put both tools behind one hostname with path routing, which on
Railway needs a proxy in front. Two subdomains of one domain avoid that, sharing a session
cookie scoped to `.tcgsouq.com`. Supabase Auth defaults to `localStorage`, which is
per-origin, so this needs cookie-based session storage configured with an explicit parent
domain — a known pattern, but not the default, and not yet tested here. Decision D2 in the
canonical doc.
