# Subsmarket — Strategy v2: the ladder, the differentiator, the catalog

Rewritten 2026-11-12 (v1 was 2026-10-30). Companion to `roadmap.md` (state and next steps), `differentiation-brief.md` (the monitor and the "why not just ask an AI" answer), `category-map.md` (what the catalog must cover) and `listing-schema.md` (how data is shaped).

## 1. The ladder (owner's vision, Nov 12)
1. **Traffic** — nothing else works without visitors. Baseline Oct 10–Nov 9: 36 visitors.
2. **Affiliate income** — the first money, earned from visitors who click through to a tool.
3. **The monitor habit** — people come back because Subsmarket shows them, in one place, what they pay for subscriptions across all their cards and payment methods. This is the differentiator and the reason to create an account.
4. **Buy and bundle** — the end goal: people buy subscriptions on Subsmarket and bundle them. The pitch to vendors needs proof: traffic, click and conversion numbers, and "what people actually pay for" data from the monitor.

Each step funds and proves the next. Do not skip ahead: no reselling, no payments, no bank licence until steps 1–3 show real numbers.

## 2. How the big sites earn (so we copy the right thing)
- **Capterra**: free for buyers; software vendors pay per click for sponsored positions (bids start around $2 a click, per third-party guides). It lists 900+ categories. Source: Capterra FAQ "Why is Capterra free?", Capterra categories page, Wikipedia (checked Nov 12).
- **AppSumo**: sells discounted software deals itself (many are one-time "lifetime" deals) and keeps a share.
- **What this means for us**: affiliate links are our stage-2 income. Later income, in order: Subsmarket-only discount codes → labelled sponsored placements once a vendor actually pays → resale and bundles. Never fake "sponsored".

## 3. Differentiation — what we offer that they don't
The owner's core worry: competitors have years of head start, and anyone can ask their own AI assistant. Our answer is to be the place that knows **your** subscriptions and the **real, dated** price of everything else.

| We offer | Capterra / G2 | AppSumo | A general AI chat |
|---|---|---|---|
| **Subscription monitor**: one view of what you pay across cards and methods, with renewal and price-rise alerts | No | No | Does not watch your money over time |
| **Real cost**: what one person and a team of 5 pay per month, dated, with price history | Vendor-entered "starting at" prices | Deal prices only | Prices can be out of date and undated |
| **Europe first**: EUR prices, EU hosting, GDPR, e-invoicing | Weak | Weak | Generic |
| **Buy or build**: Solutions pages with free / paid / build-it-yourself options and build kits | No | No | Can help, but with no tested kit or price comparison |
| **Not pay-to-rank**: labels computed from data only | Paid positions | Sells its own deals | Not applicable |
| **Later: buy and bundle** in one checkout | No | Single deals | No |

Rules that follow:
- The monitor is the signature product, not a side page. Every other feature should feed it or be fed by it (cheaper swaps → affiliate clicks; saved lists → demand data for the bundle pitch).
- Work **with** AI assistants: be the source they cite (dated plain sentences, `/llms.txt`, bots allowed) and consider a Subsmarket connector for AI assistants later.
- "Build it yourself" content is a traffic hook and earns through app-builder affiliate programs (Lovable, Base44 pay about $100 per first purchase). It is a side door, not the core.

Details, ideas and open questions: `differentiation-brief.md`.

## 4. The catalog — bigger, guided by competitors (owner decision Nov 12)
385 published listings (Nov 12) is not enough against competitors. Grow it, and use competitor sites as the map instead of inventing the structure.

**What we take from competitors (Capterra, G2, AppSumo, Product Hunt, AlternativeTo):**
- Which categories and subcategories buyers expect.
- Which tools exist in each (name and website only).

**What we never take:** their descriptions, feature lists, pros and cons, review text, screenshots or images, and no bulk copying of their pages. Reasons: copyright and their terms of use, Google ranks copied text poorly, and our own data rules. Every fact on a listing still comes from the vendor's own pages; ratings stay score + count + link.

