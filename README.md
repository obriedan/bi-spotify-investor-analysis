# Spotify (SPOT) Investor/Shareholder Analysis

**MBA Business Intelligence Continuous Assessment | National College of Ireland**

Module: H9BI Business Intelligence | Lecturer: Victor del Rosal | February 2026

This repository contains the complete working project for a 5-exercise BI assignment analysing Spotify Technology S.A. (NYSE: SPOT) through an Investor/Shareholder lens. All analysis covers the 90-day window from November 2025 to February 2026.

> **Live Dashboard**: [https://obriedan.github.io/spot-investor-dashboard/](https://obriedan.github.io/spot-investor-dashboard/)

---

## Table of Contents

- [Assignment Overview](#assignment-overview)
- [Deliverables](#deliverables)
- [Project Structure](#project-structure)
- [Workflow: How This Was Built](#workflow-how-this-was-built)
  - [Phase 0: Planning & Architecture](#phase-0-planning--architecture)
  - [Phase 1: Research & Data Gathering](#phase-1-research--data-gathering)
  - [Phase 2: Initial Build (All 5 Exercises)](#phase-2-initial-build-all-5-exercises)
  - [Phase 3: Review & Improvement](#phase-3-review--improvement)
  - [Phase 4: SEC Filing Integration](#phase-4-sec-filing-integration)
  - [Phase 5: Final Polish](#phase-5-final-polish)
  - [Phase 6: Dashboard Interactivity & Responsiveness](#phase-6-dashboard-interactivity--responsiveness)
  - [Phase 7: Independent Grading Review](#phase-7-independent-grading-review)
- [AI Tools Used](#ai-tools-used)
- [Key Data Sources](#key-data-sources)
- [Git History](#git-history)

---

## Assignment Overview

The assignment required building 7 deliverable files across 5 exercises, all analysing a specific company through an assigned analytical lens:

- **Company**: Spotify Technology S.A. (assigned based on Student ID last digit: Media/Entertainment industry)
- **Analytical Lens**: Investor/Shareholder (assigned based on Student ID second-to-last digit)
- **Persona adopted**: Institutional GARP (Growth-at-Reasonable-Price) equity fund analyst evaluating whether Spotify's profitability inflection is durable and warrants continued overweight allocation
- **90-Day Currency Requirement**: All analysis must reference issues, data, and developments from the last 90 days (November 2025 - February 2026), with specific dates and source citations

---

## Deliverables

| Exercise | File | Weight | Description |
|----------|------|--------|-------------|
| Ex1 | `Ex1_Snapshot.pdf` | 15% | Current Quarter Snapshot (max 2 pages, ~500 words) |
| Ex2 | `Ex2_IssuesBrief.pdf` | 25% | Strategic Issues Brief with 3 current issues (max 4 pages) |
| Ex3 | `Ex3_Dashboard.html` + `Ex3_Screenshot.png` + `Ex3_GitHubURL.txt` | 30% | Interactive BI Dashboard deployed to GitHub Pages |
| Ex4 | `Ex4_Prompts.pdf` | 10% | Prompt Engineering Showcase (3-step chain) |
| Ex5 | `Ex5_BoardPresentation.pdf` | 20% | Q1 2026 Board Presentation (exactly 3 slides) |

Final submission files are in `submission_files/`.

---

## Project Structure

```
.
├── CLAUDE.md                    # Master AI instructions file
├── BI_CA.pdf                    # Original assignment brief
├── sources.md                   # Master citation tracker (all URLs, dates, page refs)
├── README.md                    # This file
│
├── research/                    # Raw research data (markdown)
│   ├── spotify_financials.md        # 8-quarter trailing metrics
│   ├── spotify_earnings.md          # Q3 2025 earnings call excerpts
│   ├── spotify_news.md              # 20+ news articles (Nov 2025 - Feb 2026)
│   ├── spotify_20f_extracts.md      # SEC 20-F data extracted via NotebookLM
│   └── spotify_q4_2023_to_Q2_2024_dashboard_figures.md  # Verified historical data
│
├── Ex1/                         # Exercise 1: Current Quarter Snapshot
│   ├── requirements.md
│   └── Ex1_Snapshot.html
│
├── Ex2/                         # Exercise 2: Strategic Issues Brief
│   ├── requirements.md
│   └── Ex2_IssuesBrief.html
│
├── Ex3/                         # Exercise 3: Real-Time BI Dashboard
│   ├── requirements.md
│   ├── index.html                   # Primary working file
│   ├── Ex3_Dashboard.html           # Synced copy for submission
│   ├── Ex3_GitHubURL.txt
│   └── deploy/                      # Separate git repo for GitHub Pages
│
├── Ex4/                         # Exercise 4: Prompt Engineering
│   ├── requirements.md
│   └── Ex4_Prompts.html
│
├── Ex5/                         # Exercise 5: Board Presentation
│   ├── requirements.md
│   ├── Ex5_Slide1.html              # Individual slide files
│   ├── Ex5_Slide2.html
│   ├── Ex5_Slide3.html
│   ├── Ex5_slides.css               # Shared stylesheet
│   └── Ex5_BoardPresentation.html   # Legacy single-file version
│
└── submission_files/            # Final submission-ready files
    ├── Ex1_Snapshot.pdf
    ├── Ex2_IssuesBrief.pdf
    ├── Ex3_Dashboard.html
    ├── Ex3_Screenshot.png
    ├── Ex3_GitHubURL.txt
    ├── Ex4_Prompts.pdf
    └── Ex5_BoardPresentation.pdf
```

---

## Workflow: How This Was Built

The entire assignment was completed in a single day (February 7, 2026) through a structured human-AI collaboration using Claude Code (Anthropic). The workflow progressed through 7 distinct phases, each building on the last. Below is a detailed account of every step.

### Phase 0: Planning & Architecture

**Goal**: Before writing a single deliverable, establish a comprehensive plan covering all 5 exercises.

1. **Read the full assignment brief** (13-page PDF) to understand requirements, marking criteria, and rubric for each exercise.

2. **Defined the investor persona**: The brief said "Investor/Shareholder" but didn't specify what kind. This matters because it shapes analytical priorities. We chose a **GARP (Growth-at-Reasonable-Price) institutional fund analyst** — someone who entered Spotify on the growth story and is now evaluating whether the profitability inflection is durable. This persona creates natural analytical tension: growth vs. profitability trade-offs.

3. **Designed the folder structure**: Created a self-contained project where every research source, citation, and data point lives in markdown files. The design principle was that if Claude ran out of context or credits, another AI (or human) could pick up from the folder structure alone.

4. **Created `CLAUDE.md`**: A master instructions file establishing the 90-day currency rule, citation format requirements, grade targets, and quick tips from the brief. This file acts as persistent context across conversations.

5. **Chose execution order**: Prioritised Exercise 3 (dashboard, 30% weight) first, then built exercises in dependency order: Ex3 → Ex1 → Ex2 → Ex5 → Ex4.

6. **Tooling decision**: Chose to stay in Claude Code (app) rather than CLI, since the assignment is primarily content generation with web research needs, not large-scale software engineering.

### Phase 1: Research & Data Gathering

**Goal**: Gather all source materials needed across all 5 exercises before writing anything.

1. **Earnings data**: Used Claude (Sonnet) web search agents to locate Spotify's Q3 2025 earnings release (November 4, 2025). Extracted key metrics: Revenue (EUR 4.3B), Premium Subscribers (281M), MAUs (713M), Gross Margin (31.6%), Operating Income (EUR 582M), Free Cash Flow (EUR 806M). Saved to `research/spotify_financials.md`.

2. **Earnings call transcript**: Located the Q3 2025 earnings call transcript via Motley Fool. Extracted CEO Daniel Ek quotes and management commentary. Saved to `research/spotify_earnings.md`.

3. **Recent news search** (90-day window): Conducted extensive web searches for Spotify news from November 2025 through February 2026. Found 20+ relevant articles covering:
   - January 15, 2026: US price increase to $12.99/month
   - January 22, 2026: AI "Prompted Playlists" expansion
   - January 30, 2026: Citigroup upgrade to Buy ($650 target)
   - February 4, 2026: Stock crashes to ~$440 (44% from peak)
   - February 5-6, 2026: Physical book sales, "About the Song" feature
   - December 2025: Goldman Sachs/Erste Group downgrades

   Each article saved with publication, date, URL, and summary in `research/spotify_news.md`.

4. **Competitor data**: Researched Apple Music ($10.99/month, includes lossless), YouTube Music Premium ($10.99), Amazon Music Unlimited ($10.99, includes lossless). This pricing comparison became central to the investment thesis — Spotify at $12.99 is now the most expensive mainstream music streaming service.

5. **Historical quarterly data**: For the dashboard's 8-quarter trailing charts, needed data going back to Q4 2023. Verified figures against Spotify's Q4 2023 and Q2 2024 Shareholder Decks. Saved verified figures to `research/spotify_q4_2023_to_Q2_2024_dashboard_figures.md`.

6. **Master citation tracker**: Every source was logged in `sources.md` with URL, date, and what data was extracted, creating an audit trail.

### Phase 2: Initial Build (All 5 Exercises)

**Goal**: Produce complete first drafts of all 5 exercises.

#### Exercise 3: Interactive BI Dashboard (built first — 30% weight)

- Built a single-page HTML dashboard using Chart.js (v4.4.1 CDN) for interactive charts
- **Spotify brand colours**: #1DB954 (green), #191414 (dark background), #FFFFFF, #B3B3B3
- **6 KPI cards**: Revenue, Premium Subscribers, MAUs, Gross Margin, Operating Income, Free Cash Flow — each with QoQ and YoY change indicators
- **3 trend charts**: Revenue & Operating Income (dual-axis bar/line), Subscriber & MAU Growth (dual-axis), Gross Margin Trend (line with 30% threshold)
- **Current Issues Panel**: 5 bullet points covering pricing, stock correction, AI features, content expansion, and Q4 earnings catalyst
- **Interactive features**: Chart.js tooltips on hover, legend toggling, KPI card hover lift effects, responsive CSS Grid layout
- Deployed to GitHub Pages via `gh repo create` + `gh api` for Pages configuration
- Live at: https://obriedan.github.io/spot-investor-dashboard/

#### Exercise 1: Current Quarter Snapshot

- Styled HTML document (print-to-PDF workflow)
- 3 key financial metrics in a comparison table (Q3 2025 vs Q2 2025 vs Q3 2024)
- Single most pressing challenge: Pricing Power vs. Subscriber Retention Trade-off
- Management actions for next 90 days: AI features, content expansion, Q4 earnings guidance
- Investor perspective framing at the top

#### Exercise 2: Strategic Issues Brief

- 4-page HTML document with 3 current issues through the investor lens:
  1. **Pricing Elasticity Risk** — the January 2026 price increase and its impact on subscriber retention
  2. **Stock Price Disconnect** — 44% decline from peak despite record operating performance
  3. **Platform Diversification** — rapid expansion into audiobooks, video podcasts, physical books
- Each issue includes: When it emerged, Evidence, Why NOW, Impact Assessment, Peer Comparison, and Recommendation
- 2 data visualisations: Quarterly Financial Performance table and Competitive Pricing Comparison table
- Full assumptions box establishing the GARP investor persona

#### Exercise 5: Board Presentation (3 slides)

- Initially built as a single HTML file, but it had sizing/overflow issues when printing
- **Decision**: Split into 3 separate HTML files (`Ex5_Slide1.html`, `Ex5_Slide2.html`, `Ex5_Slide3.html`) with a shared CSS file (`Ex5_slides.css`)
- Each slide prints to a single landscape PDF page, then combined
- Slide 1: Current Quarter Snapshot with 3 KPI metrics
- Slide 2: Issues requiring investor attention with evidence
- Slide 3: Recommended actions with trigger-based decision framework (Bull/Base/Bear scenarios)
- Removed CSS hover/transition effects (useless for static PDF output)

#### Exercise 4: Prompt Engineering Showcase

- Chose Option B: Multi-Step Orchestration (3-step prompt chain)
- **Step 1 (Extract & Structure)**: Transform raw Q3 2025 earnings data into a structured comparison table with trend flags
- **Step 2 (Identify Key Risk)**: Using Step 1 output + recent market context, identify the single biggest risk to the GARP thesis (pricing-induced subscriber growth stall)
- **Step 3 (Investment Recommendation)**: Convert the risk analysis into a 3-scenario decision framework (Bull 40% / Base 40% / Bear 20%) with specific price targets
- Includes orchestration reflection discussing what worked, limitations, and what could be improved

**First commit**: `8f77ee1 Initial commit: all exercise deliverables complete`

### Phase 3: Review & Improvement

**Goal**: Systematic review and improvement of all deliverables.

After the initial build, a detailed review identified multiple areas for improvement:

1. **Student details**: Added `Daniel O'Brien | 24295337 | CVC: kvo2fNOVX0` to headers/footers across all files.

2. **AI tool references**: Fixed "Opus 4" references to "Claude Opus 4" across all files and `sources.md`.

3. **Ex1 superscript citations**: Added inline superscript numbers (1-7) linking claims to the numbered sources list. This demonstrates source handling sophistication per the rubric.

4. **Ex4 placeholder fix**: Changed `[Paste Output 1 table here]` to `[Output 1 structured table inserted here -- omitted for space; see Step 1 output above]` so it reads as a human editorial note.

5. **Ex5 rebuild**: Split the single-file presentation into 3 separate HTML slides + shared CSS. Removed all hover/transition effects. Fixed table sizing and footer overflow for landscape PDF printing.

6. **Ex3 data verification**: Verified historical quarterly figures (Q4 2023 - Q2 2024) against official Shareholder Decks. Corrected Q4 2023 Operating Income to EUR -75M (loss, not profit). Added footnote on the dashboard noting data sources.

7. **Dashboard redeployment**: After corrections, synced `Ex3_Dashboard.html`, copied to deploy folder, and pushed to GitHub Pages.

**Second commit**: `3a64680 Phase 2 improvements: student details, citations, Ex5 rebuild`

### Phase 4: SEC Filing Integration

**Goal**: Strengthen analysis with primary SEC filing citations for academic rigour.

1. **20-F extraction via NotebookLM**: The user downloaded Spotify's FY2024 20-F annual report from SEC EDGAR and ingested it into Google NotebookLM. Key data was extracted with specific page references into `research/spotify_20f_extracts.md`:
   - Revenue EUR 15,673M (p.44)
   - Operating Income EUR 1,365M (p.8/F-5)
   - Free Cash Flow EUR 2,285M (p.49)
   - Premium ARPU EUR 4.69 (p.43)
   - Risk factors on user retention (p.5)
   - Content licensing obligations EUR 4.4B (pp.13, 49)
   - Competitive landscape description (p.36)

2. **Citation integration**: Wove 20-F citations with specific page numbers into:
   - **Ex1**: Profitability trajectory (20-F p.8), FCF (p.49), ARPU (p.43), user retention risk quote (p.5)
   - **Ex2 Issue 2**: FY2024 operating income and FCF (pp.8, 49)
   - **Ex2 Issue 3**: Content cost obligations (pp.13, 49), competitive landscape quote (p.36)

3. **AI tools documentation**: Added Google NotebookLM to the "AI Tools Used" section across all deliverables, demonstrating multi-tool orchestration per the rubric.

4. **Sources.md update**: Added 20-F filing details, Shareholder Deck references, competitor pricing sources.

**Third commit**: `ea60d37 Add 20-F SEC filing citations and NotebookLM as AI tool`

### Phase 5: Final Polish

**Goal**: Address remaining issues identified during review before print-to-PDF.

1. **Ex1 word count expansion**: The body text was approximately 358 words; the brief allows up to 500. Expanded to approximately 478 words by enriching existing paragraphs (not adding new sections):
   - Section 1: Added profitability trajectory context (FY2023 loss to consecutive profits), Premium ARPU, FY2024 FCF comparison
   - Section 2: Added 20-F risk factor quote on user retention, competitive pricing gap context
   - Section 3: Expanded content expansion bullet with video podcast stats (400M viewers, 500K shows)

2. **Ex4 page-break fix**: When printing to PDF, Steps 2 and 3 headers were anchored to their content blocks via `page-break-inside: avoid` on `.step-container`, causing large whitespace gaps. Fix:
   - Removed `page-break-inside: avoid` from `.step-container`
   - Added `page-break-after: avoid` to `h2`/`h3` in print media query (keeps headers attached to following content)
   - Added `page-break-inside: avoid` to `.prompt-box` and `.output-box` individually (prevents code/output blocks from splitting, while allowing the step as a whole to break across pages)

**Fourth commit**: `9c84011 Final polish: Ex1 word count expansion, Ex4 page-break fix`

### Phase 6: Dashboard Interactivity & Responsiveness

**Goal**: Ensure the dashboard meets the "interactive" requirement and is fully responsive.

1. **Interactivity analysis**: The brief says "interactive HTML dashboard" but doesn't define interactive. The marking criteria just says "Functionality: dashboard works and displays correctly" (8 marks). Assessment: existing Chart.js tooltips, legend toggling, and hover effects already qualify. However, added one explicit interactive feature to make it unambiguous.

2. **KPI click-to-expand feature**: Each of the 6 KPI cards now responds to clicks:
   - Click a card to expand it, revealing an investor-context detail note
   - E.g., clicking "Operating Income EUR 582M" shows: "Beat Q3 guidance of EUR 485M by EUR 97M. Fourth consecutive profitable quarter after FY2023 operating loss of EUR 446M (20-F p.8). Q4'25 guidance: EUR 620M."
   - Implementation: `onclick="this.classList.toggle('expanded')"` with CSS `.kpi-detail` shown/hidden via `display: none/block`
   - "Click to expand" hint text disappears when expanded

3. **Chart responsiveness fix**: Charts overflowed on mobile viewports between 450-768px. Root cause: `grid-template-columns: repeat(auto-fit, minmax(450px, 1fr))` enforced a 450px minimum width. Fix: changed to `minmax(min(450px, 100%), 1fr)` which allows charts to shrink below 450px when the viewport requires it. Also reduced chart canvas height to 250px at the 500px breakpoint.

4. **Synced and redeployed**: Updated `Ex3_Dashboard.html`, copied to deploy folder, pushed to GitHub Pages.

**Fifth commit**: `e106234 Dashboard: add KPI interactivity + fix mobile chart responsiveness`

### Phase 7: Independent Grading Review

**Goal**: Validate the submission quality by having an independent AI agent grade the work.

Spawned a separate Claude Opus agent with:
- The complete assignment brief (all 13 pages)
- Full marking criteria and rubric for each exercise
- The 7 submission files from `submission_files/`
- No context about the build process — only the brief and the deliverables

**Results: 98/100 — EXCELLENT**

| Exercise | Score | Notes |
|----------|-------|-------|
| Ex1 | 14.5/15 | Minor: could add earnings call timestamps |
| Ex2 | 24/25 | Minor: visualisations use tables not charts; Issue 3 recommendation slightly vague |
| Ex3 | 29.5/30 | Minor: limited code comments |
| Ex4 | 10/10 | Exemplary prompt engineering showcase |
| Ex5 | 20/20 | Excellent trigger-based decision framework |

---

## AI Tools Used

| Tool | Role | How It Was Used |
|------|------|----------------|
| **Claude Code (Claude Opus 4)** | Orchestrator | Project planning, architecture design, HTML generation, code writing, analysis coordination, git operations, GitHub Pages deployment |
| **Claude (Sonnet)** | Researcher | Web searches for earnings data, news articles, competitor pricing; content drafting and data compilation |
| **Google NotebookLM** | Document Analyst | Ingested Spotify's 20-F annual report (SEC filing); extracted key financial figures with specific page references |

The human directed all analytical decisions: persona choice, issue prioritisation, recommendation framing, and quality review. AI tools executed the research gathering, content generation, and technical implementation under human guidance.

---

## Key Data Sources

- **Spotify Q3 2025 Earnings Release** (November 4, 2025) — primary financial data
- **Spotify FY2024 20-F Annual Report** (SEC EDGAR) — audited financials with page references
- **Spotify Q4 2023 & Q2 2024 Shareholder Decks** — historical quarterly data verification
- **20+ dated news articles** (November 2025 - February 2026) — 90-day currency evidence
- **Competitor pricing data** — Apple Music, YouTube Music, Amazon Music

Full citation details in [`sources.md`](sources.md).

---

## Git History

```
e106234 Dashboard: add KPI interactivity + fix mobile chart responsiveness
9c84011 Final polish: Ex1 word count expansion, Ex4 page-break fix
ea60d37 Add 20-F SEC filing citations and NotebookLM as AI tool
3a64680 Phase 2 improvements: student details, citations, Ex5 rebuild
8f77ee1 Initial commit: all exercise deliverables complete
```

---

## Technical Notes

- **HTML-to-PDF workflow**: All exercises (except Ex3) were authored as styled HTML files and printed to PDF via the browser's Ctrl+P > Save as PDF. This gives precise control over page breaks, fonts, and layout.
- **Dashboard tech stack**: Single HTML file, Chart.js v4.4.1 (CDN), CSS Grid, CSS custom properties for Spotify brand colours. No build tools or frameworks.
- **Ex5 slide approach**: Split into 3 individual HTML files with a shared CSS stylesheet. Each prints to a single landscape page, then combined into one PDF. This solved overflow issues that occurred with a single-file approach.
- **Dual git repos**: The main assignment repo (this one) and a separate `Ex3/deploy/` repo for GitHub Pages deployment. The deploy folder is gitignored from the main repo.
