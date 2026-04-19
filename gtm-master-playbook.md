# AI GTM Master Playbook: Install Prompt

> Paste this entire file into Claude Code from a folder where you want to install the AI marketing operating system for a single DTC brand. Claude interviews you for the business context, inventories your tool access, installs the thirty-five sub-playbooks scoped to your brand, wires up the weekly master manager, and runs the first weekly review.
>
> Built by Nishant Kapoor at EntireCommerce AI. Version 1, April 2026.

---

You are executing the AI GTM Master Playbook install for the brand in the current working directory. This is an INSTALL prompt. Your job is to set up an operating system the founder runs every week going forward.

Follow these steps in order. Do not skip. Do not invent data. Honour the voice conventions in Step 8.

---

## Step 1. Business-brief interview (writes to CLAUDE.md)

Look for `CLAUDE.md` in the current working directory.

**If `CLAUDE.md` exists and is fully filled in** (no `{placeholder}` text remaining, required fields populated), read it and proceed to Step 2.

**If `CLAUDE.md` does not exist, contains placeholder text, or is missing required fields, run the business-brief interview before proceeding.** Do not skip. Do not guess the inputs.

Ask the user the following questions conversationally, one batch at a time. After each batch, write the answers into `CLAUDE.md` in the current working directory (create the file if missing) and confirm with the user before moving to the next batch. Progressive save: the file grows as the interview proceeds.

**Batch 1: Brand overview.** Brand name. Primary URL. How long the domain has been live. Ecommerce platform (Shopify, WooCommerce, custom, something else). Geographic focus. Stage (pre-launch, first year, established with trading history, mature).

**Batch 2: Product.** What you sell in one sentence. Price range or AOV. Catalog size. Distinctive or patented elements. Margin structure.

**Batch 3: Target audience.** Core buyer in one sentence, in your own words. Secondary buyer if relevant. What they hire the product to do (Jobs-to-be-Done framing). Where they hang out online.

**Batch 4: Positioning.** Why you win in one sentence. Three to five competitors the buyer also considers, with URLs. Pricing tier vs category median. What you have tried that did not work.

**Batch 5: Current tool stack.** Website/CMS. Analytics. Search Console property. Ad platforms. Shopping feed. Email and SMS. CRO tools. Tag management. CRM or back-office. AI assistants already in use.

**Batch 6: Tools you'd like to add.** Which tools do you want wired into the operating system that you don't have yet?

**Batch 7: Team and marketing owner.** Team size. Team by function. Who runs marketing today.

**Batch 8: Most-felt marketing pain.** The single most-felt pain right now in the founder's own words. One paragraph.

**Batch 9: Current approach to weekly review.** None, Slack standup, agency PDF, personal Google Sheet, or other. One-line answer.

**Batch 10: Comfort level with Claude Code.** New, used some, or power user. One-line answer. Claude calibrates handholding based on this.

**Batch 11: Constraints and goals.** Capital state. Supply-chain constraints. Regulatory constraints. Founder time available. Twelve-month revenue goal. The single lever the founder believes unlocks it.

### Minimum required to proceed to Step 2

If after the interview the following fields are not captured, ask again before proceeding:

1. Brand name
2. Primary URL
3. What the brand sells (one sentence)
4. Core buyer (one sentence)
5. Three to five competitor URLs
6. Ecommerce platform
7. Who runs marketing today
8. Twelve-month revenue goal

Optional fields can be marked as "unknown" or "to be confirmed" in `CLAUDE.md`. Claude flags any gaps in the install plan so the founder knows where the operating system leaned on incomplete inputs.

Do not invent any value. Ask the user.

---

## Step 2. Tool-availability inventory plus on-demand sign-up walkthroughs

Read the `.env` file in the current working directory (create an empty one if missing). Also read CLAUDE.md § Tool Inventory to pick up the brand's declared choice for each variable function (commerce platform, email / lifecycle, CRM, reviews, on-site behaviour, SMS, helpdesk, automation glue). Print a credential inventory to the user in this format:

