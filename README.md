# Automation Portfolio: Project Files

124 individual project files built from two internal knowledge bases of automation work (Pivot 2 Thrive, HL Growth Partner and Stack&Code). Each file has a **description**, a **Mermaid flow chart** and a **case study**, in the same layout (see [_TEMPLATE.md](_TEMPLATE.md)).

## How the files are organised

| Section | What it holds |
|---|---|
| 1. Description | What it does, inputs and outputs, components, where it lives (paths and environment-variable names only) |
| 2. Flow chart | A Mermaid chart plus a numbered walkthrough. Some files add a second chart for a failure path or a second mode |
| 3. Case study | Challenge, solution, design decisions, outcome (documented facts only), lessons learned |
| 4. Operating notes | How to run, pause and debug; known issues; risks |
| 5. Related | Links to neighbouring projects and the KB sections used |

## Status key

| Status | Meaning |
|---|---|
| Live | Running or deployed according to the knowledge base as of 9 Oct 2026 |
| On demand | Built and used manually or per project; no schedule, or live deployment not evidenced |
| Designed, not built | A design, spec or prototype only |
| Legacy or retired | Superseded, disabled or finished |
| Personal tool | A utility for the owner's own use |
| Reference | Documentation, patterns or a census rather than a running system |

Counts: On demand 62, Reference 18, Personal tool 18, Live 12, Legacy or retired 8, Designed, not built 6.

## Sources and how to read the evidence

- **Main KB** (an internal knowledge base, not part of this repository): built from real files and session transcripts, snapshot 9 Oct 2026. It is the primary source. Where it and the portfolio KB disagree, the files follow the main KB and say so.
- **Portfolio KB** (also not part of this repository): derived from ChatGPT conversations. Its content is labelled "(portfolio KB)" wherever it was folded in. Section 09 holds the workstreams that exist only there.
- **No invented results.** Outcomes list only what the sources document. Where nothing was measured, the file says "No measured outcome recorded." Markers `(inferred)` and `(not found)` are carried over from the KB.
- **Public-safe edition.** This version has been redacted for publication: no secrets, no credential locations, no live admin or back-office URLs, no unfixed-vulnerability details, and no client audit findings. Where a project had such findings, the file says only that they are tracked privately. Environment-variable names appear, but never values.
- **Evidence-based, not marketing.** Project status and outcomes reflect what the sources documented as of 9 Oct 2026, including unfinished and design-only work.

## Known conflicts inside the knowledge bases

These are recorded in the affected files, not silently resolved:

- **Client Project Updates:** the schedule is described as 8am in one place and `30 10 * * 1-5` (10:30 IST) in another; the cloud cutover is described as both done and not done. The files follow Part 1 (read from the scheduler).
- **Claude Expert topic engine:** listed as a live cloud routine in the register, but Part 2 says no routine was created and all 31 posts are live.
- **Portfolio KB claims of "completed":** several (Zoho migration, ServiceM8 sync, GHL forms to Sheets, RSS to blog) are stronger than the main KB's evidence. The files state both.
- **Lead volumes, ports and hostnames** differ between sections in a few places (NDIS counts, the 23k lead list, POWER PIVOT API host). Each is flagged in its file.


## 1. Scheduled tasks and daily reporting

Recurring jobs that read calls, orders and CRM data and report to Slack and dashboards.

| Project | Status | Summary |
|---|---|---|
| [Cafe Grato Live Order Monitor](01-scheduled-tasks-reporting/cafe-grato-order-monitor.md) | Live | A read-only scheduled task that checks the live Cafe Grato order page every two hours and reports new, changed and removed orders, so a migrated coffee-shop system does not silently lose or alter orders. |
| [Client Project Updates (Fathom to GHL notes, tasks and stages, then Slack)](01-scheduled-tasks-reporting/client-project-updates.md) | Live | A weekday scheduled task that turns recorded client calls and internal huddles into neat GHL notes, assigned team tasks, rule-based pipeline moves and a Slack digest, exactly once, for the P2T and HLGP sub-accounts. |
| [Sales Call Report, Dashboard and Lead-Pipeline Sync](01-scheduled-tasks-reporting/sales-call-report-dashboard.md) | Live | A weekly and monthly cloud routine that works out which P2T and HLGP sales calls were booked, showed, no-showed or closed, reports in plain language to Slack and Excel, serves a correctable live dashboard, and moves GHL leads... |

## 2. Content, SEO and newsletters

Blog engines, newsletter builders, SEO tools and the move of the blog routines to the cloud.

