# Exercise 3: Real-Time BI Dashboard

## Weight: 30% | Max Marks: 30 | Deliverable: Ex3_Dashboard.html + Ex3_Screenshot.png + Ex3_GitHubURL.txt

## Task
Build a single-page interactive HTML dashboard presenting current business intelligence for Spotify, tailored to the Investor/Shareholder lens. Dashboard should reflect data and issues from the most recent quarter and be deployed live via GitHub Pages.

## Required Dashboard Elements

### 1. Header
- Company name: Spotify Technology S.A.
- Analytical lens: Investor/Shareholder
- Current quarter (e.g., "Q4 2025 / Q1 2026")
- Student ID

### 2. KPI Cards (minimum 4)
Key metrics with most recent quarter values and QoQ or YoY change indicators:
- Revenue
- Premium Subscribers
- Gross Margin %
- Operating Income (or Free Cash Flow)
- (Optional: MAUs, ARPU)

### 3. Trend Charts (minimum 2)
Trailing 4-8 quarters of data, with the most recent quarter highlighted:
- Revenue trend
- Subscriber growth trend
- (Optional: Margin trend, ARPU trend)

### 4. Current Issues Panel
3-5 bullet points highlighting key challenges or opportunities from the last 90 days

### 5. Professional Styling
Color scheme matching Spotify branding:
- Primary green: #1DB954
- Dark background: #191414
- White text: #FFFFFF
- Light grey: #B3B3B3

## Technical Requirements
- Single HTML file (can include inline CSS/JS or CDN links like Chart.js)
- Data must be from the most recent available quarter
- Must render correctly when opened in a browser
- Must be deployed to GitHub Pages with a working public URL
- Main file MUST be named `index.html` for GitHub Pages

## Deliverables
1. `Ex3_Dashboard.html` - the HTML file (uploaded to Moodle)
2. `Ex3_Screenshot.png` - screenshot of dashboard as backup
3. `Ex3_GitHubURL.txt` - text file containing the GitHub Pages URL

## GitHub Deployment
```powershell
# From a dedicated folder for this dashboard
git init
git add .
git commit -m "Initial commit"
gh repo create --source=. --public --push
gh api "repos/obriedan/REPO_NAME/pages" -X POST -F "source[branch]=master" -F "source[path]=/"
```
URL will be: https://obriedan.github.io/REPO_NAME/

## Marking Criteria
| Criterion | Marks |
|-----------|-------|
| Functionality: dashboard works and displays correctly | 8 |
| Data currency: metrics are from most recent quarter | 5 |
| Visual design: professional appearance | 5 |
| Code quality: clean, readable code | 4 |
| Relevance to assigned lens and current issues | 4 |
| GitHub Pages deployment: live, accessible URL | 4 |

## Citations Used in This Deliverable
*(To be populated as content is drafted)*