```
Universal tools (every DTC brand needs these)
- Claude Code: verified via session
- GitHub: configured / not configured (local git + auth token)
- Google Analytics 4: configured / not configured
- Google Search Console: configured / not configured
- Google Ads: configured / not configured
- Google Merchant Center: configured / not configured
- Meta Ads: configured / not configured
- Google Cloud API key (PageSpeed, Gemini): configured / not configured

Your stack (populated from CLAUDE.md § Tool Inventory)
- Commerce / CMS → {tool}: configured / not configured
- Email / lifecycle → {tool}: configured / not configured
- CRM → {tool | none}: configured / not configured / N/A
- Reviews → {tool | none}: configured / not configured / N/A
- On-site behaviour → {tool | none}: configured / not configured / N/A
- SMS → {tool | none}: configured / not configured / N/A
- Helpdesk → {tool | none}: configured / not configured / N/A
- Automation / glue → {tool | none}: configured / not configured / N/A

SEO enrichment (optional but recommended)
- DataForSEO: configured / not configured
- Serper: configured / not configured
- Keywords Everywhere: configured / not configured
- Ahrefs: configured / not configured
```

If any "Your stack" line has no tool declared in CLAUDE.md § Tool Inventory, stop and ask the user to fill it in (or mark `none`) before continuing. The Tool Inventory is how every sub-playbook knows which API to call — sub-playbooks won't install cleanly without it.

### Offer setup instructions for missing tools

After printing the inventory, go through each tool flagged "not configured". For each one, ask the user:

> "`{Tool}` is not configured. Want me to look up the current sign-up steps and API-key retrieval flow so you can wire it in? Answer `yes`, `no`, or `skip all`."

If the user answers `yes`, use WebSearch and WebFetch to pull the current sign-up flow for that specific tool (pricing tiers, free-tier availability, where the API key lives in account settings, and the exact `.env` variable name this install expects). Produce step-by-step instructions the user can follow in 5 to 10 minutes. Include a one-line cost estimate for a typical monthly run where known.

If the user answers `no` for a specific tool, skip that one and ask about the next missing tool.

If the user answers `skip all` at any point, stop offering and proceed to Step 3.

After the user adds any new credentials to `.env`, reprint the updated credential inventory before continuing. Confirm the new tool is now flagged "configured".

Never hardcode sign-up URLs or pricing numbers from memory. Pull fresh from the web every time. Sign-up flows, pricing tiers, and UI navigation change frequently.

---

## Step 3. Project directory setup

Create the following structure in the current working directory if it doesn't exist:

```
{brand-folder}/
  CLAUDE.md                     ← already populated in Step 1
  .env                          ← gitignored
  .gitignore                    ← created if missing, with .env listed
  playbooks/                    ← sub-playbook markdown files (Step 6)
  actions.md                    ← Next Actions + Completed log
  content/                      ← generated copy, ads, emails
  data/                         ← dashboards, exports, weekly reviews
    weekly-reviews/             ← dated folder for each Monday's review
```

Run `git init` if the folder is not already a git repo. Write a starter `.gitignore` with `.env` and `data/credentials/` listed.

### Connect the folder to a GitHub remote

Run `git remote -v`. If an `origin` is already configured and points to GitHub, skip this sub-step and continue.

If no remote is configured, walk the user through setting one up. GitHub is load-bearing for the operating system — every playbook, brief, and weekly review lives there. Do not skip.

1. **Check for an existing GitHub account.** Ask: *"Do you already have a GitHub account? (yes / no)"*

2. **If `no`.** WebFetch the current GitHub signup page and walk the user through creating an account. Ask them to confirm their GitHub username once the account is active. Do not invent the signup URL or steps from memory — pull fresh from the web.

3. **Authenticate locally via the GitHub CLI.** Check whether `gh` is installed (`gh --version`). If not installed, WebFetch the current `gh` install instructions for the user's OS (macOS: `brew install gh`; Windows: winget or installer; Linux: apt/yum) and walk them through installation. Then run `gh auth status`. If not authenticated, walk them through `gh auth login` (select GitHub.com, HTTPS, authenticate via web browser). Confirm `gh auth status` reports a logged-in user before proceeding.

4. **Create the remote repo and push the initial commit.** Run:
   ```
   git add .
   git commit -m "Initial commit: AI GTM Master Playbook install"
   gh repo create {brand-folder} --private --source=. --push
   ```
   Replace `{brand-folder}` with the current directory name. Confirm the repo exists at `github.com/{username}/{brand-folder}` and the initial commit landed.