| Project | Status | Summary |
|---|---|---|
| [Blog Post Backlog Repair (legacy, self-cancelling)](02-content-seo-newsletters/blog-backlog-repair.md) | Legacy or retired | A daily Cowork task that repaired up to 12 broken P2T and HLGP blog posts per run (dead covers, wrong links, double H1s, missing canonicals) and deleted itself when both blogs were clean. |
| [Blog Engine Watchdog (Slack failure alerts)](02-content-seo-newsletters/blog-engine-watchdog.md) | Legacy or retired | A daily check, run as a local Cowork task, that confirmed both blog engines posted their daily quota and sent one Slack alert only if something failed. |
| [Client Blog Engine: Summit Air and Solar Flex (Mon/Wed/Fri)](02-content-seo-newsletters/client-blog-engine-summit-air-solar-flex.md) | Live | A scheduled engine that researches, writes and schedules one SEO and AI-search (AEO) blog post per run for each of two client GoHighLevel accounts, Summit Air Heating & Cooling and Solar Flex, to go live at 9:00 AM US Eastern. |
| [Cloud Migration, October 2026 (why 6 Oct mattered and what was chosen)](02-content-seo-newsletters/cloud-migration-oct-2026.md) | Reference | The record of the 1 Oct 2026 decision to move the blog engines (and later other jobs) from local Cowork scheduled tasks to Claude Code cloud routines that call the GoHighLevel REST API directly, with no MCP and no PC. |
| [GHL Blog API and Shared Blog Tooling (`ghl_blog.py`, `make_cover.py`)](02-content-seo-newsletters/ghl-blog-api-and-shared-blog-tooling.md) | Reference | The shared Python helper, cover generator and GoHighLevel Blog API gotcha list that the P2T and HLGP blog routines use, so cloud runs never need the GHL MCP or a desktop. |
| [HL Growth Brief HTML email builder](02-content-seo-newsletters/hl-growth-brief-email-builder.md) | On demand | A Claude skill that converts pasted newsletter copy into the finished, validated "HL Growth Brief" email HTML for GoHighLevel, identical section-for-section to the master template, for HL Growth Partner. |
| [HLGP Daily SEO Blog Engine (3 posts/day, hlgrowthpartner.com)](02-content-seo-newsletters/hlgp-daily-seo-blog-engine.md) | Live | A cloud routine that writes, audits and publishes three keyword-cluster SEO blog posts a day to the HL Growth Partner blog, for GoHighLevel agency owners. |
| [HLGP weekly newsletter drafter](02-content-seo-newsletters/hlgp-weekly-newsletter-drafter.md) | On demand | A Claude skill that turns the last 7 days of Fathom calls into a CTA-driven weekly newsletter draft for GoHighLevel agency owners, for HL Growth Partner. |
| [31-page AI and industry landing-page blueprint](02-content-seo-newsletters/landing-page-blueprint-31-pages.md) | Designed, not built | A content dictionary, static previewer and GoHighLevel build guide for 31 programmatic SEO landing pages (14 AI function pages, an industries hub and 16 industry pages) for Pivot 2 Thrive. |
| [n8n: GHL changelog to blog, and weekly newsletter (Slack approval)](02-content-seo-newsletters/n8n-ghl-changelog-to-blog-and-newsletter.md) | Legacy or retired | An older n8n automation that watches the GoHighLevel changelog RSS, has an LLM draft a blog post for small marketing agencies, asks the team in Slack to approve, then publishes to the HLGP blog, with a second flow for a weekly... |
| [P2T Claude Expert / AI Expert Australia Topic Engine (31 topics)](02-content-seo-newsletters/p2t-claude-expert-topic-engine.md) | Legacy or retired | A fixed 31-topic, four-cluster publishing engine, one post per run, built to make Pivot 2 Thrive the cited "Claude expert" entity in Australia; all 31 posts were live by 30 Sep 2026. |
| [P2T Daily Blog Engine (3 posts/day, pivot2thrive.com.au)](02-content-seo-newsletters/p2t-daily-blog-engine.md) | Live | A cloud routine that writes, illustrates and publishes three SEO and AEO blog posts a day to the Pivot 2 Thrive GoHighLevel blog. |
| [P2T sitemap live/non-live audit and URL-usage finder](02-content-seo-newsletters/p2t-sitemap-audit-and-url-finder.md) | On demand | Two Python scripts that classify every URL in the pivot2thrive.com.au sitemap as live or dead and find every place a given page is linked, so pages can be unpublished safely. |
| [P2T weekly newsletter HTML builder](02-content-seo-newsletters/p2t-weekly-newsletter-builder.md) | On demand | A Claude skill and example package that turn pasted copy into the navy and orange Pivot 2 Thrive weekly newsletter HTML, validated and ready to paste into GoHighLevel. |
| [PoolSafe AU blog publish scripts (Servigo)](02-content-seo-newsletters/poolsafe-au-blog-publish-scripts.md) | Legacy or retired | Two one-off Python scripts that moved a "Check louvres for compliance" article from a saved web page into the PoolSafe AU GoHighLevel blog, working around a silent edit failure by creating a new post and archiving the old one. |
| [Voice note to branded newsletter](02-content-seo-newsletters/voice-note-to-branded-newsletter.md) | On demand | A Claude skill with a Python generator that turns the founder's weekly voice note, or any transcript, into a send-ready Markdown newsletter in the founder's voice for an entrepreneur audience. |
| [Weekly Content Engine SOP (LinkedIn newsletter and authority post)](02-content-seo-newsletters/weekly-content-engine-sop.md) | On demand | A delegable weekly SOP, packaged as a Claude skill, that lets a team or VA run a creator's LinkedIn authority content with about 15 minutes of creator review per week. |

## 3. GoHighLevel, CRM and migrations

CRM migrations, pipeline work, GHL audits and builders, funnels, and the consolidated API reference.

