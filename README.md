<div align="center">

---

### **[Want us to install this for you? Book a call →](https://entirecommerce.ai/book-a-call)**

---

</div>

# AI GTM Master Playbook

## A complete AI marketing operating system you can install into your own Claude Code project in about an hour. Ten function-areas covered end-to-end: paid ads, SEO, AI search (AEO), content, influencer and PR, CRO, email and CRM, creative, analytics and ops. Plus a weekly master manager that reads every channel on Monday morning, kills what isn't working, and reprioritises the week for you. Built by Nishant Kapoor at EntireCommerce AI.

---

<div align="center">

### Fastest way to use this playbook

**Paste this document's URL into Claude Code and say:**

> *"Read this and take me through it step by step."*

**Claude interviews you for the business context, walks you through any missing API setup, and installs the operating system for your brand. You don't need to read the rest of this document.**

</div>

---

## Who This Playbook Is For

This playbook is for three people.

**The founder-led DTC brand owner running marketing themselves.** You've hit the wall where product quality alone stops compounding. Revenue growth now depends on paid ads, SEO, AI search presence, email lifecycle, creative iteration, and a dozen other moving parts. You want one system that runs all of it in a single project folder with a single login. You want to spend your mornings deciding what to ship next while Claude Code handles the dashboard stitching.

**The operator who just joined a DTC brand and inherited the stack.** Klaviyo was set up by the last growth lead. Meta Ads has six campaigns running with no clear owner. Google Ads has been on autopilot for nine months. The founder wants a GTM plan by the end of the month. This playbook gives you an AI-native operating system that audits every function, produces a ranked punch list, and runs a weekly review cadence you can present in your first Monday standup.

**The agency or fractional CMO wanting an AI-native delivery system.** Your clients ask why your invoice looks like a traditional agency retainer when AI is doing most of the work. This playbook lets you show them the system: thirty-five sub-playbooks across ten functions, a weekly master manager that decides what ships next, and a shared GitHub repo they can read. The speed story sells itself once they see the cadence.

If you've been running marketing through a mix of Notion docs, Slack threads, one-off ChatGPT sessions, and a dashboard you update manually every Friday, this playbook collapses that whole pattern into a single Claude Code project.

---

## What the AI GTM Master Playbook Actually Is

**The short version.** A portable kit. Drop it into your main Claude Code project and ask Claude to set it up for your business. You get a working replica of the system we use to run go-to-market for Incred Golf, Riyanika, and other DTC clients at EntireCommerce AI. Ten function-areas. Thirty-five sub-playbooks. One weekly master manager. All grounded in a single `CLAUDE.md` business brief Claude reads on every session start.

**Best for.** Premium DTC brands. AOV £500+ or 2x category median. Founder-led. US, UK, or English-speaking European markets. Established brands with trading history, or pre-launch brands getting ready to ship.

**How it's different.** Three things most marketing systems skip.

First, **breadth across every function**. Traditional playbooks cover one channel: an SEO audit, a paid-ads framework, an email strategy document. This one covers ten function-areas end-to-end. Paid ads and SEO and AI search and content and influencer and PR and CRO and email and CRM and creative and analytics, in one coherent system, with a shared brand brief and a shared weekly cadence.

Second, **orchestration across sub-playbooks**. Each of the thirty-five sub-playbooks is self-contained and runnable on its own. The value compounds when Claude runs them in sequence: the SEO audit feeds the content strategy feeds the content calendar feeds the email nurture feeds the paid-ad creative. The master playbook wires the flow.

Third, **the weekly master manager**. One playbook sitting above the other thirty-five. It runs every Monday. Reads every channel. Decides what worked, what didn't, and what ships next. The orchestrator that most marketing stacks skip.

**Skip this playbook if** you run a service business, B2B SaaS, or a mass-market retail brand. The system is tuned for premium DTC and the sub-playbook prompts will be directionally off for other contexts. Skip it also if you prefer a single dashboard with no code, the operating system assumes you are comfortable with Claude Code, `.env` files, and GitHub-as-source-of-truth.

---

## Setup (15 Minutes)

### Prerequisites

Before you start, make sure you have:

- **Claude Code** installed. Download from [claude.com/claude-code](https://claude.com/claude-code). Verify with `claude --version`.
- **A GitHub account**. The operating system uses git for version control of every playbook, every brief, and every weekly review. Sign up at [github.com](https://github.com) if you don't have one.
- **pandoc** installed for Word-doc exports. On macOS: `brew install pandoc`. On Windows: [pandoc.org/installing.html](https://pandoc.org/installing.html).
- **A project folder** on your machine. One per brand you run. Name it after the brand.

### Cost overview

The playbook itself is free. You pay for API credits consumed by tools the operating system calls. Most tools are free or near-free. A handful of paid tools are recommended where their data is load-bearing.

| Tool | Subscription model | Typical monthly cost | Role |
|---|---|---|---|
| Claude Code | Included in Claude Pro or Max | $20 to $200 per month | The execution engine. Runs every playbook. |
| GitHub | Free for private repos | $0 | Source of truth for every playbook, brief, and weekly review. |
| Google Analytics 4 | Free | $0 | Traffic, conversions, revenue per channel. |
| Google Search Console | Free | $0 | Impressions, clicks, position changes. |
| Google Ads / Meta Ads | Free to read | $0 | Campaign performance. Your existing ad spend is separate. |
| Shopify Admin | Included in your Shopify plan | $0 | Orders, products, AOV, LTV. |
| Ahrefs or DataForSEO | Ahrefs $129+/mo, DataForSEO pay-as-you-go | **$10 to $150** | Recommended for SEO-heavy brands. DataForSEO if budget-conscious. |
| Apify or Serper | Serper free tier, Apify pay-as-you-go | **$0 to $20** | Live SERPs, competitor ad scraping. |
| Klaviyo or Brevo | Included in your existing plan | $0 | Email flows and revenue per flow. |
| Microsoft Clarity | Free | $0 | Session recordings and heatmaps. |
| Google Cloud API key | Free tier covers typical usage | $0 | Used for PageSpeed Insights and Gemini where needed. |

**Typical total cost per month across the paid external tools: $20 to $200** depending on brand scale and how many sub-playbooks you run actively.

Numbers above are approximate as of April 2026. Pricing changes. When you run the master install prompt, Claude prints the credential inventory and offers to look up current sign-up steps and pricing for any tool you're missing, straight from the web.

### Step 1: Create the project folder

```bash
mkdir my-brand && cd my-brand
git init
```

Drop the four files from this bundle (README.md, CLAUDE.md, gtm-master-playbook.md, gtm-master-playbook-deliverables.svg) into the folder.

**Gotcha I hit:** If your brand folder already holds a different Claude Code project, the install will overwrite files. Start fresh in a clean directory per brand. One brand per folder.

### Step 2: Set up your .env

Create a `.env` file in the project folder. Add the API keys you have. Missing any is fine: when you run the master install prompt in Step 4, Claude prints which tools are configured and which are missing and offers to walk you through sign-up for each missing one.

The operating system splits tools into two buckets. **Universal** tools are the ones every DTC brand needs — the Google stack and Meta. **Your stack** tools vary by brand — you tell Claude which commerce platform, email tool, CRM, reviews app, etc. you run in the `CLAUDE.md` Tool Inventory, and every sub-playbook adapts its steps and API calls accordingly. Where Claude doesn't already know a given tool, it WebFetches the vendor's current docs on the fly and writes tool-specific instructions into the sub-playbook.

Recommended starter `.env`. Keep the universal block as-is. Fill in the variables for the tools you actually run — comment out or delete lines for tools you don't use.

```
# ── Universal ──
# Analytics + search
GA4_PROPERTY_ID=
GSC_SITE_URL=
GOOGLE_APPLICATION_CREDENTIALS=

# Ad platforms
META_ADS_ACCESS_TOKEN=
META_AD_ACCOUNT_ID=
GOOGLE_ADS_DEVELOPER_TOKEN=
GOOGLE_MERCHANT_ID=

# Google Cloud API (PageSpeed, Gemini, etc.)
GOOGLE_AI_KEY=

# ── Your stack (fill in what applies, leave the rest empty) ──
# Commerce / CMS — pick one
SHOPIFY_ADMIN_API_TOKEN=
SHOPIFY_STORE_DOMAIN=
WOOCOMMERCE_CONSUMER_KEY=
WOOCOMMERCE_CONSUMER_SECRET=
WOOCOMMERCE_SITE_URL=
# (add BigCommerce, Webflow, Magento, Squarespace, etc. as needed)

# Email / lifecycle — pick one
KLAVIYO_API_KEY=
MAILCHIMP_API_KEY=
BREVO_API_KEY=
HUBSPOT_API_KEY=
ACTIVECAMPAIGN_API_KEY=
OMNISEND_API_KEY=

# On-site behaviour — pick one (optional)
CLARITY_API_TOKEN=
HOTJAR_API_KEY=

# SEO enrichment (optional, recommended)
DATAFORSEO_LOGIN=
DATAFORSEO_PASSWORD=
SERPER_API_KEY=
KEYWORDS_EVERYWHERE_API_KEY=
AHREFS_API_KEY=
```

**Gotcha I hit:** Never commit `.env` to GitHub. Add `.env` to `.gitignore` before your first commit. The install script writes a `.gitignore` for you if one doesn't exist.

### Step 3: Populate CLAUDE.md (or let Claude interview you)

You have two options:

**Option A (recommended, fastest):** Leave `CLAUDE.md` as-is. When you run the master install prompt in Step 4, Claude interviews you conversationally: brand overview, product, audience, positioning, tool stack, constraints, goals. Claude writes the file for you progressively as you answer. Takes about 10 minutes.

**Option B (DIY):** Open `CLAUDE.md` and replace every `{placeholder}` with your brand's specifics yourself before running the install. Founder voice, one or two sentences per field.

Either option produces the same end state: a populated `CLAUDE.md` that grounds every sub-playbook you run from this folder.

### Step 4: Open Claude Code and run the install prompt

```bash
claude
```

Paste the full contents of `gtm-master-playbook.md` into the terminal and hit enter. Claude walks you through:

1. Business-brief interview (writes to CLAUDE.md)
2. Tool-availability inventory + on-demand sign-up walkthroughs
3. Directory structure creation
4. API connection verification per tool
5. Sub-playbook installation (thirty-five files scoped to your brand)
6. Master manager weekly cadence setup
7. Voice gate across every generated file
8. First weekly review run

Confirm you see "Loaded CLAUDE.md" in the session log after Step 1 completes.

---

## The Files in This Bundle

### File 1: README.md

**Path:** `{your-project-folder}/README.md`
**What it does:** You're reading it. Setup, run, troubleshooting. Safe to ignore once you've installed the operating system once.
**How to use it:** Keep in the repo root as documentation for whoever joins your brand later.

### File 2: CLAUDE.md (business-briefing template)

**Path:** `{your-project-folder}/CLAUDE.md`
**What it does:** Claude Code loads this on every session start. It's where your brand's specifics live: product, audience, positioning, pricing, catalog, tool stack, constraints, and goals. Every sub-playbook reads from here first.
**How to use it:** Let Claude interview you (Option A above) or replace every `{placeholder}` yourself. Keep it tight: one to two sentences per field.

### File 3: gtm-master-playbook.md (the master install prompt)

**Path:** `{your-project-folder}/gtm-master-playbook.md`
**What it does:** The self-executing install prompt. Claude reads it, interviews you for business context, inventories your tool access, creates the full directory structure, installs all thirty-five sub-playbooks scoped to your brand, wires up the weekly master manager, and runs the first weekly review.
**How to use it:** Paste its entire contents into Claude Code and hit enter. Do not edit unless you know what you're doing. The structure is load-bearing.

### File 4: gtm-master-playbook-deliverables.svg / .png

**Path:** `{your-project-folder}/gtm-master-playbook-deliverables.svg` and `.png`
**What it does:** A one-page visual summary of the ten function-areas and the master manager. Useful for onboarding a teammate or pitching the system to a founder or CFO.
**How to use it:** Open the PNG in any image viewer. Drop into a deck. Print it out if that helps.

### File 5: gtm-master-playbook-bundle-combined.docx

**Path:** `{your-project-folder}/gtm-master-playbook-bundle-combined.docx`
**What it does:** Combined Word doc of the README, CLAUDE.md template, and master install prompt. Useful if you want to share the bundle with a team member via email or Google Docs without zipping the folder.
**How to use it:** Upload to Google Drive, convert to Google Doc, share with your team.

---

## Your First Run

Four steps. Forty-five to ninety minutes end-to-end the first time.

1. **Open Claude Code in your project folder.** `cd my-brand && claude`
2. **Paste the full contents of `gtm-master-playbook.md` into the terminal.** Hit enter.
3. **Answer Claude's interview questions.** Brand, product, audience, competitors, tool stack, goals. Takes about 10 minutes.
4. **Approve the install plan Claude prints.** Claude then creates the directory structure, writes the thirty-five sub-playbooks tailored to your brand, wires up the master manager, and runs the first weekly review.

Output lands at:

```
{your-project-folder}/
  CLAUDE.md
  .env
  playbooks/
    00-master-manager.md
    seo-audit.md
    ai-seo.md
    ... (33 more)
  actions.md
  data/
    weekly-reviews/YYYY-MM-DD.md
```

---

## What You'll Get

Ten deliverables that together constitute your AI marketing operating system.

1. **Always-on Meta and Google campaign engine.** Bidding, audiences, creative briefs, kill rules. Paid-ads sub-playbook plus creative-fatigue scoring plus competitor-ads intelligence running on a weekly cadence.
2. **Site health and content gaps audited any time.** Technical SEO, on-page, schema, backlinks, Core Web Vitals. Full SEO audit sub-playbook runnable on demand and scheduled into the monthly cadence.
3. **Citation presence and whitespace tracked weekly.** AI search visibility across ChatGPT, Claude, Perplexity, Google AI Overview. AEO sub-playbook runs every Monday inside the master manager.
4. **Pillars, briefs, drafts, and distribution at scale.** Twelve-month content strategy sub-playbook, content-gap analysis, blog-post publishing, repurposing across LinkedIn, X, Instagram, TikTok.
5. **Outreach pipeline and journalist database in one.** Influencer and PR sub-playbooks with DocuSeal, Airtable, and Drive integrations. Outbound to influencers, journalists, and partnership leads from one system.
6. **Page, funnel, and form audits on demand.** CRO sub-playbooks powered by Microsoft Clarity heatmaps and session recordings. A/B test setup and popup CRO included.
7. **Lifecycle flows, segmentation, and deliverability.** Email and CRM sub-playbooks that adapt to whichever ESP and CRM you run — Klaviyo, Mailchimp, Brevo, HubSpot, ActiveCampaign, Omnisend. Welcome, abandoned cart, post-purchase, win-back, churn prevention.
8. **Hooks, scripts, ad variations, and UGC briefs.** Creative sub-playbook producing bulk ad variations, hook taxonomies, short-form video scripts, and UGC creator briefs in your founder voice.
9. **Daily dashboard and tracking integrity audits.** Analytics and ops sub-playbooks covering GA4, Meta Pixel, GTM, attribution stitching, and a daily-refresh Google Sheet dashboard.
10. **Weekly orchestration that decides what ships next.** The master manager. Reads every channel on Monday morning, kills what isn't working, reprioritises the week. The differentiator the other nine function-areas compound into.

**Format.** One Claude Code project folder with thirty-five sub-playbook markdown files, one master manager, one CLAUDE.md brief, one `.env`, and a versioned git history. Every deliverable the system produces lands back in the same folder, committed to git, ready for the next weekly review.

---

## Modes

The install flexes based on what tools you already have and how deep you want the operating system to go on first install.

| Mode | When it applies | What changes |
|---|---|---|
| Full install | Most tools configured, founder committed to running the full system | All thirty-five sub-playbooks installed. Master manager runs every Monday. First weekly review produced on day one. |
| Selective install | You want only the function-areas you're actively working on | Claude asks which of the ten function-areas to scope to. Installs only those sub-playbooks plus the master manager. |
| Audit-only | You want to see what the system recommends before committing to install | Claude runs the GTM audit sub-playbook against your brand. Produces the ranked action list. Stops before installing anything else. |
| Dry-run | You want to see the install plan without writing any files | Claude prints the full plan: directory structure, files, credentials needed. Zero files written to disk until you approve. |

State your preferred mode at the start of Step 4. Claude confirms and adapts the rest of the install.

---

## Honest Caveats

**The operating system is only as good as the CLAUDE.md brief.** If the brief is vague, the sub-playbooks produce generic output. Spend twenty minutes on Batch 4 (positioning and competitors) during the interview. That batch drives more output quality than any other.

**Weekly cadence depends on founder or operator time.** The master manager runs every Monday but it needs a human to review the approval queue. Budget thirty to forty-five minutes every Monday morning for the review. Without that ritual, the system degrades to thirty-five disconnected playbooks.

**Some sub-playbooks assume premium-DTC defaults.** Email flow benchmarks, Meta creative formats, Shopify-specific checks. If you sell B2B SaaS or run a service business, those defaults will be directionally off. The methodology still applies, the benchmarks won't.

**Tool-specific quirks vary by stack.** Klaviyo has one quirk, Brevo has another. Meta Ad Library has a JS-rendering gotcha. The master install prompt handles the common ones but you will occasionally hit a tool-specific failure. When you do, paste the error back into Claude. Claude pulls the current fix from the web.

**API costs are real.** Budget $20 to $200 per month depending on brand scale and which sub-playbooks you run weekly. DataForSEO and Apify are the biggest spenders. Ahrefs is optional if you already have an account.

**This is an operating system you run yourself.** The system decides what ships next and drafts the work. You approve. You edit where the output needs a human touch. You ship. If you want a senior operator to run this for you on a live engagement, book a call at the top of this document.

---

## Quick-Start Checklist

Work top to bottom. Items you would run first are ordered first.

- [ ] Claude Code installed (`claude --version` works)
- [ ] GitHub account created and `git --version` works locally
- [ ] pandoc installed (`pandoc --version` works)
- [ ] Project folder created for the first brand you want to run
- [ ] README.md, CLAUDE.md, gtm-master-playbook.md from this bundle copied into the project folder
- [ ] `.env` created with the API keys you have (missing ones are fine; Claude walks you through the rest)
- [ ] `.gitignore` created with `.env` listed
- [ ] `git init` run in the project folder
- [ ] Master install prompt pasted into Claude Code and run end-to-end
- [ ] Business-brief interview completed, CLAUDE.md populated
- [ ] Tool credentials inventory reviewed, missing tools wired up or flagged as "skip"
- [ ] Install mode chosen (full, selective, audit-only, dry-run) and confirmed
- [ ] First weekly review produced at `data/weekly-reviews/YYYY-MM-DD.md`
- [ ] actions.md populated with the top five items to ship this week
- [ ] git commit of the whole install so you can diff against next week
- [ ] Monday morning ritual locked in (30 to 45 minutes, weekly)
- [ ] Book a call if you'd rather we run this for you on a live engagement: [entirecommerce.ai/book-a-call](https://entirecommerce.ai/book-a-call)

---

## Troubleshooting

| Symptom | Likely cause | Fix |
|---|---|---|
| "pandoc not found" during Word-doc export | pandoc not installed | `brew install pandoc` (macOS) or [pandoc.org/installing.html](https://pandoc.org/installing.html) |
| Claude Code hangs on the tool-inventory step | `.env` has trailing whitespace or quote issues | Open `.env`, strip whitespace and stray quotes, save, rerun |
| Master manager can't pull GA4 data | Service account lacks Viewer access on the GA4 property | Grant the service account Viewer in Admin → Property access management |
| Shopify Admin API returns 403 on product reads | Custom app token missing read scopes | Recreate the custom app with `read_products, read_orders, read_customers` scopes |
| Sub-playbook writes generic copy | CLAUDE.md brief too thin | Rerun the interview on Batch 4 (positioning, competitors, voice). Regenerate the sub-playbook. |
| Voice gate flags em-dashes or "X, not Y" patterns | Style drift in sub-agent output | Paste the banned-patterns list back into Claude and ask it to scan-and-fix the full file |
| git push fails with auth error | GitHub token missing or expired | Generate a new Personal Access Token at github.com/settings/tokens, paste into the git credential helper |
| Weekly review runs but produces no recommendations | Fewer than seven days of data in one of the channels | Expected on week one. Real signal starts week two. |

---

## Credit

Built by Nishant Kapoor at EntireCommerce AI.

- **LinkedIn**: [linkedin.com/in/nishantkapoor1](https://www.linkedin.com/in/nishantkapoor1)
- **Email**: nishant@entirecommerce.co
- **Book a call**: [entirecommerce.ai/book-a-call](https://entirecommerce.ai/book-a-call)
- **Full playbook library** (GTM audit, SEO audit, competitor creative audit, content strategy, positioning audit, and thirty-plus more): [entirecommerce.ai/playbooks](https://entirecommerce.ai/playbooks)

Use this playbook freely. Share it with other DTC founders. If you ship a case study running it on your brand, tag us. We'll link to it from the site.
