# Bangladesh Crime Data Analysis Dashboard 2024

##  Overview
Welcome to the **Bangladesh Crime Data Analysis Dashboard 2024**—a beginner-friendly Power BI project that turns raw crime stats into actionable insights. Built with love (and a lot of coffee), this dashboard helps spot trends, hotspots, and future risks in Bangladesh's 2024 crime data. Whether you're a newbie analyst or a policy pro, it's designed to feel like a friendly chat: Simple visuals, easy slicers, and forecasts that say, "Hey, watch this!"

- **Total Cases Analyzed:** 157,624 (Jan–Nov 2024; Dec projected ~13K).
- **Key Focus:** Narcotics (46K cases, 29%), regional disparities (rural ranges: 80%), and seasonal spikes (March: 17K).
- **Goal:** Empower policing with patterns—like a crystal ball for crime prevention.

**Human Touch:** Crime data can be heavy, but this tool lightens the load. Use it to make a difference—one insight at a time.
### [Power BI Live DashBoard](https://app.powerbi.com/groups/me/reports/ba48d9ad-3e8b-436c-9e89-78fa1d815f7c/89fd5550dbb8e2710130?experience=power-bi)
##  Quick Start
No PhD required! Get up and running in 5 minutes.

### Prerequisites
- **Power BI Desktop** (free: [Download here](https://powerbi.microsoft.com/desktop/)).
- **Data File:** `Crime_Statistics_2024.xlsx` (included; 187 rows of monthly/unit crime logs).
- **Skills:** Basic mouse clicks— we'll guide the rest.

### Setup Steps
1. **Open Power BI Desktop** > **Get Data** > **Excel** > Select `Crime_Statistics_2024.xlsx`.
2. **Load & Transform:** Power Query auto-cleans (nulls → 0, types fixed). Hit **Close & Apply**.
3. **Import Dashboard:** Download the `.pbix` file from [Releases](https://github.com/Jagan515/Data-Analysis-Dashboard-Report-2024) (or build from scratch using our guide).
4. **Explore:** Slicers on the side—click "March" or "DMP" to zoom. Forecast? Analytics pane > On!
5. **Share:** Publish to Power BI Service (free account) > Embed or export PDF.

**Beginner Tip:** Stuck? Slicers = your remote control. Change one, everything updates—like Netflix categories.

##  Dashboard Walkthrough
Our 4-page setup (plus predictive bonus) is intuitive: Flip like a book, drill like a pro.

### Page 1: Overview (The "Wow" Entry)
- **KPIs:** Cards for totals (157K), top crime (narcotics 29%), ratio (metro:range 1:4).
- **Line Chart:** Monthly trends (green wiggle: Jan 13K → Mar 17K dip to Aug 9K).
- **Map:** Regional bubbles (Dhaka Range biggest).
- **Why?** 30-second scoop for execs.

### Page 2: Monthly Trends (Pattern Hunt)
- **Line + Bars:** Totals + narcotics overlay. Forecast dotted line (Dec ~13K).
- **Table:** Month-by-month with % change (e.g., +17% Feb).
- **Slicer Magic:** Filter Q1—watch spikes.
- **Insight:** Q2 peaks? Plan patrols.

### Page 3: Crime Types (Bucket Breakdown)
- **Treemap:** Big squares for Other (46%) vs. tiny Riot (0.1%).
- **Stacked Bar:** Types layered over months—narcotics towers.
- **What-If:** Slider: "Cut drugs 20%?" See impact.
- **Insight:** 75% in two types—focus there!

### Page 4: Regions & Top 5 (Hotspot Heroes)
- **Filled Map:** Metro green, ranges blue—Dhaka/Chittagong red-hot.
- **Donuts:** Per-unit top crimes (DMP: Other 41%).
- **Matrix:** Ranked top 5 (e.g., DMP: Narcotics #2, 5K cases).
- **Insight:** Rural 80% load—decentralize resources.

### Bonus: Predictive Page (Future Gaze)
- **Extended Lines:** DAX TREND + ARIMA (Dec dip to 12.7K; 2025 ~12K/month).
- **Multi-Series:** Narcotics forecast (cooling to 3.5K).
- **Build Hack:** Analytics > Forecast—zero code!

**Visual Style:** Green = safe, red = alert. Mobile-friendly—shrinks like a pro.

## 🛠️ Tech Stack & Builds
Built for beginners—copy-paste friendly.

### Data Flow
- **Source:** Excel (`Crime_Statistics_2024.xlsx`—Jan-Nov, 17 units, 16 types).
- **ETL (Power Query):** 8 steps: Load > Promote headers > Fix types > Nulls=0 > Remove dups. 100% valid output.
- **Model:** Star schema (Fact: Crimes; Dims: Units/Months). Relationships: 1:*.
- **DAX Magic:** 
  - `Total Cases = SUM('Crime Stats'[Total Cases])`
  - `Rank = RANKX(ALL([Type]), [Count], DESC)`
  - `Forecast = TREND([Cases], [Month_Num], {12})` (Dec pred).
- **Visuals:** 20+ (lines, maps, donuts). Themes: Custom green/red.

### Beginner Build Guide (10 Steps)
1. **Import:** Get Data > Excel.
2. **Query:** Transform > Replace nulls=0 > Close.
3. **Model:** Manage Relationships > Auto-detect.
4. **Measure:** Modeling > New > Paste DAX.
5. **Visual:** Drag Line > X: Month, Y: Total.
6. **Slicer:** Canvas > Slicer > Month Name.
7. **Forecast:** Visual > Analytics > Forecast > On (periods=3).
8. **Map:** Visual > Map > Location: Unit, Size: Cases.
9. **Theme:** View > Themes > Browse (green.json).
10. **Publish:** Home > Publish > Share link.

**Time:** 30 mins first try. Errors? Check types—DAX hates text in numbers.

### Predictive Boost (Python Optional)
- **DAX Linear:** Built-in TREND—easy.
- **ARIMA:** Python visual > Script: `from statsmodels...` (full in repo).

##  Key Insights & Stories
From our crunch:
- **Trends:** Spring surge (17K Mar), monsoon mercy (9K Aug—618 murders outlier).
- **Types:** Other/Narcotics = 75%—misc + drugs dominate.
- **Regions:** Ranges 80% (Dhaka 25K)—rural needs love.
- **Forecasts:** 2025 mild dip (12K/month)—narcotics cooling, but repression steady.
- **Aha!:** 1:4 metro:range—urban density vs. rural volume.

**Human Story:** Behind 157K numbers? Real people. Use this to protect—e.g., hotlines for repression (17K cases).

##  Recommendations
Actionable, like a to-do list:
1. **Narcotics:** 50% budget to ranges (Dhaka/Chittagong raids).
2. **Social:** Women/child campaigns (1.5K/month steady).
3. **Seasonal:** Aug festivals—extra patrols (curb 618 murders).
4. **Tech:** Add real-time feeds (e.g., API for 2025).
5. **You:** Tweak What-Ifs—simulate "+10% policing."

**ROI?** Spot patterns → 10% case drop (our forecast sim).

##  Contributing
Love it? Fork & tweak!
- **Issues:** Bug in forecast? Open one.
- **Pull Requests:** New visual? Tag @grok-xai.
- **Code of Conduct:** Be kind—like this report.

Beginner? Start with slicers—easy wins.

##  References
- **Data:** User-uploaded `Crime_Statistics_2024.xlsx` (hypothetical Bangladesh Police; real: bbp.gov.bd).
- **Tools:** Power BI Docs ([powerbi.microsoft.com](https://powerbi.microsoft.com)); DAX Guide ([dax.guide](https://dax.guide)).
- **Forecasts:** Statsmodels ARIMA (Python 3.12).
- **Inspo:** "Storytelling with Data" by Cole Nussbaumer Knaflic (fun read).


##  License
MIT—free to remix, just credit us. (For fun, not harm.)


---