| Project | Status | Summary |
|---|---|---|
| [BNI Referral Engine email-automation pack (and BNI/Expo scoring webhook backends)](03-ghl-crm-migrations/bni-referral-engine-email-pack.md) | Designed, not built | A written specification of every email, trigger, wait, tag and workflow for the "BNI Referral Engine" done-for-you product, plus the Express webhook backends that score BNI and Expo surveys into PDFs, built for Pivot 2 Thrive. |
| [GHL account audit (skill, ghl_audit runs and a complete client audit)](03-ghl-crm-migrations/ghl-account-audit.md) | On demand | A business-need-driven audit of a GoHighLevel sub-account across 260 features, scored 0-100 and dollar-quantified, with a Stop/Avoid list and a 30/60/90 roadmap, used on the team's own accounts and for a client. |
| [GHL AI prompt builder and search-for-ghl skills (with the Pool Safe AU page-prompt run)](03-ghl-crm-migrations/ghl-ai-prompt-builder-and-search-for-ghl.md) | On demand | Two Claude skills that turn HTML pages, screenshots and plain-language processes into paste-ready prompts for GoHighLevel's AI builders, and that architect any requirement native-first inside GHL, for the Pivot 2 Thrive and HL... |
| [GHL API contracts and quirks (consolidated reference)](03-ghl-crm-migrations/ghl-api-contracts-and-quirks.md) | Reference | A consolidated reference of how the GoHighLevel API actually behaves, learned across the team's migrations, audits, blog tooling and imports, with a troubleshooting decision tree built from those quirks. |
| [ghl-builder and Apex GHL Injector (push HTML into the GHL page builder)](03-ghl-crm-migrations/ghl-builder-apex-injector.md) | On demand | Experimental tooling that gets an arbitrary HTML page, or editable native elements, into a real GoHighLevel funnel page by reusing GHL's own builder autosave request, for the Pivot 2 Thrive and HL Growth Partner team. |
| [GHL login security-code relay from a team mailbox to Slack (design only)](03-ghl-crm-migrations/ghl-login-otp-capture-design.md) | Designed, not built | A proposed scheduled routine that would surface GoHighLevel "Login security code" emails, which arrive in a shared team mailbox, in a private Slack channel so team members can log in without access to the mailbox. |
| [High-Ticket Sales Accelerator funnel pages (offer, checkout and thank-you HTML for GHL)](03-ghl-crm-migrations/high-ticket-sales-accelerator-funnel-pages.md) | On demand | Three single-file HTML pages and three checkout blocks for the HL Growth Partner "High-Ticket Sales Accelerator" Inner Circle membership, ready to paste into GoHighLevel custom-code elements. |
| [HLGP to P2T pipeline copy and client placement](03-ghl-crm-migrations/hlgp-to-p2t-pipeline-copy.md) | On demand | A one-off script-and-API job that copied the structure of the HLGP "Lead Pipeline" and "Client Project Status" pipelines into the P2T GHL sub-account and placed the 17 current P2T clients into the new status pipeline. |
| [Real-estate prospect importers (Python scripts and colour-coded workbook staging)](03-ghl-crm-migrations/real-estate-prospect-importers.md) | Legacy or retired | Python scripts and a staged master sheet that load Wasteman Rubbish Removal's real-estate prospect lists into its GHL account as tagged contacts grouped under per-office Businesses. |
| [ServiceM8 to GoHighLevel migration engine (skill and Tint Melbourne reference run)](03-ghl-crm-migrations/servicem8-ghl-migration-engine.md) | On demand | A tested, resumable Node.js engine that loads a ServiceM8 account into a client's GoHighLevel sub-account as native custom objects with associations, so any CRM contact shows its company, its jobs and its job contacts. |
| [ServiceM8 to GoHighLevel two-way sync blueprint](03-ghl-crm-migrations/servicem8-ghl-two-way-sync-blueprint.md) | Designed, not built | A designed, GHL-native two-way sync between ServiceM8 and GoHighLevel for Wasteman Rubbish Removal (jobs to opportunities, contacts, scheduling, payments), published as a 35-workflow blueprint and build pack but never built. |
| [Wasteman ServiceM8 to GoHighLevel migration (real-estate scope, then all categories for 24 months)](03-ghl-crm-migrations/wasteman-servicem8-ghl-migration.md) | On demand | A scoped second run of the ServiceM8 migration engine that loaded Wasteman Rubbish Removal's real-estate clients, and later all categories for the last 24 months, into its GHL sub-account with property-manager, billing and... |
| [Zaffarology email batch tooling (`email_batch`)](03-ghl-crm-migrations/zaffarology-email-batch-tooling.md) | On demand | Partly built Python tooling to send the "1.2M List" GHL email template to batches of 5,000 contacts tagged `1.2m_list` and tag them as sent, only after explicit confirmation; the test sender exists, the batch sender was never... |
| [Zaffarology 1.2M-record list: XLSX to CSV split and import-time estimate](03-ghl-crm-migrations/zaffarology-list-split-and-import-estimate.md) | On demand | Profiled a purchased 1.2 million record Australian marketing list, estimated how long a PIT-based API import would take, and re-cut the list into 11 CSV files small enough for GHL's built-in importer. |
| [Zoho to HighLevel idempotent migration (Clixpert, n8n)](03-ghl-crm-migrations/zoho-to-highlevel-migration-clixpert.md) | On demand | An n8n workflow that migrates a Zoho CRM Excel export for Clixpert into HighLevel: accounts become contacts, and jobs, contracts and products become custom-object records, with notes kept on the contact. |

## 4. Lead generation, outreach and data pipelines

Lead extraction and crawling, follow-up and cold-email engines, NDIS datasets and master databases.

