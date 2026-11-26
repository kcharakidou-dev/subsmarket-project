# Subsmarket — Differentiation brief (for the dedicated chat)

Written 2026-11-12; founding insight added 2026-11-13. Read with `strategy.md` §3. Nothing here is decided or built unless marked "live". Ideas marked "to check" need research before anyone relies on them.

## The founding insight (owner, Nov 13) — core of the project
Why the owner wanted this app two years ago: **not because she couldn't search for an app, but because she had to install it to find out its limitations.**

Subsmarket's job is to tell people the limits *before* they sign up or install: what the free plan really allows, what the cheap tier leaves out, what only shows up after you start using it. Every listing, the advisor and every page should be judged against this: **does it save the visitor from installing something to discover it doesn't do what they need?**

What this means in practice:
- A "free plan" yes/no flag is not enough; the limits of that plan are the valuable part.
- Each subcategory has a few **deciding facts** (the things that make or break the choice), verified on the vendor's own site and dated.
- The advisor uses common sense: works out what matters for the request, asks one question when the answer changes the result, drops tools that fail the need and says why, and says "not verified" rather than guessing.
- When nothing fits, say so plainly and offer the nearest option.

How it was found: on Nov 13 the owner searched for a free VPN to connect to the USA. The advisor's only suggestion was Proton VPN, whose free plan picks the country for you, which she only learned after clicking through. Pilot proposed on VPN & privacy first, then other subcategories (see `roadmap.md`).

## The question
Competitors have years of experience and far more listings, and anyone can ask their own AI assistant for a recommendation. What does a visitor gain from Subsmarket that they cannot get elsewhere?

Working answer: **Subsmarket tells you the limits before you install, shows everything you pay for, and what you should be paying.** Parts to develop:
0. Limits before you install (the founding insight above).
1. The subscription monitor (main differentiator for coming back).
2. A clear reason to use Subsmarket even if you have Claude, ChatGPT or Gemini.

## Part 1 — The subscription monitor

### The owner's own pain (the story to tell)
She found she was paying far more than she realised, because the charges were spread over different cards and different payment methods. Nothing showed the total in one place.

### Why it is hard
- Charges sit on several cards, bank accounts, PayPal, Apple and Google Play.
- Statement names are cryptic (e.g. "OPENAI *CHATGPT").
- Yearly charges are forgotten; free trials turn into paid plans; prices rise quietly.
- Work and personal subscriptions get mixed.

### What is live today (finder v1, Nov 7)
- /subscription-finder: drop one bank-statement CSV; it is read in the browser and never sent to the server.
- Recurring charges are detected and matched to catalog tools by billing names.
- Report: subscriptions found, monthly and yearly totals, overlaps, annual-billing hints, free alternatives, how to cancel.
- Signed-in users can save the extracted list (never the statement). Data in Ireland (EU).
- Not yet tested with the owner's own bank export.

### Ideas to take it further (to discuss, in rough order of effort)
| Idea | What the user gets | Flags |
|---|---|---|
| **Several statements at once** | Drop files from every card and bank; one merged total | Small step from v1; needs duplicate handling |
| **One big number first** | "You spend €X a month, €Y a year on N subscriptions" at the top, details below | Design only |
| **Quick-add from the catalog** | Tick the tools you use, enter the price or accept the list price; no statement needed | Easy; less accurate |
| **Renewal calendar and alerts** | Email before a yearly renewal, a trial ending or a price rise | Needs an email provider; the reason to keep an account |
| **Cheaper-swap suggestions** | "You pay €30 for X; Y does the same for €12" | This is where the monitor earns affiliate income; must stay honest (data-only, not commission-led) |
| **PDF statements** | Works for banks with no CSV export | Roadmap says: only with clear consent and immediate deletion |
| **Receipt forwarding** | Forward receipts to a personal Subsmarket address; catches PayPal, Apple, Google Play | We would process emails on the server: privacy wording and consent needed |
| **Inbox scan** | Connect Gmail/Outlook, find receipts automatically | Heavy: provider security review, high trust barrier — to check |
| **Bank connection through a licensed provider** | Automatic, always up to date | Roadmap decision Nov 7: no direct bank connections (regulated under PSD2). Using a licensed provider may be possible — to check with a lawyer before considering |
| **Shareable savings card** | "I found €480 a year of forgotten subscriptions" image, no personal data | Free marketing |
| **Team view** | A small business sees every tool the team pays for, by person | Later; strong for the bundle pitch |

### How the monitor feeds the ladder
- **Traffic**: it is the launch hook and the thing worth sharing.
- **Affiliate income**: swap suggestions and "you might not need this" lead to tool pages.
- **Bundle pitch**: with consent and only in aggregate, it shows what people really pay for and which tools go together.

### Competitors to study first (to check — names from general knowledge, not yet researched)
Subscription trackers such as Rocket Money (US), Bobby, and bank-app features that list recurring payments. Questions: what do they charge, do they work in the EU, do they compare prices or suggest alternatives (our edge), how do they get the data?

### Open questions for the owner
1. **Personal subscriptions too** (Netflix, Spotify, gym) **or only work software?** Her own story was personal; the catalog is work tools. Personal ones have few affiliate programs but make the total meaningful. (Asked Nov 12, not yet answered.)
2. Free for everyone, or a paid tier later (e.g. alerts, several statements)?
3. How much are we willing to process on the server (receipts, PDFs), given the privacy promise is a selling point?
4. Greek and EU banks first? Which export formats?

## Part 2 — "Why not just ask my own AI?"

### What a general AI chat lacks (our angles)
- **Verified limits before you install**: a general AI often names a tool without knowing what its free or cheap plan actually allows today; ours are checked on the vendor's site and dated (founding insight).
- **Memory of your money over time**: it does not track your renewals or warn you.
- **Dated, checked prices**: ours carry a date and a source; price history shows rises.
- **Local detail**: EUR pricing, EU hosting, Greek e-invoicing.
- **Deals**: Subsmarket-only discount codes (once programs approve us).
- **One place to act**: compare, click through, and later buy and bundle.

### Ideas (to discuss)
- **"Build it yourself" content**: for each common need, an honest page — buy it (cost), or build it with an AI app builder (time, cost, a tested prompt kit). Earns through app-builder affiliate programs. Already started as "build kits" on Solutions pages; kits need hands-on testing before charging.
- **Be the AI's source**: `/llms.txt`, plain dated sentences, so assistants cite Subsmarket.
- **A Subsmarket connector for AI assistants**: let people ask "what does X cost for 5 people?" from inside their own assistant, with our data. Brings the brand to where people already are — to check effort.
- **"Ask your AI, then check here"**: a page that takes an AI's recommendation and shows the real current prices and cheaper equivalents.
- **Prompt packs**: ready prompts to get more from the AI subscription you already pay for (traffic, email sign-ups).

## How to run the dedicated chat
1. Research the competitors above and what users complain about (own words, sources, dates).
2. Pick 2–3 monitor ideas to prototype as a design draft; owner reacts.
3. Decide open question 1 first — it changes the design and the catalog.
4. Only then write the Lovable request, after "build it".
5. Record decisions in `roadmap.md` and move settled items from this brief into `strategy.md`.
