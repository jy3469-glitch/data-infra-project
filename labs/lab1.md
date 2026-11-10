# Lab 1

**Name:**
**Due:** Sunday, October 25 at 11:59 PM
**Submit:** your repo URL in the Lab 1 assignment on CourseWorks

| Part | Where | File |
|---|---|---|
| **In class:** first DuckDB query on the penguins data | Session 1 | `notebooks/lab1_first_query.ipynb` |
| **At home:** two related tables of your own in DuckDB | Before Sunday | `notebooks/lab1_home_your_data.ipynb` |
| **At home:** lifecycle map of your data | Before Sunday | This file (below) |

---

## Lifecycle map of your data

In class we named five stages every data system has. Trace them for the two tables you loaded at home. Some rows ask what you did this week; the last two ask you to look ahead to the system you'll build by December. Educated guesses are fine; say where you're unsure.

**My tables:** (main table) + (second table)

| Stage | For your data | Your answer |
|---|---|---|
| **1. Ingestion** | Where did each file come from, and how did you get it (portal download, export, API)? If the source changed its format tomorrow, what would break? | I obtained PLUTO and POPS as CSV files from NYC Open Data and loaded them into DuckDB. If the source changes column names, data types, or numeric formatting, the import process or SQL queries could fail. |
| **2. Validation** | What did `DESCRIBE`, `SUMMARIZE` and the key check reveal? Name one check you'd want to run *every time* new data arrives. | I used DESCRIBE and SUMMARIZE to examine data types, value ranges, and missing values. The BBL key check showed that 385 of 390 non-null POPS BBLs matched PLUTO, while 5 did not. Two POPS records had missing BBLs. I would check missing and unmatched data especially in key column.|
| **3. Transformation** | What did you change to make the data usable (e.g. the missing-value fix)? What would you still need to clean, join or calculate to answer your question? | I adjusted CSV import settings to handle missing values and comma-formatted numbers. Next, I would join POPS with PLUTO using BBL, investigate unmatched records. |
| **4. Scheduling** | How often does the source publish updates (check its website)? If your app used this data, how often would it need to refresh to stay useful, and why? | PLUTO has quarterly major updates and monthly zoning-only updates between them. The POPS dataset lists updates every six months. I would check for new versions monthly and refresh the application when updates become available. |
| **5. Interface** | Who would want answers from this data? Write the plain-English question they'd ask, and what a good answer would show them. | Urban planners, community organizations, and residents could use this data. A question they might ask is: "Where are the POPS in my neighborhood, and what types of properties are they associated with?" A useful interface would show a map of POPS locations, space types, and associated land-use and zoning information. |

**Which stage feels most fragile for your data, and why?** (two or three sentences)

---Validation feels most fragile, especially when matching the two datasets. Five POPS records with non-null BBLs did not match PLUTO, and two records were missing BBLs entirely. Differences in data versions or parcel identifiers could affect the reliability of future spatial analyses.

## Checklist before you submit

- [ ] In-class notebook: every cell ran, including your own query and three observations
- [ ] At-home notebook: both CSVs in `data/`, both tables loaded and checked, the key relationship described, five queries each with a one-line note, three observations, two dataset cards
- [ ] This lifecycle map filled in, plus the "most fragile" answer
- [ ] Every notebook saved (Cmd+S), then committed and pushed
- [ ] Repo URL pasted into CourseWorks