| Project | Status | Summary |
|---|---|---|
| [Client Finder AI platform (project "scaber", now "scraper")](04-lead-gen-outreach-data/client-finder-ai-platform.md) | Live | A multi-tenant SaaS that finds local and B2B businesses missing digital tooling, scores them by buying intent, enriches contacts, writes AI outreach, sends follow-ups and notifies on replies, for digital agencies and AI... |
| [Cold-Email Strategy Miner](04-lead-gen-outreach-data/cold-email-strategy-miner.md) | Personal tool | A Python script that reads the owner's own Gmail inbox over IMAP, uses Gemini to pick out the cold and warm outreach emails and ad emails that arrived, and generates 30 distinct outreach templates from what it finds. |
| [Cold Outreach Leads Analyzer](04-lead-gen-outreach-data/cold-outreach-leads-analyzer.md) | On demand | A set of Python scripts that crawl each lead's website in the Stack&Code cold-outreach spreadsheet, diagnose real friction and automation opportunities, score and prioritise the lead, and draft an email subject and body... |
| [Contact-List Merge and Master Database Builder](04-lead-gen-outreach-data/contact-list-merge-master-database.md) | On demand | Python scripts that merge dozens of messy contact exports and lead sheets into one de-duplicated master list grouped by country or continent, and split into enriched (email and phone) versus unenriched records. |
| [Follow-up Email Engine (Default Mode and Custom Mode)](04-lead-gen-outreach-data/followup-email-engine.md) | On demand | A sequence-based follow-up system inside Client Finder AI that sends threaded Gmail follow-ups to leads who have not replied and stops at once on reply, bounce or unsubscribe. |
| [Google Maps Places API lead extractor](04-lead-gen-outreach-data/google-maps-places-lead-extractor.md) | On demand | A Python command-line tool that bulk-extracts Australian business leads (law firms, aesthetic clinics, real estate agencies, financial advisors) from the Google Places API (New) into CSV and XLSX for a client lead-list order. |
| [Job Agent (folder `pdf`): Resume Tailoring and Job Application Automation](04-lead-gen-outreach-data/job-agent-resume-tailoring.md) | Designed, not built | A FastAPI scaffold for AI-assisted targeted job applications: scrape job boards, score each job against a resume, generate a tailored resume and auto-apply with Playwright. |
| [NDIS Batch Intelligence Analyzer](04-lead-gen-outreach-data/ndis-batch-intelligence-analyzer.md) | On demand | A resumable Python batch tool that crawls and rule-analyses NDIS provider websites into a reviewable intelligence CSV, without calling an LLM or sending any email, so Stack&Code outreach can be prepared in bulk. |
| [NDIS Provider Dataset Cleaning](04-lead-gen-outreach-data/ndis-provider-dataset-cleaning.md) | On demand | A one-off data-cleaning exercise that turned the raw August 2026 NDIS provider directory into a contactable target list of active registered head offices with working websites, for Stack&Code outreach. |
| [Node built-in GlobalCrawler and Autonomous Lead Engine](04-lead-gen-outreach-data/node-globalcrawler-and-autonomous-lead-engine.md) | On demand | An always-on crawler and scheduled saved-search engine built into the Client Finder AI web server, so lead discovery runs by itself with RAM-aware pacing and no one clicking "start job". |
| [Platform hardening, multi-server claim safety and production smoke test](04-lead-gen-outreach-data/platform-hardening-and-smoke-test.md) | On demand | A set of database claim-safety fixes and a one-command Playwright API smoke test that let the Client Finder AI app and the Python crawler share one MariaDB without double-processing, and let the owner check production quickly. |
| [Python global lead-discovery crawler ("leadengine" v4)](04-lead-gen-outreach-data/python-global-lead-discovery-crawler.md) | On demand | A standalone Python worker that discovers businesses worldwide, enriches them with verified contacts and scores, and writes directly into the Client Finder AI database, designed for a cheap 2 vCPU / 2 GB server. |
| [Stack&Code Email Trigger with Crawler](04-lead-gen-outreach-data/stackandcode-email-trigger-crawler.md) | On demand | A Python command-line tool that crawls a prospect's website, works out its industry and pain points, has an LLM write a personalised pitch, optionally sends it by SMTP, logs it in SQLite and pings Telegram, for Stack&Code cold... |
| [Transcript: In-Browser Meeting Recorder with Gemini Notes](04-lead-gen-outreach-data/transcript-meeting-recorder.md) | Personal tool | A React and Vite prototype that records or uploads meeting audio in the browser, shows a live transcript, and uses Gemini to produce a summary, key decisions, action items and a chat Q&A over the transcript, all stored locally. |

## 5. Excel operations and workflow tools

Timesheets, n8n hosting, audit backends, PDF factories and spreadsheet-driven forms.

