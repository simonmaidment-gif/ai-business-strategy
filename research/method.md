# Research method

**Status:** draft v0.1, 2026-10-18. The method will change after the pilot run of the test script (see
[Revision log](#revision-log)).

This document sets out what I'm investigating, how, and how I'll judge what I find. It states no
conclusions. Findings go in `research/products/`, `research/landscape/` and `research/sources/`, and the
framework is only written after them.

## 1. Research question

> How should a 10-50 person organisation that already uses AI ad hoc turn that into a deliberate operating
> layer, and which existing products serve each part of it?

"Ad hoc" means staff use ChatGPT, Copilot, Gemini or similar, often in personal accounts, with no shared
company context, no shared workflows, no policy and no measurement.

"Operating layer" means whatever has to exist so that AI use in the organisation compounds instead of
staying individual: shared context, shared ways of working, rules, and some way of knowing whether it pays
off.

### Sub-questions

1. **What does an operating layer consist of?** I start from a five-layer working hypothesis (below) and
   expect the evidence to confirm, merge, split or replace it.
2. **What do existing products already cover?** In particular, products that call themselves an "AI
   operating system" for companies.
3. **Where is the real gap** between what a small organisation needs and what it can buy and run?
4. **Does any part only make sense at a certain size?** Micro (2-9), small (10-50), mid (50-500), enterprise.
5. **What do the frameworks say?** AWS CAF-AI, the AWS GenAI maturity model, the Generative AI Atlas, and
   ISO/IEC 42001 and 27001. Where do they agree, and where do they assume an enterprise that a 15-person
   organisation isn't?

### Working hypothesis (to be tested, not a deliverable)

| # | Layer | Problem it would solve |
|---|---|---|
| 1 | Context | Everyone re-explains the business to AI, every time |
| 2 | Workflows | Value depends on who happens to be good at prompting |
| 3 | Governance | Data risk, no policy, no record of what AI is used for |
| 4 | Measurement | No one knows whether AI is paying off |
| 5 | Platform choice | Tool sprawl, lock-in, paying twice for overlapping products |

The research can reject any of these. A layer is kept only if it has evidence that the problem is real and
evidence of at least three ways to address it, across at least two product categories, or if the evidence
shows no product addresses it (which is itself a finding).

## 2. Scope

**In scope:** products and practices a 10-50 person organisation could realistically adopt, plus enough
enterprise context to say what changes at scale. Micro organisations are recorded, but they aren't the
design target.

**Region:** I'm based in Australia, so the default view is Australian. Data residency is assessed for AU
first, then UK/EU and US. Prices are recorded in the vendor's currency and converted to AUD on the access
date.

**Out of scope for now:** building new software, model benchmarking (which model writes the best text), and
consumer products with no organisational tier unless micro orgs realistically use them.

## 3. Product categories

The landscape is scoped by category, not by vendor, so that the comparison isn't driven by whoever has the
loudest marketing. A product can sit in more than one category. It's filed under its primary one and tagged
with the others.

| # | Category | What qualifies | Examples to check (not yet assessed) |
|---|---|---|---|
| 1 | **Assistant workspaces** | Organisation tiers of the general assistants, with admin controls and shared projects | ChatGPT Business/Enterprise, Claude Team/Enterprise, Gemini for Workspace, Microsoft 365 Copilot, Perplexity Enterprise |
| 2 | **Enterprise search and knowledge** | Search or Q&A across the organisation's existing systems, permission-aware | Glean, Guru, Atlassian Rovo, Notion AI, Coveo |
| 3 | **Company brain and knowledge OS** | Products, open source included, whose main job is to hold and serve organisational knowledge to AI | Mem, Tana, Obsidian with plugins, open-source "company brain" projects, GBrain-style setups |
| 4 | **Agent and workflow builders** | Building reusable AI agents or multi-step AI workflows, usually no-code | Dust, Relevance AI, Lindy, StackAI, Copilot Studio, custom GPTs/Projects |
| 5 | **Automation and integration** | Connecting systems, with AI steps inside automations | Zapier, Make, n8n, Power Automate |
| 6 | **Hyperscaler and suite offerings** | AI platforms from AWS, Microsoft, Google, Salesforce, ServiceNow and similar | Amazon Q Business, Bedrock, Azure AI Foundry, Vertex AI / Agentspace, Agentforce, Now Assist |
| 7 | **AI governance, risk and compliance** | Policy, AI inventories, risk assessment, ISO 42001 tooling | Credo AI, Holistic AI, Vanta / Drata AI modules, OneTrust AI governance |
| 8 | **Adoption and usage analytics** | Measuring who uses AI, for what, and with what effect | Vendor admin analytics, Worklytics, Larridin, digital-adoption platforms |
| 9 | **Self-described "AI operating systems" for companies** | Products that position themselves as the AI operating layer for a company. These are the direct comparators | Workday Sana, Dust, Langdock, Business in a Box, GROON AIOS, Company OS (Product Hunt), and others found during the longlist |

**Breadth target:** a longlist of 40+ products in `research/landscape/longlist.md`, then a shortlist of
15-20 researched in depth, each with a note in `research/products/<product>.md`.

**Inclusion rule for the shortlist:** every category is represented. Every category-9 product is included.
Other products need to be either widely adopted or a credible option for a 10-50 person organisation.

## 4. Comparison dimensions

Every product is assessed on the same dimensions so the notes can be compared side by side.

| Dimension | What I record | Evidence type |
|---|---|---|
| **Layer coverage** | Which hypothesis layers it serves (context, workflows, governance, measurement, platform), rated *none / partial / strong* with a one-line reason | Docs and hands-on |
| **Fit by org size** | Micro, small, mid and enterprise. For micro, whether the individual or consumer tier is the realistic one and whether there's an admin console | Pricing page, docs |
| **Pricing** | Model (per seat, usage, credits, platform fee), minimum seats, price at 8 and at 50 seats, in vendor currency and AUD | Pricing page |
| **Non-profit pricing** | Discount or grant programme, checked on the vendor's own pages | Vendor pages only |
| **Data residency** | Where data is stored and processed. AU available? UK/EU? Model-provider sub-processors | Trust centre, DPA |
| **Security and compliance** | SOC 2, ISO 27001, ISO 42001, other claims. Whether a report or certificate is published or only claimed | Trust centre |
| **Training on customer data** | Default and contractual position | Terms, DPA |
| **Admin and governance controls** | SSO, roles, data-access controls, retention, audit logs, model allow-lists | Docs and hands-on |
| **Lock-in and export** | What can be exported (context, workflows, logs), in what format, and whether leaving is easy | Hands-on |
| **Integrations** | Fit with the stacks small organisations already own (Microsoft 365, Google Workspace, Slack, Notion, Dropbox, Xero) | Docs and hands-on |
| **Maturity and momentum** | Founded, funding or parent, release cadence, visible customer base | Public sources |
| **Sources** | Every claim links to its source, with the date accessed | |

**Evidence labels.** Each claim in a product note is labelled by how I know it:
- **[tested]** I did it hands-on.
- **[vendor]** the vendor says so in its docs, pricing or trust pages.
- **[third-party]** an analyst, review site or practitioner says so.
- **[docs-only]** a product I couldn't get access to, rated from documentation only.

Vendor claims are never presented as tested. Where sources disagree (pricing especially), I record both and
say which I trust and why.

## 5. Hands-on test script

Every category-9 product, and the top ~5 general shortlist products, go through the same script. The point
is a fair, repeatable comparison of what small organisations actually get, not of what the marketing says.

### 5.1 The test company

A **synthetic** organisation. No real client or personal data goes into any product, ever.

> **Fieldnote Studio (synthetic).** An 8-person cultural heritage and exhibition consultancy in Melbourne.
> It writes interpretation plans, grant applications and collection significance assessments for regional
> museums, galleries and councils. Staff: director, two senior consultants, two consultants, a researcher,
> a designer and an operations manager. Stack: Google Workspace, Slack, Xero, a shared drive of past project
> files. Everyone uses ChatGPT or Claude on personal accounts. There's no AI policy.

Why this sector: it's the sector I know best, its documents are long-form and context-heavy (so a context
layer should visibly help), and it handles material with real sensitivity (unpublished research, Indigenous
cultural and intellectual property, client funding details), so governance has something concrete to protect.

The test kit lives in `research/test-kit/` and is identical for every product:
- **Company profile:** who we are, services, clients by type, tone of voice (1-2 pages)
- **Policies:** a short AI-use policy draft, a data classification sheet, a cultural-safety protocol
- **Past work:** three synthetic project files (an interpretation plan, a grant application, a significance
  assessment)
- **A "confidential" item:** a synthetic client funding letter marked restricted, used to test governance
- **The workflow brief:** the task used in step 3

### 5.2 Steps

Time-box each product to about 2 hours of hands-on work across the steps. Start a timer at sign-up.

| Step | What I do | Pass looks like | Record |
|---|---|---|---|
| **0. Get in** | Sign up with the research alias, on the cheapest tier that has organisation features. Read the trial terms first. Note whether a card is needed | A working org workspace without a sales call | Minutes to a usable workspace, card needed (y/n), sales-gated (y/n), trial length and conversion terms |
| **1. Load the context** | Add the company profile, policies and past work, using whatever the product offers (upload, connector, knowledge base, instructions) | A fresh chat or agent answers "who are we and how do we write?" correctly without being told | Method used, minutes, answer quality (*wrong / partial / right*), whether a second user gets the same context |
| **2. Build one workflow** | Build a reusable "draft an interpretation plan outline from a project brief" workflow that other staff can run, then run it on a new brief | A second (invited) user can run it and gets output that uses company context and house style | Minutes to build, whether it's shareable, output quality, how much prompting skill it took |
| **3. Set one governance control** | Make the restricted funding letter inaccessible to everyone except the director, or keep it out of AI responses. Then, as a non-director user, try to get its contents out | The control holds | The control used, whether it held [tested], plus retention, audit log, model and training settings available |
| **4. Find usage and value reporting** | Look for any admin view of who uses AI, for what, how often and at what cost | Some per-user or per-workflow usage view exists | What exists, what's advertised but missing, whether value (not only activity) is measurable |
| **5. Export and leave** | Export everything: context, workflows or agents, conversation history, audit logs. Then cancel and request deletion | A usable export in an open format, and a clear deletion path | What exported and in what format, what couldn't, cancellation steps, deletion confirmation |

### 5.3 What to record for every run

- Time to first value (minutes from sign-up to step 1 passing)
- Setup friction, as notes on each place I got stuck
- **Advertised versus actual:** every feature claimed on the marketing site that I couldn't find or that
  didn't work as described
- Admin and governance depth
- Export and lock-in
- Price at 8 and at 50 seats (AUD)
- Screenshots of each step, saved under `research/products/<product>/` (no personal data visible)

A run log template is in `research/products/_template.md`.

### 5.4 Sales-gated or enterprise-only products

Request a demo or trial using the synthetic company's profile, honestly described as research. If access
is refused or needs a sales process a 10-50 person organisation wouldn't go through, record that as a
finding ("not reachable by a small organisation") and rate the product from documentation only, labelled
**[docs-only]**.

### 5.5 Operational rules

- Sign up only with the dedicated research email alias.
- Read each trial's terms before signing up. Note auto-conversion dates in a trial calendar and cancel
  before any paid conversion.
- **Spend cap: AUD 150 in total** across all trials. Prefer trials with no card required. Record any spend
  in `research/landscape/spend-log.md`.
- Export before cancelling: some trials cut off access immediately on cancellation.
- Synthetic data only. Never connect a real Google, Slack or Microsoft account that contains real data.
  Use a dedicated test workspace.
- Disclose that this is independent research if a vendor asks. No product is paid or sponsored, and none
  gets to see a note before it's published.

## 6. Source synthesis

Each framework source in [`resources/README.md`](../resources/README.md) gets one note in
`research/sources/`, which records:

1. What the source claims (paraphrased, with section references)
2. What it implies for a small organisation's AI operating layer
3. What it assumes about organisation size, budget or staffing
4. Where it agrees or disagrees with the other sources

ISO/IEC 42001 and 27001 are cited by clause and Annex A control number with a paraphrase only. They're
never quoted.

## 7. Limits and bias

- **A single researcher.** One person's hands-on experience isn't a usability study. The script makes
  runs comparable, but the judgment calls (answer quality, friction) are mine. Where they matter, I'll show
  the evidence (screenshots, outputs) so readers can disagree.
- **A synthetic company, not a real one.** It can't show adoption, behaviour change or politics. That's
  what the later real install is for.
- **Point in time.** This market changes monthly. Every claim is dated and the landscape gets a regular
  refresh.
- **Conflict of interest.** I built [Curatorial.app](https://curatorial.app/), an AI workspace for
  curators. It isn't a general company AI layer and isn't assessed here, but readers should know I build in
  an adjacent space.
- **Sector skew.** The test company is a cultural-sector consultancy. Results should generalise to small
  knowledge-work firms, but I'll note anything that looks sector-specific.

## 8. Outputs

- `research/landscape/longlist.md`: the 40+ product longlist, by category
- `research/products/<product>.md`: shortlist notes, each with a hands-on section and a dated access log
- `research/sources/<source>.md`: one note per framework source
- Posts: the method (this document), the market map, and the hands-on comparison

## Revision log

| Date | Change |
|---|---|
| 2026-10-18 | v0.1 draft |
