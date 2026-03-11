# Survey Analysis

Analyze developer survey results from CSV exports (e.g. Google Forms). The CSV header row contains the questions, every subsequent row is one response.

## Input

- A CSV file in `tmp/` containing survey responses
- The user specifies which column maps to which analysis type (or infer from column headers)

## Analysis Steps

### 1. Parse & Classify Columns

Identify column types from headers:

- **Team column** — used to segment all analysis by team
- **NPS question** — numeric 0-10 scale ("How likely are you to recommend...")
- **Ordinal questions** — ordered categories (e.g. "Very easy" → "Very difficult", "All of the time" → "Never")
- **Agreement statements** — Likert scale ("Strongly agree" → "Strongly disagree")
- **Free-text questions** — open-ended comments and feedback

### 2. eNPS Analysis

For the NPS question:

- Classify: Promoters (9-10), Passives (7-8), Detractors (0-6)
- Calculate: eNPS = % Promoters - % Detractors
- Report: overall + per team
- Include: absolute counts, percentages, mean, median, score distribution

### 3. Numeric Rating Analysis

For ordinal and agreement questions:

- Map responses to numeric scale (e.g. "Very easy" = 5, "Strongly agree" = 5)
- Calculate per question: average, distribution (absolute + relative)
- Calculate favorable % (top-2) and unfavorable % (bottom-2)
- Rank statements by favorability to surface strengths and concerns
- Per-team averages table — this is the main heatmap view

### 4. Free-Text Theme Clustering

For every free-text column:

- Read all responses and cluster into recurring themes
- Separate **positive** and **negative** sentiments
- Count mentions per theme
- Map themes to teams
- Group themes by topic area (e.g. "AI Tooling", "Dev Environment", "Processes & Collaboration")

### 5. Summary

Synthesize a key takeaways section:

- Top strengths (backed by data)
- Priority improvement areas (ranked by frequency + severity)
- Teams needing attention (low eNPS or multiple low scores)

## Output

### Markdown Analysis

Save a comprehensive analysis document to `tmp/` containing all sections above with tables and key observations.

### CSV Tabs for Google Sheets

Generate individual CSV files in `tmp/survey-csvs/` designed as tabs to sit alongside the raw data in a Google Sheet:

| Tab | Content |
|-----|---------|
| eNPS Overall | Category breakdown, score distribution, overall eNPS |
| eNPS by Team | Per-team promoters/passives/detractors + eNPS |
| Ordinal Questions Overall | Per-question response distributions |
| Agreement Statements Overall | Full Likert distribution + favorable/unfavorable % |
| Per-Team Averages | All numeric questions averaged per team, including eNPS — **main heatmap table** |
| Ordinal by Team | Per-team distributions for each ordinal question |
| Themes: [Topic] | One CSV per theme cluster (sentiment, theme, mentions, teams) |
| Requested Tools | Tool wishlist with mention counts (if applicable) |

### Memory

- Save key metrics and file locations to memory for future reference
- Link from `MEMORY.md` to a dedicated survey memory file with details

## Conventions

- Use Python (via Bash) for all numeric calculations — do not calculate manually
- Always report both absolute counts and percentages
- Sort teams by score/eNPS descending in tables
- Keep theme names concise but descriptive
- Include team abbreviations in theme tables for scannability