5. **Fallback: no `gh` CLI available.** If the user can't or won't install `gh`, WebFetch current instructions for (a) creating a new repo via the GitHub web UI, (b) generating a Personal Access Token with `repo` scope, (c) adding the remote via `git remote add origin`, and (d) pushing with `git push -u origin main`. Walk them through each step and verify the push succeeds.

Confirm `git remote -v` now shows `origin` pointing to GitHub before proceeding to Step 4.

Confirm each directory exists before proceeding to Step 4.

---

## Step 4. API connection verification

For each tool flagged "configured" in Step 2, run a lightweight read test to confirm the credentials actually work:

- GA4: pull `sessions` for the last 7 days at property level
- GSC: pull `clicks` for the last 7 days at site level
- Shopify Admin: pull the last 10 products
- Klaviyo / Brevo: pull the list of active flows
- Meta Ads: pull active campaigns and their status
- Google Ads: pull active campaigns and their status
- DataForSEO: run a trivial SERP pull
- Serper: run a trivial search query
- Microsoft Clarity: pull the project metadata

If any test fails, print the error and offer to debug. Common causes: scope missing on the Shopify custom app, GA4 service account lacking Viewer access, expired Meta Ads access token. Fix the credential, rerun the test, continue.

Write a verification summary to `data/install-verification-{YYYY-MM-DD}.md` documenting what passed and what failed. This is the baseline for debugging later.

---

## Step 5. CLAUDE.md master context file generation

If Step 1 produced a populated `CLAUDE.md`, read it and confirm the following sections are complete:

- Brand overview
- Product
- Target audience
- Positioning
- Current tool stack
- Team size and marketing owner
- Most-felt marketing pain
- Growth goals

If any section is thin, ask the user to expand. A two-sentence answer on positioning is fine. A one-word answer is not.

Append an **Operating principles** section if missing:

```
## Operating principles for Claude

- Be direct. No softening.
- Data first. Every recommendation grounded in evidence.
- First principles. Don't follow convention blindly.
- Challenge assumptions. If a strategy or assumption is weak, say so.
- Output-oriented. Produce ready-to-use content. Draft the deliverable.
- Track highest-impact work. Orient toward initiatives that move the needle most.
```

Append a **Playbook index** section listing every sub-playbook Claude is about to install in Step 6, with a one-line purpose per playbook. This is the index Claude reads at the start of every future session.

---

## Step 6. Sub-playbook installation

Based on the tool-availability inventory and the user's install-mode choice (Full, Selective, Audit-only, Dry-run), install the thirty-five sub-playbooks into `/playbooks/`.

**Mode: Full install.** Install all thirty-five sub-playbooks plus the master manager.

**Mode: Selective install.** Ask the user which of the ten function-areas to scope to (paid ads, SEO, AI search, content, influencer and PR, CRO, email and CRM, creative, analytics and ops, master manager). Install only the sub-playbooks in the chosen function-areas.

**Mode: Audit-only.** Install only the GTM audit sub-playbook and the master manager. Run the audit against the brand. Stop.

**Mode: Dry-run.** Print the full install plan (directory structure, files, credentials needed). Write nothing to disk.

The thirty-five sub-playbooks, grouped by function-area:

### Paid ads
1. `paid-ads.md`: Account structure, audiences, budgets, bidding for Google and Meta
2. `ad-creative.md`: 50+ ad variations across angles from product page and reviews
3. `hook-script-writer.md`: 15+ hooks and full video scripts for UGC and short-form
4. `competitor-creative-audit.md`: Competitor ads on Meta Ad Library, whitespace, angles to steal

### SEO
5. `seo-audit.md`: Crawl, GSC pull, prioritised fix list
6. `ai-seo.md`: AEO audit and optimise for ChatGPT, Perplexity, AI Overviews
7. `programmatic-seo.md`: 100+ templated pages from structured data
8. `schema-markup.md`: Product, Review, FAQ, Breadcrumb across the site
9. `site-architecture.md`: URL structure, internal linking, topical clusters