| Project | Status | Summary |
|---|---|---|
| [AutoClaw (third-party headless agent, evaluated)](05-excel-workflow-tools/autoclaw.md) | Reference | An open-source TypeScript command-line AI agent, kept in the Workflows & Automation folder, that runs a tool-calling loop non-interactively in Docker or CI; it is third-party software that was built locally, not a product the... |
| [BNI Network Value Calculator and PDF factory](05-excel-workflow-tools/bni-network-value-calculator-and-pdf-factory.md) | On demand | A lead-generation calculator for BNI members: a short GHL survey scores how well a member follows up with their network, a Node backend turns the score into a branded personal PDF, and the results are written back to the GHL... |
| [n8n hosting templates](05-excel-workflow-tools/n8n-hosting-templates.md) | Reference | Two Nginx reverse-proxy templates that make a self-hosted n8n (port 5678) reachable on a domain through a HestiaCP-style hosting control panel. |
| [Pivot GHL Hub (`editor`)](05-excel-workflow-tools/pivot-ghl-hub-editor.md) | On demand | A local Express "agency hub" starter that connects one HighLevel agency install over OAuth 2.0, discovers its sub-accounts, and lists their forms, funnels and surveys in a small read-only dashboard. |
| [POWER PIVOT audit backend and ABCD Audit checkout (`microsaas`)](05-excel-workflow-tools/power-pivot-audit-backend-and-abcd-checkout.md) | On demand | A lead-magnet and paid-audit micro-SaaS for HL Growth Partner: a free five-pillar agency audit quiz, a Node/Express backend that re-scores it, builds the PDF report, emails it and syncs the lead to GoHighLevel, and a paid... |
| [Scope Stainless Works digital timesheet](05-excel-workflow-tools/scope-stainless-works-digital-timesheet.md) | On demand | A client demo that replaces a handwritten weekly timesheet with a GoHighLevel survey, a Google Sheet that does all the checking and totals, and a manager approval step, built in two variants (A: HTML demo plus n8n, superseded;... |
| [Singapore Power forms to Excel](05-excel-workflow-tools/singapore-power-forms-to-excel.md) | On demand | A Python generator that rebuilds Singapore energisation and certification paperwork as one Excel workbook, where a single input tab drives four printable one-page A4 forms for a solar-PV electrical contractor. |

## 6. Apps, calculators, websites and funnels

Portals, task managers, quizzes, calculators, funnels and client websites.

| Project | Status | Summary |
|---|---|---|
| [AI Agency readiness quiz: scoring and PDF inside one GHL Custom Code action](06-apps-calculators-websites/ai-agency-readiness-quiz-ghl-custom-code.md) | On demand | A dependency-free JavaScript program, pasted into a single GoHighLevel Custom Code workflow action, that scores the "AI Agency in a Box" quiz out of 100, builds a 2-page branded PDF, stores it on the contact and optionally... |
| ["Start Your Own AI Agency" / Unfranchise funnels and link pages](06-apps-calculators-websites/ai-agency-unfranchise-funnels-and-link-pages.md) | On demand | Pivot2Thrive's AI-agency franchise offer pages: an offer page with a quiz survey, checkout panels for full-pay or instalment, a thank-you page, GHL custom CSS, and a link-in-bio page. |
| [AI Launchpad funnel (quiz, Roadmap session and Founders Launchpad coaching)](06-apps-calculators-websites/ai-launchpad-funnel.md) | On demand | A funnel for Dr Priya's AI offer: invitation, a free quiz that produces a Personal AI Launchpad Map, a paid Roadmap session, and an optional six-month group coaching programme, with a GHL build specification. |
| [AUSTRAC AML/CTF platform concept and Tranche 2 Readiness Scorecard](06-apps-calculators-websites/austrac-tranche-2-scorecard-and-platform-prototype.md) | Designed, not built | Pivot2Thrive's explored product for professional-services firms facing AUSTRAC Tranche 2: a scope-of-work and research base, a mock-data prototype app with an additive customer risk engine, and a free 12-minute readiness... |
| [Authority Inner Circle member portal](06-apps-calculators-websites/authority-inner-circle-member-portal.md) | Live | A member portal for the "Authority Daily 3" programme (Show, Sell, Serve) that runs as an iframe inside GoHighLevel sub-accounts, with daily check-ins, proof and revenue capture, awards, reminders and a two-way mirror of... |
| [BNI and Franchise PDF factory with postcode lock (EXPOBNI backend)](06-apps-calculators-websites/bni-franchise-pdf-factory-and-postcode-lock.md) | On demand | A Node/Puppeteer webhook backend that turns a GHL survey submission into a scored, branded PDF linked on the contact, and also locks a territory postcode for the "AI Agency / Unfranchise" offer. |
| [BNI landing page, revenue-leak calculator and expo collateral](06-apps-calculators-websites/bni-landing-page-and-revenue-leak-calculator.md) | On demand | A funnel for BNI chapter members and expo visitors: a redesigned landing page, a separate follow-up revenue-leak calculator and survey, and printed expo collateral. |
| [BNI Oasis Connect member directory](06-apps-calculators-websites/bni-oasis-connect-member-directory.md) | On demand | A public member-directory page for a BNI chapter plus an admin portal where an admin pastes a chapter member-list URL and the members (photos, contact details, socials) are imported automatically. |
| [Cafe Grato shop, subscriptions and wholesale app](06-apps-calculators-websites/cafe-grato-shop-and-subscriptions-app.md) | Live | A custom coffee e-commerce and back-office system for a coffee roaster, embedded into a GoHighLevel site, with Stripe checkout, subscriptions, wholesale and pre-order pages, stock and shipping rules. |
| [Centinl AML/CTF audit portal with AI scoring](06-apps-calculators-websites/centinl-aml-ctf-audit-portal.md) | Live | A portal where reporting entities answer 23 AML/CTF evidence questions and upload documents, and admins run an AI score that produces a 0-100 rating and a formal Word review report, with GoHighLevel as the only datastore. |
| [Cleaning-industry GHL snapshot and funnels](06-apps-calculators-websites/cleaning-industry-ghl-snapshot-and-funnels.md) | On demand | A productised "Cleaning Industry GHL snapshot" (residential, commercial and hybrid delivery models) with documentation, follow-up message vault, scripts and funnel pages. |
| [Clixpert job orders: GHL webhook to MySQL to branded PDF](06-apps-calculators-websites/clixpert-job-order-pdf-webhook.md) | On demand | A PHP webhook and PDF generator for Clixpert: a GHL workflow posts a job order, every field is stored in MySQL, and a processor later builds a branded PDF and writes its link back to the GHL contact. |
| [Doloras / Aspirations United programme page](06-apps-calculators-websites/doloras-programme-page.md) | On demand | A single static landing page, "Self-Expression and Free Choice: A Pathway to Freedom", with inline CSS and no scripts or forms. |
| [Dr Priya personal brand site](06-apps-calculators-websites/dr-priya-personal-brand-site.md) | On demand | A set of static pages for the Pivot2Thrive principal's personal brand: home, keynote speaker and a HighLevel Partner Program affiliate page, with a script that rebuilds the affiliate page from the home page. |
| [EMAAR Finance calculators hub](06-apps-calculators-websites/emaar-finance-calculators-hub.md) | On demand | A static "Financial Calculators" page for a finance broker, listing about 28 calculators that open in a popup iframe to a third-party provider's tools. |
| [HLGP 20-Hour Sprint funnel](06-apps-calculators-websites/hlgp-20-hour-sprint-funnel.md) | Live | A static-HTML funnel for HL Growth Partner's "20-Hour Sprint" offer, pasted into a GoHighLevel funnel, with GHL survey popups, checkout customisations and an enrolment-deadline countdown. |
| [HLGPods Task Manager (PHP original)](06-apps-calculators-websites/hlgpods-task-manager-php.md) | Legacy or retired | The original internal project and task manager for the agency's client work: clients, tasks, time logs, staff pods, documents and an encrypted credentials vault, with AI import of tasks from pasted text or documents. |
| [JustFlo website and GHL build prompts](06-apps-calculators-websites/justflo-website-and-ghl-prompts.md) | On demand | A marketing site for "JustFlo, the AI-powered business operating system" built as 12 static HTML pages, with per-page prompts for rebuilding it as native drag-and-drop pages in GoHighLevel's Ask AI Build mode. |
| [Keystone Strategic Advisory website (HTML conversion for GHL)](06-apps-calculators-websites/keystone-strategic-advisory-site.md) | On demand | A client website "Put AI to Work in Your Business", converted to static HTML for placement on the client's GoHighLevel site, with GHL form iframes and a booking modal. |
| [Landy / Londy email templates](06-apps-calculators-websites/landy-londy-email-templates.md) | On demand | Two static HTML email layouts for GoHighLevel's email builder: an end-of-financial-year Ford Ranger offer and a monthly newsletter. |
| [Pivot 2 Thrive new website (proposed replacement)](06-apps-calculators-websites/pivot2thrive-new-website.md) | On demand | A static replacement for pivot2thrive.com.au, about 39 pages, built from the real site's sitemap and content plus GHL account data, deployed to a preview host without touching the live GHL site. |
| [PMAI Task Manager (multi-tenant SaaS rewrite)](06-apps-calculators-websites/pmai-task-manager-multi-tenant.md) | Live | The StackandCode PMAI Task Manager: the PHP task tool rebuilt in Node as a multi-tenant SaaS with kanban, time tracking, invoices, a client portal, an integrations hub and an AI assistant. |
| [Pool heat pump sizing calculator and store pages](06-apps-calculators-websites/pool-heat-pump-sizing-calculator.md) | On demand | A lead-gated calculator for a pool-heating client that turns pool size, location and season into the required kW and recommended heat pump models, plus follow-on store pages that recommend GHL store products. |
| [PoolSafe AU website and GHL rebuild](06-apps-calculators-websites/poolsafe-au-website-and-ghl-rebuild.md) | On demand | An exact static copy of a Queensland pool-safety certification business's WordPress site, then a rebuild inside GoHighLevel using per-page Ask AI Build prompts, with the gotchas learned over three prompt rounds. |
| [POWER PIVOT Agency Audit (scored self-assessment front end)](06-apps-calculators-websites/power-pivot-agency-audit-front-end.md) | On demand | A single-page lead-magnet quiz for HL Growth Partner in which agency owners answer five pillars of yes/ok/no items and receive a score, blind spots, an estimated revenue leak and an emailed PDF report. |
| [Servigo BNI visitor funnel](06-apps-calculators-websites/servigo-bni-visitor-funnel.md) | On demand | A static "Visitor Registration - Independent Chapter Communications" page for a BNI chapter (one person per profession), kept with two PDF guides on the chapter automation build. |
| [Stack&Code company website with AI chatbot and Telegram takeover](06-apps-calculators-websites/stackandcode-company-website.md) | On demand | The marketing site for StackandCode, a full-stack and AI automation agency, with contact, newsletter and lead-magnet APIs and an AI chatbot whose conversations can be taken over by a human through Telegram. |
| [Willy voice and text assistant for PC and phone](06-apps-calculators-websites/willy-voice-assistant.md) | Personal tool | A "Gemini-style" assistant that controls the owner's Windows PC and Android phone by voice or text, with reminders, routines, if-this-then-that rules, email and server monitoring, and chat-bot front ends. |

## 7. Personal tools, media pipelines and infrastructure

Desktop utilities, the HeyGen video pipeline, logo kits, cloud scripts and the connector census.

| Project | Status | Summary |
|---|---|---|
| [Adaptive Power Manager](07-personal-tools-media-infra/adaptive-power-manager.md) | Personal tool | A PySide6 power daemon and dashboard for the owner's Windows gaming laptop that switches between four power profiles to extend battery life and logs battery health. |
| [Portfolio & Clients folder: Agency Growth OS, AI Sales OS and portfolio sites](07-personal-tools-media-infra/agency-growth-os-and-ai-sales-os.md) | Personal tool | Three separate git repos: a modular n8n system that finds and scores development-agency leads, a Telegram AI sales bot foundation, and two Node/Express portfolio sites. |
| [BatteryBoost Pro](07-personal-tools-media-infra/batteryboost-pro.md) | Personal tool | A C# WinForms tray app that freezes background apps after a period of inactivity so they use no CPU, then thaws them when they get focus, to stretch laptop battery. |
| [BeatSync RGB](07-personal-tools-media-infra/beatsync-rgb.md) | Personal tool | A Python app that lights the owner's ASUS TUF laptop keyboard in time with whatever audio the PC is playing, using the OpenRGB SDK server. |
| [CanvasFlow (carousel and document designer)](07-personal-tools-media-infra/canvasflow-carousel-designer.md) | Personal tool | A React and Vite browser app that turns a topic into a designed multi-slide social carousel or document, with AI copy, themes, a brand kit and PNG or PDF export. |
| [Cloud & Infra: S3 helper scripts](07-personal-tools-media-infra/cloud-infra-s3-helper-scripts.md) | Personal tool | Two small Python scripts for the owner's own use: list (and optionally bulk-download) everything in an S3 bucket, and confirm which AWS identity the stored keys belong to. |
| [Connectors and MCP servers in use (usage census)](07-personal-tools-media-infra/connectors-and-mcp-servers-in-use.md) | Reference | A reference inventory of every Claude connector and MCP server seen in the session transcripts, with call counts, so it is clear which ones do the real work in the automations and which are connected but idle. |
| [EmotionSoundLab](07-personal-tools-media-infra/emotionsoundlab.md) | Personal tool | A desktop brainwave and binaural-beat synthesizer with a computer-keyboard piano, oscillators, noise, filters, effects, presets, recording and a visualiser, built for the owner's own use. |
| [Files Arranger (drive organiser pipeline)](07-personal-tools-media-infra/files-arranger.md) | Personal tool | A Python pipeline that sorts the Downloads folder with an 18-rule classifier, then consolidates, regroups and tidies the C: and D: drives for the owner's own PC. |
| [GHL form embed test pages and pool heat calculator form](07-personal-tools-media-infra/ghl-embed-test-pages-and-pool-heat-calculator.md) | Personal tool | Static front-end experiments for making an embedded GoHighLevel form look like one clean dark "glass" card, plus a standalone pool-heat-calculator lead form prototype. |
| [LinkedIn post via self-hosted n8n (on demand and daily AI schedule)](07-personal-tools-media-infra/linkedin-post-n8n-workflow.md) | Personal tool | A Python command line tool that posts to LinkedIn through a self-hosted n8n webhook, plus a second n8n workflow that writes and publishes an AI-generated LinkedIn post every weekday. |
| [Other Personal Tools & Labs folders (map and small items)](07-personal-tools-media-infra/other-personal-tools-and-labs.md) | Reference | A short map of the smaller folders in the owner's Personal Tools & Labs area, saying what each one is, whether it is the owner's own work, and where its fuller page is. |
| [Scripts (school-management API reference documents)](07-personal-tools-media-infra/scripts-school-api-reference.md) | Reference | Two Markdown API references for a school-management backend, kept in a folder called Scripts although it holds no scripts; documents only. |
| [setup-openssh.ps1: Windows SSH server with key login](07-personal-tools-media-infra/setup-openssh-windows-ssh-server.md) | Personal tool | A PowerShell script that turns the owner's Windows PC into an SSH server reachable with a key (passwordless login), for remote control from another machine. |
| [Singapore electrical turn-on paperwork workbooks (client folder)](07-personal-tools-media-infra/singapore-electrical-turn-on-paperwork-workbooks.md) | On demand | Python/openpyxl scripts that keep about 15 per-site Excel workbooks consistent, so one data sheet feeds the printable compliance forms for Singapore electrical turn-on paperwork. |
| [Sound Typer (the "duck" family of typing-sound apps)](07-personal-tools-media-infra/sound-typer-duck-family.md) | Personal tool | A system-wide Windows typing companion that plays a themed sound on every key press, built as one program with many sound themes, for the owner's personal use. |
| [Stack&Code logo and site-asset sessions (neon logo cleanup, Canva logo update, site optimisation)](07-personal-tools-media-infra/stack-and-code-logo-and-site-asset-sessions.md) | Reference | A record of three Claude Code sessions that produced the clean neon Stack & Code logo, applied it across the Stack&Code website's icons, SEO images and blog art, and optimised the site's performance. |
| [Stack&Code Logo creator (brand kit generators)](07-personal-tools-media-infra/stack-and-code-logo-creator.md) | Personal tool | Python generators and an HTML showcase that define and export the Stack & Code ("SaC") brand identity: a 3D isometric interlocking hexagonal "S" monogram, with wordmark and text-format variants. |
| [StartupBackup](07-personal-tools-media-infra/startupbackup.md) | Legacy or retired | An archive folder holding registry Run-key backups and a startup clean-up script, taken as a safety copy before trimming Windows startup items. |
| [System Dashboard Pro, AutoBoost and server AutoBoost](07-personal-tools-media-infra/system-dashboard-pro-and-autoboost.md) | Personal tool | Three related system utilities: a Tk monitoring dashboard, a silent Windows RAM and CPU booster, and a Linux port of that booster deployed to the owner's servers. |
| [Zaffarology video pipeline (`zaff vid`): HeyGen avatar, ffmpeg branding, Drive upload](07-personal-tools-media-infra/zaffarology-video-pipeline-zaff-vid.md) | On demand | A Node.js pipeline that renders a HeyGen AI avatar reading written scripts, brands the footage locally with ffmpeg (captions, logo, website text, end card) and optionally uploads the finished vertical videos to Google Drive,... |

## 8. Custom Claude skills

Reusable playbooks. Skills that already have a project file are linked from the overview.

| Project | Status | Summary |
|---|---|---|
| [Custom Claude skills: overview and index](08-claude-skills/00-skills-overview.md) | Reference | An index of the owner's hand-made Claude skills (reusable process playbooks), where the four drifted copies live, which skills have their own project file, and the risks to watch. |
| [clone-blueprint (12-field AI clone identity card skill)](08-claude-skills/clone-blueprint.md) | On demand | A Claude skill that builds, saves and loads a 12-field "Clone Blueprint" identity card for a personal brand or business, so all AI content creation starts from the person's own niche, offer, tone and story. |
| [markitdown-converter (any file or URL to Markdown skill)](08-claude-skills/markitdown-converter.md) | On demand | A Claude skill that converts PDF, Word, PowerPoint, Excel, HTML, data files, images, audio, EPUB, email, ZIP and YouTube URLs into clean Markdown using Microsoft markitdown, singly or in batches. |
| [p2t-sop-writer (SOP detection and writing skill)](08-claude-skills/p2t-sop-writer.md) | On demand | A Claude skill that detects repeatable tasks from calls, Slack and GHL patterns, writes crisp table-format SOPs, and appends them to the master P2T SOP Playbook workbook, with an optional white-label client version. |
| [pivot2thrive-funnel-economics (paid-ads funnel diagnostic skill)](08-claude-skills/pivot2thrive-funnel-economics.md) | On demand | A Claude skill that finds where paid-acquisition spend leaks across an impressions-to-customers funnel, ranks the highest-leverage fix and issues a scale or no-scale verdict, as a written report, an interactive calculator or a... |
| [priya-business-advisor (strategy advisor persona skill, high level only)](08-claude-skills/priya-business-advisor.md) | Personal tool | A Claude skill that gives the business owner a consistent senior-advisor voice for strategy, pricing, operations, finance and risk questions, so the business context does not need re-explaining each time. This file describes... |
| [project-scope-tracker (call and proposal to client scope tracker skill)](08-claude-skills/project-scope-tracker.md) | On demand | A Claude skill that turns a client call transcript plus the agreed proposal into a client-facing scope and a Google Sheet project tracker, with paste-ready Slack messages for the project manager. It exists only in the synced... |
| [sales-engine (daily outbound sales ritual skill)](08-claude-skills/sales-engine.md) | On demand | A Claude skill that runs the owner's 45-60 minute daily sales ritual: score leads, draft multi-channel reach-outs against daily quotas, track follow-ups, and pitch paid speaking gigs. |
| [seo-os (SEO Operating System skill)](08-claude-skills/seo-os.md) | On demand | A Claude skill that runs a repeatable six-phase SEO framework for any niche, city or client, built from the HL Growth Partner reference project and invoked only by name. |
| [transcript-to-scope-sop (call transcript to Idea Brief, Scope of Work and SOPs)](08-claude-skills/transcript-to-scope-sop.md) | On demand | A Claude skill that turns any call transcript into three linked, evidence-backed documents: a Project Idea Brief, a defensible Scope of Work and delivery SOPs, separating what was committed from what was merely floated. |
| [website-audit (scripted four-lens website audit skill)](08-claude-skills/website-audit.md) | On demand | A Claude skill that crawls a live website with bundled Python scripts and produces an evidence-based, scored, page-by-page audit through four lenses: developer, QA tester, SEO specialist and business owner. |

## 9. Integrations and operations (portfolio KB only)

Workstreams that appear only in the ChatGPT-derived portfolio KB. Evidence is thinner, and each file says what is still undocumented.

| Project | Status | Summary |
|---|---|---|
| [ClickUp, Slack and Clockify integration](09-integrations-operations/clickup-slack-clockify-integration.md) | Reference | Connects ClickUp task events to task-status handling, Clockify time-tracking records and Slack team notifications, as described in the portfolio knowledge base. |
| [Clockify project and task matching](09-integrations-operations/clockify-project-task-matching.md) | Reference | Matches Clockify projects and tasks to the correct spreadsheet records so time tracking and operational reporting line up. |
| [Cloudflare Worker for Spotify RSS](09-integrations-operations/cloudflare-worker-spotify-rss.md) | Reference | A Cloudflare Worker script that processes Spotify RSS-related content; the portfolio knowledge base confirms it existed but records almost nothing else. |
| [Cron-based website and application monitoring](09-integrations-operations/cron-website-application-monitoring.md) | Reference | Scheduled checks that detect website and application issues; the Café Grato order monitor is the one concrete, documented instance. |
| [GHL custom-field tracking application](09-integrations-operations/ghl-custom-field-tracking-app.md) | Reference | A custom application that tracks GoHighLevel custom-field data and supports PDF-generation workflows, as described in the portfolio knowledge base. |
| [GHL forms to Excel and Google Sheets sync](09-integrations-operations/ghl-forms-to-sheets-sync.md) | Reference | Transfers GoHighLevel form and survey submissions into spreadsheet rows; the main KB documents one concrete design of this pattern in the Scope Stainless timesheet. |
| [GHL webhook automation](09-integrations-operations/ghl-webhook-automation.md) | Reference | A reusable pattern for using GoHighLevel events and webhooks to trigger external workflow logic such as record syncs, Slack alerts and PDF builds. |
| [Slack team notifications](09-integrations-operations/slack-team-notifications.md) | Reference | Automatically notifies the team in Slack when workflow events occur, such as task status updates, GHL webhook events and content approval requests. |

---

To add a project, copy [_TEMPLATE.md](_TEMPLATE.md) into the matching folder, fill in every section, and add a row here.
