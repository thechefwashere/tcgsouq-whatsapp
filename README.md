# tcgsouq-whatsapp — PokeSouq WhatsApp

Private WhatsApp inbox and broadcast tool for [PokeSouq.com](https://pokesouq.com) on
Meta's WhatsApp Cloud API, replacing Wati: inbox PWA, templates including carousel,
segmented broadcasts, customer preferences and consent, order updates from Shopify, and a
health dashboard for the number.

Status: **scoping**. No application code yet. The plan, research and alignment proposal
live in `thechefwashere/tcgsouq-shopify` under `docs/social-hub/`. The sibling repo
`tcgsouq-social` owns social posting.

## docs/platform — the ground rules

`docs/platform/` holds a dated snapshot of the official WhatsApp Business Platform
documentation (Cloud API, templates, webhooks, pricing, limits), the WhatsApp and Meta
policies that govern messaging, and the Shopify endpoints this tool uses. Each file carries
a front matter with the source URL, the UTC fetch time and a hash of the content, so a later
re-fetch shows exactly which rules changed and when.

```
docs/platform/manifest.json        the list of pages to snapshot
docs/platform/<platform>/INDEX.md  per-platform index with fetch dates and status
docs/platform/<platform>/<page>.md the snapshot (front matter + Markdown)
docs/platform/CHANGES.md           appended on every re-run that finds changed pages
```

Re-fetch (needs Python 3.11+):

```
pip install --user beautifulsoup4 lxml markdownify
python3 scripts/fetch_platform_docs.py --manifest docs/platform/manifest.json
```

Unchanged pages keep their original `fetched_at` and only update `last_checked_at`.
Pages marked `EMPTY` in an index are rendered in the browser and could not be captured
by a plain fetch; they are listed so nobody assumes they were checked.

Meta's `developers.facebook.com/documentation/...` pages are served as Markdown to
non-browser clients and are stored as received; all other pages are converted from HTML.
Snapshots are reference copies of third-party documents and remain the property of their
publishers.
