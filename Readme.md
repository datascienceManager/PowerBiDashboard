Here's the full plan laid out before the mockup:

**Step 1 — Sample data** is described below for each of the 4 reports. **Step 2 — Power BI instructions** follow. **Step 3 — Interactive dashboard mockup** is the widget below.

---

### Sample data structure (CSV format for Power BI)

**Report 1 — World Cup Pass Sales**
`customer_id, country, journey, group (Target/Control), pass_type, converted (0/1), revenue`
e.g. `C001, Saudi Arabia, Journey 1, Target, Full Pass, 1, 299`

**Report 2 — Match → Full Pass Upgrade**
`customer_id, country, journey, group, match_pass_date, full_pass_date, upgraded (0/1), upgrade_revenue, days_to_upgrade`

**Report 3 — Entertainment Engagement**
`customer_id, group, content_language, content_title, content_category, user_type, viewed (0/1), content_discovered (0/1)`

**Report 4 — Viewing Engagement**
`customer_id, group, country, team_interest, fixture, avg_minutes_watched, total_minutes, return_sessions`

---

### Power BI instructions (per report)

1. Import each CSV via **Get Data → Text/CSV**. Create a shared `dim_customer` table linked on `customer_id`.
2. Create measures: `Incremental Conversion = [Target Conv Rate] - [Control Conv Rate]` and `Incremental Revenue = [Target Revenue] - [Control Revenue]`.
3. For Report 2, add a calculated column: `Days to Upgrade = DATEDIFF([match_pass_date], [full_pass_date], DAY)`.
4. For Report 3, use `Viewer Ratio = DIVIDE(COUNTROWS(FILTER(Table, [viewed]=1)), COUNTROWS(Table))`.
5. Use slicers on `Country`, `Journey`, `Group`, `Pass Type`, `Content Language`, and `User Type` as global filters.
6. Use **Matrix visuals** for Target vs. Control breakdowns, **Bar/Column charts** for KPI comparisons, and **Card visuals** for headline incremental figures.Here's what you're looking at and how to build it in Power BI:

---

**What each tab shows you**

Tab 1 — Pass Sales Incremental gives you the four headline KPI cards (incremental revenue, conversion lift in pp, and cohort sizes), a grouped bar comparing Target vs. Control conversion by pass type, and a horizontal bar of incremental revenue by country. The matrix at the bottom is your Journey × Pass Type drill-down.

Tab 2 — Match→Full Upgrade adds a time-to-upgrade line chart (cumulative % upgraded over days), a country-level grouped bar, and the full funnel table. The median days-to-upgrade KPI is the one Power BI will need a PERCENTILE measure for.

Tab 3 — Entertainment Engagement focuses on the viewer/non-viewer ratio and content discovery rate, broken down by Arabic vs. English and by user type (New WC vs. Existing Football). The horizontal bars on the right are a quick-glance visual you'd build as a bar chart with a categorical axis.

Tab 4 — Viewing Engagement shows minutes-watched comparisons by country, a tournament-arc line chart showing how return sessions grow across stages, and a team-interest table — this one proves CRM drives actual consumption, not just transactions.

---

**The three Power BI measures you'll need most**

```
Incremental Conv Rate = 
  CALCULATE([Conv Rate], [Group] = "Target") 
  - CALCULATE([Conv Rate], [Group] = "Control")

Incremental Revenue = 
  CALCULATE([Total Revenue], [Group] = "Target") 
  - CALCULATE([Total Revenue], [Group] = "Control")

Avg Min Watched = 
  AVERAGEX(CustomerTable, [total_minutes])
```

### Below Second process to develop better power bi report 

Generated 4 CSV files (1,000 rows each) plus a comprehensive step-by-step Power BI guide. Let me start building them now.All 4 files confirmed — 1,001 lines each (header + 1,000 rows). Now let me write the complete step-by-step guide.All 5 files are valid. Let me present them all together.Here's everything you have:

**5 files ready to download:**

The Word guide is the main document — 10 phases covering every click. The four CSVs are your data, each with exactly 1,000 rows and realistic distributions (Target outperforms Control on every KPI, with the right variance to feel like real data).

---

**What the guide covers, phase by phase:**

Phase 1 — Power BI Desktop install and initial setup. Phase 2 — Power Query transformations for all four tables (data types, custom columns like `Days_Bucket`, `Viewer_Status`, `Fixture_Sort`). Phase 3 — data model and a shared `DateTable` with relationships. Phase 4 — every DAX measure you need, written out in full with copy-paste code. Phases 5–8 — one phase per report, specifying which visual type to use, which fields go where, and how to format each chart. Phase 9 — consistent formatting rules, page navigator, and publishing to Power BI Service. Phase 10 — a troubleshooting table for the seven most common issues (blank measures, wrong sort order, slow rendering, etc.).

---

**Recommended order of attack:**

Start by placing all four CSVs in the same folder, then open Power BI Desktop and work through Phases 1–3 once (they apply globally). Then build one report page at a time — Report 1 is the simplest and establishes the pattern for the others. Report 4 is the most complex due to the fixture sort logic, so leave it last.


### Third Process for power bi report enhance ment 

Let me build a much more polished, visually rich version of the guide with a proper dashboard mockup embedded.Now let me rebuild the Word guide to match this premium dark aesthetic — with colour-coded sections, a proper cover page, and styled callout boxes.Here's what's been upgraded across both the dashboard and the guide:

**Dashboard — what's new**
The design now uses a full dark navy (#0F1923) canvas with a collapsible icon sidebar, a live status badge in the header, and tab icons for each report. KPI cards have coloured left-accent bars (blue for revenue, green for conversion, purple for audience, amber for control). Charts use a dark-mode Chart.js theme with proper tooltips and dashed lines for Control series. Every table row has hover highlighting. The filter bar has toggle pills for Target/Control.

---

### With Golden color and look and feel like OTT web page 

Now I can see exactly what you're going for — the OTT platform aesthetic. Let me rebuild the dashboard to match: black background, gold/yellow accents, purple card panels, white text, that premium streaming platform feel.The dashboard now matches the OTT brand language exactly:

**What's been replicated from the TOD page:**

The top navigation bar mirrors the real  layout — "OTT" logo in gold on the left, nav links with "FIFA World Cup 2026™" in gold as the active item, and . The four-panel promo strip on the Pass Sales page echoes the "ALL 104 GAMES / ALL IN 4K HDR / ALL THE ACTION / ALL YOUR DEVICES" feature cards from the screenshot — same deep purple-navy background. The overall palette is pure black canvas, gold (#F5C518) as the primary accent for Target group data, purple panels for supporting cards, and green/blue for secondary KPIs — exactly the  colour world.

**Click through all four tabs** — Pass Sales, Match→Full Upgrade, Entertainment, and Viewing Engagement — each has its own KPI cards, charts and breakdown table in the same TOD style.

Want me to now rebuild the Word guide cover and section headers to match this  gold/black theme as well?

