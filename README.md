# Movie Recommendation System

A content-based movie recommendation engine built in Python and SQL, developed as part of my MSc Data Analytics coursework. The system surfaces the five most similar movies to any given input title, drawing on genre, keyword, cast, popularity, and user rating data.

---

## Project Overview

Built on a dataset of thousands of movies, this project covers three areas of analysis:

1. **Recommendation Engine** — a content-based similarity system that matches movies across multiple dimensions
2. **International Production Analysis** — SQL-based exploration of which countries produce the most non-English language content and co-production patterns
3. **Budget vs Revenue Analysis** — statistical investigation into whether larger budgets lead to greater revenue, including correlation testing, regression modelling, and profitability thresholds

---

## Tech Stack

- **Python** — Pandas, NumPy, Scipy, Matplotlib, Seaborn
- **SQL** — PandaSQL for relational queries on DataFrames
- **Jupyter Notebook**


---

## Recommendation Engine

The core function takes a movie title and returns the five most similar movies ranked by popularity.

```python
get_matching_movies('The Matrix')
```

**Similarity is assessed across:**
- Genre overlap
- Keyword/theme similarity
- Cast
- User ratings and vote count
- Popularity score

**Edge cases handled:**
- Movie not in dataset → prints a warning message
- Empty string provided → returns the overall most popular movies in the library

### Example Outputs

```python
get_matching_movies('The Matrix')
# Returns five similar movies ranked by popularity
Getting movie suggestions...


1. I, Robot (2004)

Starring: Will Smith as Del Spooner

Overview:
In 2035, where robots are common-place and abide by the three laws of robotics, a techno-phobic cop investigates an apparent suicide. Suspecting that a robot may be responsible for the death, his investigation leads him to believe that humanity may be in danger.

Average vote: 6.7/10
Runtime: 115 minutes


2. Equilibrium (2002)

Starring: Christian Bale as John Preston

Overview:
In a dystopian future, a totalitarian regime maintains peace by subduing the populace with a drug, and displays of emotion are punishable by death. A man in charge of enforcing the law rises to overthrow the system.

Average vote: 6.9/10
Runtime: 107 minutes


3. Hollow Man (2000)

Starring: Kevin Bacon as Sebastian Caine / Hollow Man

Overview:
Cocky researcher, Sebastian Caine is working on a project to make living creatures invisible and he's so confident he's found the right formula that he tests it on himself and soon begins to vanish. The only problem is – no-one can determine how to make him visible again. Caine's predicament eventually drives him mad, with terrifying results.

Average vote: 5.6/10
Runtime: 112 minutes


4. The Chronicles of Riddick (2004)

Starring: Vin Diesel as Riddick

Overview:
After years of outrunning ruthless bounty hunters, escaped convict Riddick suddenly finds himself caught between opposing forces in a fight for the future of the human race. Now, waging incredible battles on fantastic and deadly worlds, this lone, reluctant hero will emerge as humanity's champion - and the last hope for a universe on the edge of annihilation.

Average vote: 6.3/10
Runtime: 119 minutes


5. Deep Blue Sea (1999)

Starring: Thomas Jane as Carter Blake

Overview:
On a remote former submarine refueling facility called Aquatica, a team of scientists are searching for a cure for Alzheimer's disease. Dr. Susan McAlester genetically engineers three Mako sharks, intending to increase their brain capacity so that they can harvest the tissue as a cure for Alzheimer's. Unfortunately, the increased brain capacity also makes the sharks smarter, faster, and more dangerous. Aquatica's financial backers are skeptical and nervous about the tests, and send a corporate executive to visit the facility.

Average vote: 5.6/10
Runtime: 105 minutes

get_matching_movies('DSA8002 the Movie')
Warning!
No movie found with the title: "DSA8002 the Movie". Please try again!


```

---

## Key Findings

### Budget vs Revenue
- Calculated the percentage of movies that make a loss (revenue < budget)
- Median revenue-to-budget ratio reveals typical return on investment
- Regression model used to predict revenue for a $10M budget
- Analysis suggests a minimum investment threshold above which profitability becomes significantly more likely

### International Production
- Identified the volume of non-English language movies in the library
- Ranked countries by primary and secondary production contributions
- Explored co-production patterns between country pairs

