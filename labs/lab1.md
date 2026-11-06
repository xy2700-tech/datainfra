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

**My tables:** (inputs) + (provisions)

| Stage | For your data | Your answer |
|---|---|---|
| **1. Ingestion** | Where did each file come from, and how did you get it (portal download, export, API)? If the source changed its format tomorrow, what would break? | I downloaded both tables from github, where they existed as csv files |
| **2. Validation** | What did `DESCRIBE`, `SUMMARIZE` and the key check reveal? Name one check you'd want to run *every time* new data arrives. | I would run DESCRIBE everytime to see what is the type of data each column contains, a common error is columns that are supposed to contain numerical data returning as varchar due to rows that contain NULL|
| **3. Transformation** | What did you change to make the data usable (e.g. the missing-value fix)? What would you still need to clean, join or calculate to answer your question? | I changed the NULL values under share_provided into 0|
| **4. Scheduling** | How often does the source publish updates (check its website)? If your app used this data, how often would it need to refresh to stay useful, and why? | The source updates roughly every year and they are compiled manually by analysts |
| **5. Interface** | Who would want answers from this data? Write the plain-English question they'd ask, and what a good answer would show them. | Anyone who cares about the semiconductor supply chain will want to consult this data set. They might ask what company dominates the market for any process in chip design and manufacturing, a good answer will return the provider's name and market share for each process|

**Which stage feels most fragile for your data, and why?** It feels fragile during the transformation stage because there are a lot of missing data due to companies not disclosing information on their market share. The column of market share takes numbers and treating absent data of zero will enable analysis but falsely represent the how much actual market share on any step of chip design a company holds.Also the provider list has both countries and companies under the same column.

---

## Checklist before you submit

- [ ] In-class notebook: every cell ran, including your own query and three observations
- [ ] At-home notebook: both CSVs in `data/`, both tables loaded and checked, the key relationship described, five queries each with a one-line note, three observations, two dataset cards
- [ ] This lifecycle map filled in, plus the "most fragile" answer
- [ ] Every notebook saved (Cmd+S), then committed and pushed
- [ ] Repo URL pasted into CourseWorks
