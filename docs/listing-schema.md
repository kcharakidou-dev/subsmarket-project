# Subsmarket — Listing Schema v1

Approved 2026-10-28; updated 2026-11-10 (multiple categories, fixed label lists per category, `voice` axis); updated 2026-11-12 ("AI app builders" label, `billing_names`, competitor-source rule; six label changes from Grok's new listings — in preview, not yet published); **updated 2026-11-15: listing tiers `data_tier` = verified / basic (Lovable commit c865773, preview only until the owner publishes).** Note: the label lists below predate the Nov 14–15 changes (Crypto, Ecommerce, Investing labels, Cybersecurity's antivirus labels, website builders split) — see `category-map.md` §0 and `grok-bot.md` until this list is refreshed. **Update 2026-11-15 (21:47, daily docs sync): the basic-listing support is published (Nov 15 ~18:3x, deployment c80345e9, per `system-registry.md`), and the label lists below were refreshed from `src/lib/subcategories.ts` — they now include the Nov 13–15 changes.** **Update 2026-11-24 (nightly update): "Work OS" renamed "Project management" (HQ #47, Lovable commit a58437b, live); the two Email & SMS marketing labels of Nov 23 added to the list (HQ #37, commit 1d0bd70).**

Governs every tool listing in the Subsmarket catalog (Lovable project "Scout Your Next Tool"). Additive to the existing `tools` table; nothing existing is removed.

## Principles

1. **Structured over free text.** Pricing, ratings and geo facts are columns, not sentences, so the site can sort, filter and compute.
2. **Every fact has a date.** `price_verified_at` and `ratings_verified_at` are mandatory on verified listings; the UI shows "verified <month year>".
3. **No invented data.** Unknown = `null`, never a guess. Tier prices come from the vendor's pricing page or two independent 2026 trackers.
4. **Own words only.** Community sentiment is summarised, never quoted. External ratings are numbers + counts with a link out. Competitor sites (Capterra, G2, AppSumo, Product Hunt, AlternativeTo) may be used to discover which tools and categories exist — names and websites only; never their descriptions, feature lists, reviews or images.
5. **Affiliate data is private.** Commission terms, networks and application status live in an admin-only table, never on the public page.
6. **Persona prices make tools comparable.** Every verified listing carries what a solo user and a team of 5 would actually pay per month (cheapest sensible paid tier, annual billing where offered, seat minimums respected).
7. **List a tool everywhere a buyer would look.** A tool has a main category plus up to 2 more (max 3) where that use is a core part of the product, not a minor feature. Be conservative.

## 0. Listing tier (`tools.data_tier`, new Nov 15)

| Value | Meaning | What the site does |
|---|---|---|
| `verified` (default; all 572 existing rows) | prices and details checked on the vendor's own pages | shown first in category/subcategory lists and search; "Verified" check badge on cards with "Price and details checked on the vendor's site, <Mon YYYY>" (from `price_verified_at`); eligible for every showcase |
| `basic` | name, website, category/label, short description only; details not yet checked | shown **after** verified tools in lists and search; card says "Basic listing · details not yet checked", price "Not stated", no team price, no compare; trimmed tool page with a "check the vendor's site before you pay" note; **noindex**, not in sitemap; never in homepage sections, Quick picks, computed labels, guides, editorials, /essentials, Solution top-3, compare or "People also compared"; the advisor may suggest them only after verified fits and says "details not yet checked", never a price |

- Owner decision Nov 15: basic listings let the catalog grow beyond what can be fully verified each day; they stay visible but clearly labelled.
- A basic listing still follows the data rules: no invented prices (leave them null), own-words description, correct categories and labels.
- Upgrading basic → verified = full research per `grok-listing-brief.md`, then set `data_tier = 'verified'`.
- Admin Identity tab and CSV/JSON import accept `data_tier` (missing = verified; any other value is rejected).
- The vault's statement matching still uses all published tools, including basic ones.

## 1. Identity (`tools`)

| Field | Type | Notes |
|---|---|---|
| name, slug | text | existing |
| data_tier | text | `verified` / `basic` — see §0 |
| tagline | text | ≤ 15 words, own words |
| description | text | 2–4 sentences |
| logo_url | text | real brand logo (SVG/PNG), not Google favicon; NULL = resolved from domain via Logo.dev |
| website_url | text | existing |
| categories | `tool_categories` rows | 1–3 per tool (many-to-many) |
| subcategories | text[] | one label **per category** the tool is in, taken from that category's fixed list (see below) |
| sub_type | text | e.g. AI: assistant, writing, image, video, voice, agents, meetings, presentations, research · PM: task manager, work OS, kanban, time tracking, docs, agency & client work, personal productivity, roadmap & dev |
| hq_country | text | ISO-2 |
| status | text | `active` / `sunset` / `acquired` — default `active` |
| billing_names | text[] | card-statement descriptors (e.g. "OPENAI *CHATGPT"); drive the subscription monitor's matching; add when known, never guess |

### Fixed subcategory labels per category (source of truth in the site code: `src/lib/subcategories.ts`)
Tiles only show labels from the category's own list; a tool with no label from that list still appears in the category's "All tools" grid. Matching ignores upper/lower case. Counts and gaps per label: `category-map.md`.
- **ai-tools**: AI assistants & chat · Research & search · Writing & marketing copy · Video & avatars · Voice & audio · Meeting notes & transcription · Presentations & documents · AI agents & automation · Coding assistants · AI app builders
- **image-creation**: AI image generators · AI studios (image + video) · Photo editing & product shots · Logos & vectors · Text in images · Included in chat plans
- **project-management-productivity**: Project management *(named "Work OS" until Nov 24; "Work OS" stays as an alias and the old tile address redirects)* · Kanban · Roadmap & dev · Agency & client work · Freelancer ops · Client portals · Time tracking · Personal productivity · Docs & wiki
- **office-chat-phones** *(category added Nov 13)*: Email & office suites · Team chat · Video meetings · Business phone & online numbers (aliases: Business phone, Online numbers, VoIP, Virtual phone numbers)
- **website-builders-ecommerce** *(named "Website builders" since Nov 15; slug unchanged)*: Website builders · Landing page builders *("Ecommerce platforms" moved to ecommerce on Nov 15; before that the list was Website builders · Ecommerce platforms · Landing page builders)*
- **email-sms-marketing**: Newsletters & email campaigns · Marketing automation · SMS marketing · Email deliverability & verification *(new Nov 12)* · Business texting · Transactional email *(both new Nov 23)*
- **crm-sales**: Small business CRM · Sales pipeline · Sales outreach · Lead generation · Proposals & e-signature
- **design-creative**: Graphic design · Photo editing (alias: Photo editing & product shots) · UI & prototyping
- **accounting-invoicing**: Small business accounting · Invoicing & billing · Bookkeeping · Expense management · Receipt capture
- **web-hosting-domains**: Managed hosting · WordPress hosting · VPS & cloud · Domain registrars *(new Nov 12)*
- **customer-support-scheduling**: Help desk & live chat · Shared inbox · Scheduling & booking · Knowledge base *(new Nov 12)*
- **seo-marketing-tools**: SEO suites · Keyword research & content optimization *(Nov 12; replaces "Content optimization", which stays as an alias)* · Rank tracking · Analytics & reporting · Social media management (alias: Social scheduling)
- **financial-markets-trading** *(named "Investing & trading" since Nov 14)*: Charting & analysis · Brokers · Screeners & research (alias since Nov 12: Stock research & analysis) · Portfolio tracking · Backtesting · Social trading · Trading journals · Budgeting & net worth · Robo-advisors · AI stock research *(last three new Nov 14)*
- **crypto** *(category added Nov 14)*: Crypto tax software · Crypto exchanges · Hardware wallets · Crypto wallet apps · Crypto trading bots · Crypto portfolio trackers · Crypto cards
- **ecommerce** *(category added Nov 14)*: Ecommerce platforms · Print on demand · Inventory & order management (aliases: Multichannel listing, Inventory management) · Amazon seller tools · Shipping & fulfillment · Dropshipping · Sales tax & compliance · Returns management · Reviews & loyalty · AI product photos (alias: Photo editing & product shots)
- **cybersecurity-privacy** *(Nov 15)*: Password managers · VPN & privacy · Home security suites · Mobile antivirus · Mac antivirus · Parental controls · Identity theft protection · Data removal services · Business antivirus · Encrypted email — no aliases on the new labels. *(Retired Nov 15: "Antivirus & endpoint security", the Nov 12 merge of "Antivirus" and "Endpoint security" with aliases Antivirus, Endpoint security, Antivirus & endpoint; its old addresses redirect to Home security suites.)*
- **music-audio-production**: DAW · Plugins · Samples & loops · Mixing & mastering · Music distribution · Podcasting · Audio repair · AI music · Voice & audio

"AI app builders" = describe an app or website and get a working one, no coding needed; these tools are cross-listed in website-builders-ecommerce › Website builders.

Nov 12 label changes: Lovable commit ffcddeb (2.7 credits, 174 tests pass, six category pages + ESET checked at 1280/390). Old tile addresses (SEO content-optimization, cybersecurity antivirus and endpoint-security) redirect permanently to the new tiles. In preview until the owner publishes.

A new label needs a code change in `src/lib/subcategories.ts`; until then it will not show as a tile. When a bot uses a label that is not on a list, prefer adding an alias to an existing tile over creating a near-duplicate tile.

## 2. Pricing (`tools`)

| Field | Type | Notes |
|---|---|---|
| pricing_model | text | `free` / `freemium` / `subscription` / `one_time` / `credits` |
| has_free_plan, has_free_trial | bool | NOT NULL — `false` when not advertised |
| trial_days | int | null if no trial |
| trial_card_required | bool | |
| billing_unit | text | `per_seat` / `flat` / `usage` / `credits` |
| seat_minimum | int | default 1 (Asana 2, Teamwork 3–5, Recraft Teams 3) |
| pricing_tiers | jsonb | `[{ "name", "price_monthly_usd", "price_annual_per_month_usd", "unit", "included": [..] }]` |
| price_solo_usd | numeric | computed persona price, per month |
| price_team5_usd | numeric | computed persona price, per month |
| starting_price | text | existing; keep as display fallback only |
| price_verified_at | date | mandatory on verified listings |

## 3. Geo (`tools`)

| Field | Type | Notes |
|---|---|---|
| localised_pricing | bool | vendor shows local currency at checkout |
| price_solo_eur | numeric | only if vendor publishes EUR |
| regional_tiers | text | e.g. "AI Plus cheaper in 40+ emerging markets" |
| excluded_countries | text[] | ISO-2 |
| eu_data_hosting | text | `yes` / `enterprise_only` / `no` / `unknown` |
| dpa_available | bool | |

## 4. Ratings (`tools`)

| Field | Type | Notes |
|---|---|---|
| g2_score, g2_count | numeric, int | |
| capterra_score, capterra_count | numeric, int | |
| trustpilot_score, trustpilot_count | numeric, int | shown with count; big consumer AI brands sit at 1.2–1.6 for billing reasons — G2/Capterra are primary |
| ratings_verified_at | date | mandatory on verified listings |
| score_value, score_ease, score_depth, score_support | smallint 1–5 | editorial |
| category_scores | jsonb | AI tools & image creation `{ "text", "image", "video", "voice", "agents" }` (score ≥3 shows as a "Covers:" chip) · PM `{ "automation", "client_work" }` |

## 5. Community sentiment (`tools`)

| Field | Type | Notes |
|---|---|---|
| praise | text | one line, own words |
| complaint | text | one line, own words |
| sentiment_source_url | text | Reddit thread or review roundup |

## 6. Affiliate — admin only (`tool_affiliate_programs`, RLS: admin read/write)

| Field | Type | Notes |
|---|---|---|
| tool_id | uuid FK | |
| has_program | bool | |
| network | text | `partnerstack` / `impact` / `rewardful` / `dub` / `firstpromoter` / `cj` / `rakuten` / `in_house` / `none` |
| commission_terms | text | e.g. "25% of first year", "30% recurring ×12 mo" |
| cookie_days | int | |
| affiliate_geo | text | restrictions on who can be an affiliate |
| application_status | text | `none` / `applied` / `approved` / `rejected` |
| program_url | text | |
| notes | text | |

`affiliate_url`, `commission_rate`, `commission_flat` stay on `tools` (the `/go` redirect needs `affiliate_url`).

## 7. Editorial (`tools`)

| Field | Type | Notes |
|---|---|---|
| best_for | text[] | existing |
| features, pros, cons | text[] | existing |
| standout | text | the one thing it is uniquely good at |
| why_listed | text | for lesser-known tools: why it deserves a slot |
| alternatives | text[] | slugs |
| featured | bool | existing |

## Public tool page — section order

1. Hero: logo, name, tagline, "Listed in:" category links, "Covers:" chips, badges (free plan · trial · EU hosting), CTA
2. "What you'd pay": solo / team of 5 per month, billing unit, seat minimum, verified date, full tier table
3. External ratings strip: G2 · Capterra · Trustpilot with counts, verified date, links out
4. Editorial scores (4 bars + category axes)
5. What it is · standout capability · best for
6. Community sentiment: praise / complaint / source
7. Geo & compliance box
8. Pros / cons
9. Alternatives (same category)
10. CTA + disclosure

Basic listings (§0) use a trimmed page: hero, description, "Listed in:", the "not yet checked" note, website button, disclosure.

## Category page

Intro + Quick picks strip → subcategory tiles from the category's fixed list (count, from-price, highest rated) linking to `/category/<cat>/<sub>` → "All tools" grid (verified first, then basic). Sort: default (G2, ≥20 reviews) · solo price · team-of-5 price · G2 score · value score — applied within each tier. Labels are computed from data only (Highest rated · Cheapest for one person · Cheapest for a team of 5 · Top-rated free plan), verified listings only.