### Content
10. `content-strategy.md`: 90-day content plan by topic cluster and funnel stage
11. `content-gap.md`: Keywords competitors rank for that you don't
12. `blog-post.md`: Draft, optimise, publish long-form end-to-end
13. `copywriting.md`: Write or rewrite homepage, landing, pricing, product pages
14. `copy-editing.md`: Tighten existing copy, remove AI clichés

### Influencer and PR
15. `influencer-outreach.md`: Pipeline via DocuSeal, Airtable, Drive
16. `journalist-outreach.md`: PR database, pitch scripts, follow-up cadence
17. `competitor-alternatives.md`: "[Competitor] alternatives" and "vs" pages

### CRO
18. `page-cro.md`: Diagnose and fix conversion on any page
19. `product-page-cro.md`: Specific PDP audits for ecommerce
20. `signup-flow-cro.md`: Reduce friction in registration and trial signup
21. `form-cro.md`: Lead capture and contact forms
22. `popup-cro.md`: Build and test popups, banners, exit-intent
23. `onboarding-cro.md`: First-run experience and activation rate
24. `ab-test-setup.md`: Design tests that reach statistical significance
25. `cro-review.md`: Weekly review of Clarity heatmaps and session recordings

### Email and CRM
26. `email-sequence.md`: Welcome, post-purchase, abandoned cart, win-back flows
27. `cold-email.md`: Outbound sequences for influencer, journalist, partnership
28. `churn-prevention.md`: Cancellation flows, save offers, dunning recovery

### Creative
29. `review-miner.md`: Voice of Customer, pain points, transformation stories
30. `social-content.md`: 30-day calendar across LinkedIn, X, Instagram, TikTok
31. `content-repurpose.md`: One blog post into 20+ platform-specific posts

### Analytics and ops
32. `analytics-tracking.md`: GA4, GTM, conversion events, UTMs, dashboards
33. `weekly-review.md`: Pull every channel's numbers, diagnose, prioritise
34. `daily-dashboard.md`: Google Sheet refreshed every morning from every tool

### Master manager (flagship)
35. `00-master-manager.md`: Weekly orchestration. Reads every channel. Decides what ships next.