**Coverage before count:** `category-map.md` lists every category, its subcategories, how many tools each has and the gaps. Bots fill the thinnest subcategories first. A tool goes in every category where a buyer would look (max 3).

**Two speeds (planned, not built yet):**
| Tier | Fields | Shown to Google? |
|---|---|---|
| **Basic** | name, website, tagline, categories, labels, logo, pricing model if obvious | No (noindex) and a visible "basic listing — not yet verified" badge |
| **Verified** | full schema with sources and dates | Yes |
| **Editorial** | featured, affiliate link live | Yes |

Basic listings let the catalog look complete quickly; only verified ones are pushed to Google, because Google penalises thousands of thin auto-made pages.

**Verification order:** tools people search "<tool> pricing" / "<tool> alternatives" for → tools with an affiliate program → thinnest subcategories → stale listings.

**Targets:** every subcategory at least 8 tools; 1,000 listings (basic + verified) by end of January 2027, at least half verified. (v1 targets of 2,000 by end-January were not on track: 385 on Nov 12.)

## 5. Validity process (unchanged from v1)
1. **Provenance**: `sources` per tool (pricing page, G2, Capterra, Trustpilot, sentiment, affiliate), shown collapsed on the page.
2. **Tiering and authorship**: `data_tier` (basic | verified | editorial), `created_by` (grok | claude | admin), `last_checked_at`.
3. **Price history**: `tool_price_history`, appended on every verification. Enables price-change pages, alerts and a monthly "SaaS price changes" report.
4. **Re-verification**: top 500 by traffic every 60 days, others every 180.
5. **Geo**: visitor country on advisor questions and /go clicks; `tool_prices_by_country` when vendors localise; `excluded_countries`, `eu_data_hosting`, `dpa_available` mandatory in verified rows.
6. **Approval gate**: verified rows may auto-publish; weekly 10% spot-check.
7. **Corrections**: listing requests route vendor and visitor fixes into /admin.
8. **Never**: copy review text; show a number without a date; publish an affiliate commission figure on a public page.

## 6. Traffic (stage 1)
In order:
1. Pages generated from the catalog: "X pricing", "X alternatives", "X vs Y", "Best X for…".
2. The monitor as the launch hook: Product Hunt, SaaSHub, AlternativeTo, BetaList.
3. Solutions pages answering real pain-point questions; share them where the questions are asked (Reddit, LinkedIn).
4. "Build it yourself" guides.
5. Original data that earns links: monthly price-changes report, EU hosting index, cheapest tools for a team of 5.
6. A Greek page on myDATA e-invoicing apps.

SEO and AI-search rules (unchanged): index only verified tool pages, alternatives, compare, category, subcategory and changes pages; structured data (SoftwareApplication + Offer, BreadcrumbList, FAQPage, ItemList; no aggregateRating unless it is our own data); canonical URLs; sitemap with lastmod = verified date; `/llms.txt`; allow GPTBot, PerplexityBot, ClaudeBot, Google-Extended; keep verified dates in plain text. Expect 3–6 months before meaningful search traffic on a new domain.

## 7. Toward buy and bundle (what to collect now)
- Tiers that map to products for sale, per-country prices and currencies, tax notes, trial terms.
- Vendor relationships: claim channel → affiliate programs → exclusive codes → reseller agreements.
- Demand data: advisor questions, clicks, countries, and (with consent, in aggregate only) what monitor users pay for.
- Proof for the pitch: visitors, clicks, conversions per vendor.

## 8. Build order (each step only after "build it")
1. Category map agreed → bots re-pointed at gaps; basic/verified tiers in the database.
2. Monitor v2 (see `differentiation-brief.md`).
3. Alternatives, pricing and compare pages from the catalog.
4. Email sign-up with renewal and price-drop alerts.
5. Price history and the monthly report.
6. Exclusive codes, then labelled sponsored placements, then the bundle pilot.
