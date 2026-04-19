# Business brief: {Your brand}

> This file is the business brief Claude Code loads automatically on every session start. It grounds every sub-playbook the master install produces in your brand's specifics.
>
> **Two ways to populate it:**
>
> **Option A (fastest, recommended).** Leave the file as-is (or delete it entirely). Run the `gtm-master-playbook.md` install prompt and Claude interviews you conversationally, asks every question below, and fills in the file for you as you go. Takes about 10 minutes. You answer questions in plain language; Claude writes the structured brief.
>
> **Option B (DIY).** Fill in every `{placeholder}` yourself before running the install. Keep it tight: one to two sentences per field. Use founder voice over marketing copy.
>
> Either way the end state is the same: a populated `CLAUDE.md` that every sub-playbook (SEO audit, paid ads, email, weekly review, and the other thirty) reads from.

---

## Brand overview

- **Brand name**: {Your brand name}
- **Primary URL**: {https://yourbrand.com}
- **Domain age**: {How long the domain has been live, e.g. "launched March 2025" or "ten years"}
- **Ecommerce platform**: {Shopify / WooCommerce / Custom / etc.}
- **Geographic focus**: {US, UK, EU, global, etc.}
- **Stage**: {Pre-launch / first year / established with trading history / mature}

## Product

- **What you sell (one sentence)**: {e.g. "Launch-monitor-backed short-game training systems for club golfers improving wedge consistency."}
- **Price range**: {e.g. "£500 to £1,200. AOV £650."}
- **Catalog size**: {Number of active SKUs or product lines}
- **Distinctive or patented elements**: {What makes this product materially different from alternatives}
- **Margin structure**: {COGS ballpark, shipping costs, any surprising margin drags}

## Target audience

- **Core buyer (one sentence)**: {e.g. "Club golfers in the US aged 35 to 55 frustrated by inconsistent wedge distances inside 100 yards."}
- **Secondary buyer (if any)**: {Second audience segment if material}
- **What they hire you to do (Jobs-to-be-Done framing)**: {The functional, emotional, and social jobs your product solves}
- **Where they hang out online**: {Reddit subs, niche forums, YouTube channels, Instagram accounts, podcasts}

## Positioning

- **Why you win (one sentence, in your words)**: {What you do that nobody else does, or do better}
- **Three competitors the buyer also considers**: {List 3 to 5 competitors with URLs. These feed the competitor-audit and content-gap sub-playbooks directly.}
  - {competitor 1 URL}
  - {competitor 2 URL}
  - {competitor 3 URL}
- **Pricing tier vs category median**: {e.g. "priced 3x category median" or "premium of the category" or "value tier"}
- **What has been tried and did not work**: {Previous positioning angles, channels, campaigns that missed}

## Current tool stack

List every tool you use for marketing and operations today. Claude detects which have API credentials wired in `.env` and offers sign-up walkthroughs for the rest during the install.

- **Website / CMS**: {Shopify, WordPress, Next.js, etc.}
- **Analytics**: {GA4, Mixpanel, etc.}
- **Search visibility**: {Google Search Console, Bing, etc.}
- **Ad platforms**: {Google Ads, Meta Ads, TikTok, etc.}
- **Shopping feed**: {Google Merchant Center, Bing Merchant}
- **Email / SMS**: {Klaviyo, Brevo, ActiveCampaign, Postscript, etc.}
- **CRO / session behaviour**: {Microsoft Clarity, Hotjar, FullStory}
- **Tag management**: {GTM, Shopify Pixel Manager}
- **CRM / back-office**: {Airtable, HubSpot, custom}
- **AI assistants / prompts**: {Claude, ChatGPT, internal tools}

## Tools you'd like to add

Which tools do you want wired into the operating system that you don't have yet? Claude uses this list during the install to prioritise the sign-up walkthroughs.

- {Tool 1 and why: e.g. "Ahrefs for backlink intel once I justify the $129/mo"}
- {Tool 2 and why}

## Team size and marketing owner

- **Total team size**: {Head count today}
- **Team by function**: {Founders, product, ops, support, marketing}
- **Who runs marketing today**: {Founder / in-house growth lead / fractional / agency / nobody formally}

## Most-felt marketing pain right now

Name the single most-felt marketing pain in your own words. One paragraph. Example: "Meta Ads ROAS has fallen from 4.2 to 1.8 in the last six weeks and I can't tell whether it's the creative, the audience saturation, or iOS 18 tracking loss."

{Your answer}

## Current approach to weekly review

How do you currently review marketing performance week-over-week? Pick the closest match or describe your own pattern.

- {None, we just look at dashboards ad-hoc}
- {Slack standup every Monday}
- {Agency sends a weekly PDF report}
- {I export data into a personal Google Sheet}
- {Other: describe}

## Comfort level with Claude Code

Pick the closest match. The install prompt calibrates its handholding based on this.

- {New: I installed Claude Code this week}
- {Used some: I've run a few sessions}
- {Power user: I have CLAUDE.md files and slash commands wired up across multiple projects}

## Known constraints

- **Capital**: {Funded / bootstrapped / pre-revenue / cash-flow runway if relevant}
- **Supply chain**: {Any sourcing, manufacturing, or inventory constraints that shape growth pace}
- **Regulatory or compliance**: {FDA, DSHEA, BIS hallmarking, country-specific rules, etc.}
- **Time**: {Founder time available for this work, any seasonal or launch-window pressures}

## Growth goals

- **Twelve-month revenue goal**: {What you want the P&L to look like 12 months from now if this works}
- **The one lever you believe unlocks it**: {If you could only pull one thing, what would it be? The operating system sanity-checks this against the weekly data.}
- **What "winning" looks like in three months**: {Leading indicators you'd be happy to see: organic traffic, conversion rate, list size, ad ROAS, retention, etc.}

## Voice and brand guidelines (optional)

- **Spelling conventions**: {e.g. "ecommerce one word, never hyphenated"}
- **Phrases to avoid**: {Any banned clichés, industry jargon you reject}
- **Phrases the brand owns**: {Your recurring taglines, headlines, or catchphrases}
- **Tone**: {Direct / warm / technical / luxury / conversational}

## Session history (updated by Claude across sessions)

> Claude appends notes below as it learns patterns specific to your business. Leave this section blank to start; it grows over time.

---

## How Claude should use this file

On every session start, load this brief and treat it as the ground truth for your brand's specifics. When you run any sub-playbook (the weekly master manager, the SEO audit, the paid-ads sub-playbook, anything in `/playbooks/`), cross-reference the inputs here before asking the user for them. Do not invent values. If a field is blank, ask the user to fill it in before proceeding with work that depends on it.
