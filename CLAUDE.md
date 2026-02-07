# BI Assignment - Spotify (SPOT) | Investor/Shareholder Lens

## Assignment Context
- **Module**: Business Intelligence (H9BI), NCI MBA
- **Company**: Spotify Technology S.A. (NYSE: SPOT)
- **Industry**: Media/Entertainment (Student ID last digit: 7)
- **Analytical Lens**: Investor/Shareholder (Student ID second-to-last digit: 3)
- **Perspective**: Institutional investor evaluating the stock
- **Deadline**: Saturday 7 February 2026, 17:00
- **Submission**: 7 files via Moodle/Turnitin

## Investor Persona & Assumptions
All deliverables adopt this perspective (state assumptions at top of each):
- **Fund type**: Mid-cap GARP (Growth-at-Reasonable-Price) equity fund
- **Investment thesis**: Holds SPOT position based on growth story; now evaluating whether profitability inflection is durable and warrants continued overweight allocation
- **Key criteria**: Revenue growth sustainability, gross/operating margin trajectory, ARPU trends, competitive moat, FCF generation
- **Risk tolerance**: Moderate - accepts volatility for growth but needs evidence of improving unit economics
- **Time horizon**: 12-24 months (quarterly portfolio review)

## Critical Rules

### 90-Day Currency Requirement
ALL analysis MUST reference issues from the last 90 days (approx Nov 2025 - Feb 2026). Generic historical analysis will NOT receive full marks. Every issue must include:
- A specific date or quarter when it emerged
- A direct quote or citation from earnings materials, SEC filings, or dated news
- Explanation of why this is a NOW issue, not an ongoing concern

### Citation Format
Always use specific citations:
- "20-F p.47" or "Q4 2025 earnings call, 32:15" - NOT "annual report" or "earnings call"
- "Reuters, 15 Jan 2026" - NOT "news reports"
- Specific page numbers, timestamps, or section references

### Grade Target: Excellent (70-100%)
To achieve this band:
- Issues from last 30-60 days with specific dates cited
- Emerging developments identified
- Sophisticated AI orchestration with refined and validated outputs
- Clear human judgment applied throughout
- Professional-grade output quality

## Quick Tips for Success (from brief)
1. Source documents from SEC EDGAR, company IR pages, Yahoo Finance
2. The earnings call transcript is the RICHEST source for current issues - the 10-K/20-F provides context but earnings materials reveal what's happening NOW
3. Search for recent news from last 30-90 days to surface issues management is dealing with right now
4. Cite specific dates and sources: "most recent earnings call, 14:32" is better than "earnings call"
5. AVOID generic issues: "Competitive pressure" or "economic uncertainty" are perennial concerns - find the SPECIFIC challenges being discussed THIS quarter
6. Deploy GitHub Pages early - Exercise 3 carries the most weight (30%)
7. Keep the Investor/Shareholder lens in mind throughout every exercise
8. Test all deliverables before submitting: open HTML in browser, verify GitHub URL works, check PDFs render correctly
9. Let your own voice shine - YOU are guiding AI, not the other way around

## File Naming Convention (exact names required)
| Exercise | Filename | Format |
|----------|----------|--------|
| 1 | Ex1_Snapshot.pdf | PDF, max 2 pages |
| 2 | Ex2_IssuesBrief.pdf | PDF, max 4 pages |
| 3 | Ex3_Dashboard.html | HTML file |
| 3 | Ex3_Screenshot.png | PNG screenshot (backup) |
| 3 | Ex3_GitHubURL.txt | Text file with GitHub Pages URL |
| 4 | Ex4_Prompts.pdf | PDF, max 3 pages |
| 5 | Ex5_BoardPresentation.pdf | PDF, exactly 3 slides |

## Submission Checklist
- [ ] All files use correct naming convention
- [ ] PDF files are within page limits
- [ ] HTML file opens correctly in a web browser
- [ ] GitHub Pages URL is accessible and displays dashboard
- [ ] Screenshot shows complete dashboard
- [ ] All sources and AI tools are documented
- [ ] Company and lens documented based on student ID
- [ ] All issues cited are from the last 90 days with specific dates/sources

## GitHub Pages Deployment Workflow
For Exercise 3 dashboard deployment:

```powershell
cd "Ex3_Dashboard_folder"
git init
git add .
git commit -m "Initial commit"
gh repo create --source=. --public --push
gh api "repos/obriedan/repo-name/pages" -X POST -F "source[branch]=master" -F "source[path]=/"
```

Site will be live at: `https://obriedan.github.io/repo-name/`

**Important**: Main file MUST be named `index.html` for GitHub Pages root URL to work.

## Project Structure
```
sources.md              - Master citation tracker (ALL links and references)
research/               - Raw research data
  spotify_financials.md - Quarterly metrics, KPIs, trailing data
  spotify_earnings.md   - Key excerpts from earnings call/release
  spotify_news.md       - Recent news with dates and summaries
  peer_comparison.md    - Competitor data
Ex1/ through Ex5/       - Exercise folders with requirements.md and deliverables
```
