# Hulu Titles EDA (Movies & TV Shows)

Small Exploratory Data Analysis (EDA) project using a Hulu titles dataset.  
Goal: practice data cleaning, grouping, and visualization in pandas/seaborn.

## Dataset
File: `data/hulu_titles.csv`  
Main columns used: `type`, `country`, `date_added`, `release_year`, `rating`, `duration`, `listed_in`

Notes:
- `country` and `listed_in` contain multiple values in one cell (comma-separated), so I used **split + explode** for analysis.
- Some `rating` values were actually durations (e.g., `"90 min"`, `"2 Seasons"`), so I handled/flagged that issue.

## Questions Answered
1. What’s the split of Movies vs TV Shows?
2. Which countries contribute most content?
3. How has content changed over `release_year` and `date_added`?
4. What are the top genres (`listed_in`)?
5. How are ratings related to other attributes (type/genres)?

## Key Takeaways (high-level)
- Movies vs TV Shows are close in count (TV Shows slightly higher in this dataset).
- The United States contributes the most titles; Japan and the UK are also major contributors.
- Top genres include Drama, Comedy, Action/Adventure, and Documentaries.
- Hulu additions (`date_added`) increase strongly in recent years (visible in monthly/yearly trends).
- Because genres are multi-label, exploding `listed_in` means a single title can be counted under multiple genres.

## How to Run
1. Clone this repo
2. Install requirements:
   ```bash
   pip install -r requirements.txt
3. Open and run the notebook: `Hulu_EDA.ipynb`

## Repo Contents
- `Hulu_EDA.ipynb` - main notebook
- `requirements.txt` - dependencies
- `data/hulu_titles.csv` - dataset used

## Limitations / Assumptions
- Many missing values in `country`
- Only `release_year` is available (no full release date), so some time-based analyses are approximate
- Multi-genre titles are counted multiple times when using exploded genres
