# footystats-analyze-game (alias: fag)

## Description
Analyzes a FootyStats match by collecting key stats from the game page and both individual team pages, then exports the data to a CSV/Excel file.

## Required Tabs
Open the following 3 tabs before running:
1. **Game/H2H page** — e.g. `https://footystats.org/russia/team-a-vs-team-b-h2h-stats`
2. **Home team page** — e.g. `https://footystats.org/clubs/home-team`
3. **Away team page** — e.g. `https://footystats.org/clubs/away-team`

> Note: On the game page, the **HOME team is listed on the LEFT** and the **AWAY team is on the RIGHT**.

## Data to Collect

### From the Home Team Page (home context stats):
| Field | Where to Find |
|---|---|
| Home Form (PPG) | Top of page under "Home Form" — e.g. 2.82 |
| Home Record (W - D - L) | Stats table → Home Form row → W, D, L columns |
| Table Position | Stats description text — e.g. "1st out of 18" |
| % Goals Scored at Home | Goals section → Scored Over 0.5 FT → At Home column |
| Over 0.5 Goals % (Home) | Over/Under section → Over 0.5 → At Home column |
| Over 1.5 Goals % (Home) | Over/Under section → Over 1.5 → At Home column |
| Current Home Form (Last 5) | Stats table → Home Form → Last 5 column (e.g. W-W-W-W-W) |
| Current Overall Form (Last 5) | Stats table → Overall → Last 5 column (e.g. W-W-W-W-W) |

### From the Away Team Page (away context stats):
| Field | Where to Find |
|---|---|
| Away Form (PPG) | Top of page under "Away Form" — e.g. 0.64 |
| Away Record (W - D - L) | Stats table → Away Form row → W, D, L columns |
| Table Position | Stats description text — e.g. "12th out of 18" |
| % Goals Scored Away | Goals section → Scored Over 0.5 FT → At Away column |
| Over 0.5 Goals % (Away) | Over/Under section → Over 0.5 → At Away column |
| Over 1.5 Goals % (Away) | Over/Under section → Over 1.5 → At Away column |
| Current Away Form (Last 5) | Stats table → Away Form → Last 5 column |
| Current Overall Form (Last 5) | Stats table → Overall → Last 5 column |

### From the Game/H2H Page:
| Field | Where to Find |
|---|---|
| H2H Record | "Past H2H Results" section — e.g. Fakel 1 - 0 - 0 FK Chernomorets |

## Output Format (CSV/Excel)

Export as a CSV with the following structure:

```
, HOME TEAM, AWAY TEAM
Team, [Home Team Name], [Away Team Name]

--- FORM & RECORD ---
PPG (Home/Away Context), [Home PPG], [Away PPG]
Record (W - D - L), [HW - HD - HL], [AW - AD - AL]
Table Position, [Home Position], [Away Position]

--- GOALS ---
% Goals Scored At Home/Away, [Home Scored Over 0.5%], [Away Scored Over 0.5%]
Over 0.5 Goals %, [Home %], [Away %]
Over 1.5 Goals %, [Home %], [Away %]

--- CURRENT FORM ---
Current Home/Away Form (Last 5), [H form], [A form]
Current Overall Form (Last 5), [H overall], [A overall]

--- HEAD TO HEAD ---
H2H Record (W - D - L), [Home team H2H], [Away team H2H]
Last Meeting, [result], 
```

## Steps

1. Open the 3 required tabs (game page + home team page + away team page)
2. Read each page using the get_page_text tool
3. Extract all fields listed above
4. Build a CSV string with the structure shown
5. Run the following JavaScript on the game tab to trigger the download:

```javascript
const csv = `...your CSV content here...`;
const blob = new Blob([csv], {type: 'text/csv;charset=utf-8;'});
const url = URL.createObjectURL(blob);
const a = document.createElement('a');
a.href = url;
a.download = '[home-team]-vs-[away-team]-analysis.csv';
document.body.appendChild(a);
a.click();
document.body.removeChild(a);
URL.revokeObjectURL(url);
```

## Example Output (Fakel vs FK Chernomorets, Mar 14 2026)

| | HOME TEAM | AWAY TEAM |
|---|---|---|
| Team | Fakel | FK Chernomorets Novorossiysk |
| PPG (Home/Away) | 2.82 | 0.64 |
| Record (W-D-L) | 10 - 1 - 0 | 1 - 4 - 6 |
| Table Position | 1st | 12th |
| % Goals Scored | 91% | 64% |
| Over 0.5 Goals % | 91% | 100% |
| Over 1.5 Goals % | 45% | 73% |
| Home/Away Form (Last 5) | W-W-W-W-W | W-L-L-L-D |
| Overall Form (Last 5) | W-W-W-W-W | W-D-W-L-W |
| H2H Record (W-D-L) | Fakel: 1-0-0 | FK Chernomorets: 0-0-1 |

## Notes
- Always check whether Home/Away context is correct (home team stats in home column, away team stats in away column)
- The CSV file is named `[home-team]-vs-[away-team]-analysis.csv`
- Premium stats (Corners, Cards, Odds) are not included as they require a paid account