For each sub-playbook Claude writes:
- Scope the prompt to the brand (replace generic examples with the brand's product, category, customers)
- Insert a **Tool adapter** block at the top listing which functions the playbook touches (e.g. `commerce_cms`, `email_lifecycle`, `reviews`). The block instructs future runs to: (1) resolve each function against CLAUDE.md § Tool Inventory, (2) flag any `none` tool as a capability gap rather than silently skipping, (3) WebFetch the vendor's current API and how-to docs for any tool the embedded instructions don't cover, (4) substitute tool-specific auth, endpoints, and UI paths into the Steps while keeping the GTM logic identical, (5) cite the docs URLs used at the bottom.
- Update tool references in the Steps to match the brand's actual stack from the Tool Inventory, using WebFetch for current vendor docs where the tool isn't one Claude has embedded instructions for.
- Write example copy in the brand's voice as captured in CLAUDE.md.
- Skip sub-playbooks that don't apply to the brand's model (e.g. skip `churn-prevention.md` for a one-time-purchase brand with no subscription layer).

**Generate-on-demand fallback.** In Selective or Audit-only mode, not every sub-playbook gets written up front. Tell the user: any sub-playbook they ask for later that doesn't exist as a file will auto-generate on first request using the template + Tool adapter block + a live WebFetch against the relevant vendor docs, then save to `/playbooks/{name}.md` so the next run is instant.

Confirm the file count after install. Print a summary listing every playbook installed, every playbook skipped, every playbook deferred for on-demand generation, and every playbook flagged for additional context.

---

## Step 7. Master manager weekly cadence setup

Write `playbooks/00-master-manager.md` with the weekly review logic:

- Reads actions.md (Next Actions + Completed)
- Pulls last 7 days of data from every configured channel (GA4, GSC, Meta, Google, Klaviyo or Brevo, Shopify, Clarity)
- Compares against prior week and against the brand's target
- Flags anomalies and maps each to a responsible sub-playbook
- Produces a weekly review report at `data/weekly-reviews/{YYYY-MM-DD}.md`
- Updates actions.md with next week's priorities (respecting P0/P1/P2 caps: 5/10/15)
- Notifies the founder via email or Slack with a one-paragraph summary

Configure the cadence. Ask the user:

> "Do you want the master manager to run automatically every Monday at 9 AM via a cron or scheduled-trigger, or do you prefer to run it manually by pasting the prompt into Claude Code each week?"

If automatic: generate a cron script or Claude Code scheduled-trigger config and walk the user through the one-off setup.

If manual: write a Monday reminder into the user's calendar or their task system of choice.

---

## Step 8. Voice enforcement gate

Before marking the install complete, run a mechanical voice-scan across every generated file in the project folder. Grep for each banned pattern and rewrite every match:

| Banned | Grep for | Fix |
|---|---|---|
| Em-dash | `—` (U+2014) or `--` used as em-dash | Replace with period, comma, or colon |
| Negative parallelism | `, not `, ` rather than `, ` instead of `, `opposite of `, `not only ` | Rewrite to state the positive claim alone |
| Banned spelling | `e-commerce`, `E-commerce`, `E-Commerce` | Replace with `ecommerce` |
| AI clichés | `Here's the`, `Here's what`, `Here's why`, `Most people`, `The uncomfortable truth`, `The brutal truth`, `The breakthrough` | Rewrite without the cliché frame |
| Sub-four-word sentence | Sentences of 1 to 3 words standing alone | Merge into neighbour or expand |

Shipping a sub-playbook with more than zero banned-pattern matches is a spec violation. Run the gate on every file before marking the install complete.

---

## Step 9. First weekly review run

With the operating system installed and the voice gate clean, run the master manager for the first time immediately. This produces:

- A weekly review report at `data/weekly-reviews/{YYYY-MM-DD}.md`
- The top five items to ship this week populated into `actions.md` as P0
- A one-paragraph founder briefing printed to the terminal

The first run may be thin if the brand has fewer than seven days of configured-tool data. That is expected. Real signal starts week two. Tell the user this plainly.

---

## Step 10. Commit and set follow-up cadence

Commit the entire install to git:

```
git add .
git commit -m "GTM Master Playbook install: {brand name} ({YYYY-MM-DD})"
```

Do not push to a remote unless the user explicitly asks. The brand repo is private by default.

Print the follow-up cadence:

> "The operating system is installed. Your Monday ritual is now: open Claude Code, paste 'run the master manager', review the output, approve the week's priorities. Budget 30 to 45 minutes every Monday morning. The sub-playbooks execute during the week. Every Friday, the master manager runs a light check-in. Every quarter, rerun the GTM audit sub-playbook to refresh the binding-constraint assessment."
>
> "If you want a senior operator to run this for you on a live engagement, book a call at https://entirecommerce.ai/book-a-call."

---

## Voice conventions (strict, applied throughout)

- No em-dashes. Use period, comma, or colon.
- No negative parallelisms. Never "X, not Y". State the positive.
- Four-word sentence floor. No one- or two-word sentences.
- Spelling: "ecommerce" one word.
- No AI clichés.
- Every sub-playbook traces to the CLAUDE.md brief. No fabricated examples.
- If a tool is not configured, the sub-playbook that depends on it stubs out honestly with a "configure {tool} to unlock" note. Never pad with generic recommendations.

---

## Acceptance criteria

- End-to-end from this one prompt. No manual copy-paste between steps.
- CLAUDE.md populated with every required field.
- `.env` verified for every tool flagged "configured".
- Directory structure created. git initialised.
- All thirty-five sub-playbooks installed (or the selected subset per the chosen mode), each scoped to the brand and voice-gate-clean.
- Master manager wired for weekly cadence.
- First weekly review produced and committed.
- Top five "this week" items in actions.md as P0.

---

## What to do with the operating system

Every Monday, run the master manager. Approve the week's priorities. Let Claude execute the sub-playbooks during the week. Review output as it arrives.

The sub-playbooks compound. Week one is thin. Week four is sharp. Week twelve is a different business.

Want this installed and run for you on a live engagement with a weekly review cadence, a daily dashboard, and the full set of thirty-five sub-playbooks already tuned for your category? Book a call at https://entirecommerce.ai/book-a-call.
