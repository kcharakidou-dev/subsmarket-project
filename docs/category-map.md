# Subsmarket — Category map

Updated 2026-11-21 (~17:00, chat): **ranked list for both Grok bots (HQ #4) — section 0a**; the owner upgraded the Grok plan, bot B starts. Updated 2026-11-15 (~19:50): **Website builders split from Ecommerce** and the new tiles **published**; Grok now follows a 7-day plan (see `grok-bot.md`). ~16:55: antivirus is NOT a separate category — its labels live under Cybersecurity & privacy (owner's correction). 2026-11-14 (~23:30): plan for Crypto, Ecommerce, Investing, Antivirus (section 0). Draft 1 of Nov 12 follows below it (its counts are out of date).

## 0a. Ranked list for the bots (Claude, 2026-11-21; owner's rule from HQ #4)

**How it is ranked:** affiliate pay (how many of our listings have a known affiliate program; recurring-commission categories score higher) × search demand (US monthly searches and cost per click from Ubersuggest, Nov 14 and Nov 21; a high cost per click = a valuable visitor) × how thin we are (targets: 40 listings per category, 8 per label). Counts below = all rows, published or not, on Nov 21 ~16:50 Athens. Claude keeps this list; the owner can reorder it at any time.

### Bot A — one category day each, from Mon Nov 23 (50 verified + up to 50 basic; fewer is fine)
Bot A had its days for Crypto, Ecommerce, Investing & trading and Cybersecurity (antivirus labels) on Nov 15–22. Next:

| # | Day | Category (slug) | Listings | Labels under 8 | Known affiliate programs | Demand (US/month, cost per click) |
|---|---|---|---|---|---|---|
| 1 | Mon Nov 23 | Email & SMS marketing (`email-sms-marketing`) | 29 | Deliverability & verification 5 | 30 of 31 | "email marketing software" 135,000, $83 |
| 2 | Tue Nov 24 | Web hosting & domains (`web-hosting-domains`) | 23 | Managed hosting 5 · VPS & cloud 5 · Domain registrars 5 | 23 of 25 | "web hosting" 135,000, $28 (hosting pays some of the highest one-off commissions) |
| 3 | Wed Nov 25 | CRM & sales (`crm-sales`) | 31 | Lead generation 4 · Sales pipeline 5 · Sales outreach 5 · Proposals & e-signature 6 | 27 of 34 | "small business crm" 4,400, $49 · "lead generation software" 720, $54 |
| 4 | Thu Nov 26 | SEO & marketing tools (`seo-marketing-tools`) | 30 | SEO suites 5 · Social media management 5 · Rank tracking 7 · Analytics & reporting 7 · Keyword research 7 | 27 of 31 | "seo tools" 165,000, $24 |
| 5 | Fri Nov 27 | Accounting & invoicing (`accounting-invoicing`) | 30 | Receipt capture 3 · Bookkeeping 5 · Expense management 5 · Small business accounting 7 | 18 of 32 | "accounting software for small business" 18,100, $44 |
| 6 | Sat Nov 28 | Office, chat & phones (`office-chat-phones`) | 13 | Video meetings 1 · Team chat 2 · Email & office suites 3 · Business phone 7 | 9 of 13 | "virtual phone number" 18,100, $21 · "video conferencing software" 5,400, $33 (few credible tools per label: expect fewer than 100) |
| 7 | Sun Nov 29 | Customer support & scheduling (`customer-support-scheduling`) | 30 | Knowledge base 5 · Shared inbox 5 · Scheduling & booking 7 | 22 of 27 | "help desk software" 5,400, $108 |
| 8 | Mon Nov 30 | Website builders (`website-builders-ecommerce`) | 26 | Landing page builders 5 | 19 of 25 | "website builder" 201,000, $29 (only 2 labels) |
| 9 | Tue Dec 1 | Design & creative (`design-creative`) | 36 | UI & prototyping 7 | 20 of 35 | "graphic design software" 14,800, $11 |
| 10 | Wed Dec 2 | Music & audio production (`music-audio-production`) | 27 | AI music 1 · Podcasting 3 · Audio repair 3 · DAW 4 · Plugins 5 · Mixing 6 · Distribution 6 · Samples 7 · Voice 7 | 22 of 49 | "ai music generator" 90,500 but $4.50 · "music production software" 14,800, $6 (traffic, low pay) |

After Dec 2: AI tools (132), Project management (111) and Image creation (67) are already the biggest; Claude writes the next list before Dec 2. New main categories (section 4: HR & payroll, Online courses, File storage, Forms…) slot in only after the owner says yes to each.

### Bot B — fill categories that have had their day (20 a day, 20:00 Athens, from Sun Nov 22)
- **Lane:** Crypto, Ecommerce, Cybersecurity & privacy, and Investing & trading (after its Nov 22 day); from Nov 23, each category from the bot A list once its day has passed. Never the category bot A works on that day.
- **Choosing labels each run:** count listings per fixed label in the lane (published or not). Labels under 8 first, then under 15. Within each step these go first, in this order: Password managers · VPN & privacy · Identity theft protection · Data removal services · Mac antivirus · Mobile antivirus · Sales tax & compliance · Returns management · Print on demand · Dropshipping · Budgeting & net worth · Robo-advisors · Crypto tax software · Crypto portfolio trackers · Crypto cards; then the rest, thinnest first. About 5 per label, so about 4 labels a run.
- **Where tools come from:** leftover `new` names in the listing queue (`tool_candidates`) for those labels first, then the usual search (PartnerStack → Claude's connectors → directories). When credible tools run out for a label, move on; never pad.
- **Labels under 8 in the lane on Nov 21:** Encrypted email 1 · Social trading 1 · AI product photos 2 · AI stock research 4 · Mac antivirus 5 · Budgeting & net worth 6 · Returns management 6 · Print on demand 6 · Mobile antivirus 7 · Password managers 7 · Robo-advisors 7 · Dropshipping 7 (today's Ecommerce runs and Sunday's Investing day will fill some).

## 0. New-category plan (owner decision Nov 14, corrected Nov 15)

**Owner's priority order:** 1 Crypto · 2 Ecommerce · 3 Investing · 4 Antivirus (inside Cybersecurity). Since Nov 15 Grok fills them on a 7-day plan (one category per day, Nov 16–22), then follows the ranked list in section 0a (Nov 21) — details in `grok-bot.md`.

**Demand data:** Ubersuggest (owner's account, connected Nov 14; Individual plan €29/month, trial). US monthly searches and the price advertisers pay per click (CPC), read Nov 14. A high CPC = a valuable visitor. European numbers (DE, UK) not yet pulled.

**Database (Nov 14–15):** categories `crypto` (Crypto) and `ecommerce` (Ecommerce) created; `financial-markets-trading` renamed **"Investing & trading"**; `website-builders-ecommerce` renamed **"Website builders"** (slugs unchanged). Ecommerce › Ecommerce platforms: Shopify, WooCommerce, BigCommerce, Big Cartel, PrestaShop, Sellfy, Gumroad (Ecommerce only) and Wix, Squarespace, Ecwid (also in Website builders). A category `antivirus-device-security` was created Nov 14 by mistake and **deleted Nov 15** with its 6 links; the 6 tools keep the labels "Home security suites" (Bitdefender, ESET, Emsisoft) and "Business antivirus" (CrowdStrike Falcon, SentinelOne, ThreatDown) under Cybersecurity.
**Code (Lovable, published Nov 15 ~17:25, deployment f289d87a):** label lists below in `src/lib/subcategories.ts`; Cybersecurity's "Antivirus & endpoint security" tile retired (old addresses redirect to Home security suites); Website builders' labels = Website builders · Landing page builders (the old Ecommerce platforms tile address redirects to Ecommerce › Ecommerce platforms).
**Listings so far:** 44 crypto listings from Grok's Sunday Nov 15 run, unpublished (Crypto stays hidden on the site until one is published).

### Crypto (`crypto`)
| Subcategory label | US searches/mo | CPC | Note |
|---|---|---|---|
| Crypto tax software | 4,400 | $32 | Best fit: real subscription, priced per tax year (Koinly, CoinLedger, CoinTracker, CoinTracking, Summ) |
| Crypto exchanges | 74,000 head term | $20 | Brand names own the head term; aim at "lowest fees" (1,900), "for beginners", "regulated". Many have no subscription; Coinbase One and Kraken+ are paid memberships |
| Hardware wallets | 4,400 + ~15,000 ("hardware wallet for crypto") | $5 | One-time purchases (Ledger, Trezor, Tangem, Keystone) |
| Crypto wallet apps | 2,900 | $23 | Mostly free |
| Crypto trading bots | 1,900 | $12 | Subscriptions (3Commas, Cryptohopper, Coinrule, Pionex); "AI trading bot" growing |
| Crypto portfolio trackers | 880 | $12 | Fits the vault idea |
| Crypto cards | 1,900 | $8 | Niche |
Left out on purpose: signal / Telegram groups (~1,600, scam-heavy), no-KYC exchanges (legal risk). Screeners, staking, news apps < 500 each — later.

### Ecommerce (`ecommerce`)
| Subcategory label | US searches/mo | CPC |
|---|---|---|
| Ecommerce platforms (10 today) | 14,800 | $17 |
| Print on demand | 22,200 | $9 |
| Inventory & order management (aliases: Multichannel listing, Inventory management) | 14,800 | $74 |
| Amazon seller tools (product research 480, PPC 260, repricer 210, profit calculator 720; "amazon seller tools" 2,900) | ~4,500 | $10–28 |
| Dropshipping | 1,000 | $20 |
| Shipping & fulfillment | 880 | $44 |
| Sales tax & compliance | 480 | **$368** |
| Returns management | 260 | $145 |
| AI product photos (alias: Photo editing & product shots; cross-list with image-creation) | 390 | $16 |
| Reviews & loyalty | 170 | $4 |
The owner works in Amazon selling and can add more Amazon subcategories; "Amazon seller tools" may later split (product research · ads/PPC · repricing · analytics & profit).

### Website builders (`website-builders-ecommerce`, "Website builders" since Nov 15)
Labels: Website builders · Landing page builders. AI app builders (AI tools label) are cross-listed here as "Website builders". Store platforms do not belong here — only tools that are both a site builder and a shop (Wix, Squarespace, Ecwid type) sit in both categories.

### Investing (`financial-markets-trading`, "Investing & trading")
| Subcategory label | US searches/mo | CPC | Today |
|---|---|---|---|
| Budgeting & net worth (new) | **110,000** | $6 | 0 (YNAB, Monarch, Empower, Copilot…) |
| Brokers (investing apps) | 18,100 ("investing app"), options platforms 1,900 / $23 | $12 | 2 |
| Screeners & research | 12,100 ("stock screener") | $5 | ~8 |
| Robo-advisors (new) | 8,100 | $17 | 0 |
| Trading journals | 5,400 | $4 | 5 |
| AI stock research (new) | 1,300 ("ai stock picker") | $8 | 0 |
| Portfolio tracking (dividend tracker 1,300) | 880 | $9 | ~8 |
| Charting & analysis / Backtesting | 390 each | $18 / $8 | covered |
Also: enrich the existing listings (several have no structured price: eToro, Finviz, Interactive Brokers, TradingView, getquin). Grok does not update rows — Claude does this separately.

### Antivirus — labels inside Cybersecurity & privacy (`cybersecurity-privacy`)
Full Cybersecurity list (Nov 15): Password managers · VPN & privacy · **Home security suites · Mobile antivirus · Mac antivirus · Parental controls · Identity theft protection · Data removal services · Business antivirus** · Encrypted email. No aliases on the antivirus labels (aliases double-counted on Nov 14).
| Subcategory label | US searches/mo | CPC |
|---|---|---|
| Parental controls | 40,500 | $7 |
| Identity theft protection | 33,100 | $38 |
| Mobile antivirus | 27,100 (Android) | $17 |
| Data removal services | 12,100 (up from 1,600 a year ago) | $13 |
| Home security suites (3 today) | 6,600 ("best antivirus"), "free antivirus" 14,800 | $15 |
| Mac antivirus | 4,400 | $26 |
| Business antivirus (3 today) | 1,300 | $44 |
Rule: every listing shows first-year AND renewal price; persona prices use the renewal price. Kaspersky: new US consumer sales banned. "Free antivirus" is a filter (has_free_plan), not a label.

### SEO & marketing tools — what it covers (owner's question, Nov 15)
Ranking on **Google**: SEO suites, keyword research, rank tracking, analytics; plus "Social media management". Amazon ranking tools go in Ecommerce › Amazon seller tools. Social media as its own category: open question.

---

## 1. Current categories (published tools, Nov 12 — out of date)
| Category | Tools | Who fills it |
|---|---|---|
| AI tools | 102 | Claude scheduled task |
| Project management & productivity | 81 | Claude scheduled task |
| Image creation | 51 | Claude scheduled task |
| Website builders & e-commerce (now "Website builders") | 26 | Grok |
| CRM & sales | 25 | Grok |
| Design & creative | 24 | Grok |
| Accounting & invoicing | 23 | Grok |
| Music & audio production | 22 | Grok |
| SEO & marketing tools | 20 | Grok |
| Email & SMS marketing | 19 | Grok |
| Customer support & scheduling | 18 | Grok |
| Cybersecurity & privacy | 15 | Grok |
| Financial Markets & Trading (now "Investing & trading") | 14 | Grok |
| Web hosting & domains | 13 | Grok |

Nov 14 counts: AI tools 131 · PM 93 · Image 54 · CRM, Website builders, SEO 30 each · Accounting, Support, Design, Email, Investing 29 each · Music 27 · Cybersecurity 24 · Hosting 23 · Office, chat & phones 13 · Ecommerce 10 (cross-listed). Website builders lost 7 store platforms on Nov 15 (→ about 23).

Nov 21 counts (all rows, published or not): AI tools 132 · Project management 111 · Crypto 114 · Ecommerce 101 · Cybersecurity 101 · Investing 78 · Image 67 · Design 36 · CRM 31 · Accounting, Support, SEO 30 each · Email 29 · Music 27 · Website builders 26 · Hosting 23 · Office, chat & phones 13. Per-label counts: section 0a.

## 2. Thin subcategories (fewer than 5 tools, Nov 12) — fill these first
(Out of date — see section 0a for the Nov 21 counts.)
- **1 tool**: Endpoint security · Antivirus · Encrypted email · Backtesting · Social trading · AI music
- **2 tools**: Small business accounting · Analytics & reporting · Content optimization · Portfolio tracking · Brokers · Samples & loops · UI & prototyping
- **3 tools**: Marketing automation · Audio repair · Podcasting · Receipt capture · Social scheduling
- **4 tools**: DAW · Lead generation · Sales pipeline · Screeners & research · Charting & analysis · Help desk & live chat

## 3. Label problems seen in the data
- "Logo & brand design" is on 3 tools but is not in any category's fixed list (so it shows in no tile). Decide: add it to Design & creative, or relabel to "Logos & vectors" / "Graphic design".
- "Social scheduling" (3) is an alias of "Social media management" (5) — merge to one label.
- "Photo editing" (6, Design) and "Photo editing & product shots" (8, Image creation) are aliases — fine, but check tools are not double-counted.
- Roadmap item still open: published tools with no label for one of their categories (e.g. Webflow had none under Website builders on Nov 14).
- The 6 antivirus tools still also carry the old labels ("Antivirus", "Endpoint security", "Antivirus & endpoint") — harmless, no tile matches them now.

## 4. Candidate new categories (seen on Capterra / G2 / AppSumo; owner to confirm)
| Candidate | Example tools (names only, to verify) | Note |
|---|---|---|
| **Team communication & video meetings** | Slack, Zoom, Google Meet, Microsoft Teams, Loom | Done Nov 13 as "Office, chat & phones" |
| **Automation & integrations** | Zapier, Make, n8n | Could be a label under AI tools › AI agents & automation instead |
| **Video creation & editing** | CapCut, Descript, Veed | Roadmap already asks: own category? |
| **HR, payroll & hiring** | Gusto, Deel, BambooHR, Personio | Strong affiliate programs; EU angle (Personio) |
| **File storage & backup** | Dropbox, Google Drive, pCloud, Backblaze | Common forgotten subscriptions |
| **Forms & surveys** | Typeform, Tally, Jotform | Often built yourself — fits "buy or build" |
| **Email & office suites** | Google Workspace, Microsoft 365, Proton, Zoho Workplace | Covered by "Office, chat & phones" |
| **Online courses & memberships** | Teachable, Kajabi, Thinkific, Podia | Solo creators; good commissions |
| **Social media management** | Buffer, Hootsuite, Later | Today a label under SEO |
| **Analytics & dashboards** | Plausible, Hotjar, Looker Studio | EU-hosted options are a selling point |
| **Developer tools** | GitHub, Vercel, Supabase | Maybe later |
| **Personal subscriptions** (streaming, music, news, fitness) | — | Only if the monitor covers personal spending |
Rule since Nov 15: Claude creates a main category only after the owner has explicitly said yes to it.

## 5. Targets
- Every subcategory: at least 8 tools.
- Every category: at least 40 tools.
- Each tool listed in every category where a buyer would look (max 3).
- Overall: 1,000 listings by end of January 2027 (see `strategy.md` §4).

## 6. How the bots use this map
1. Before each run, count tools per subcategory and pick where to fill: Grok bot A follows the category days in section 0a (from Nov 23); Grok bot B follows the bot B rules in section 0a.
2. Discover candidates from competitor category pages (names and websites only), skip anything already in `tools` (slug or domain).
3. Research each tool from the vendor's own pages per `grok-listing-brief.md`.
4. Cross-list per the multi-category rule.
5. Refresh the counts in this doc monthly (or when a category is added).

## 7. Rule for using competitor sites
Take: category names and structure, and which tools exist (name + website).
Never take: descriptions, feature lists, pros and cons, review text, images or screenshots; no bulk copying of pages. All facts come from the vendor's own pages; ratings are score + count + link, dated.
