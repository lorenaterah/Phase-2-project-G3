
# In-depth Analysis of Box Office Films

## Project Overview

This project conducts a comprehensive analysis of the movie industry to uncover actionable insights for stakeholders looking to enter the market. By leveraging data from multiple sources including Box Office Mojo, IMDB, and movie_gross, we explore trends in financial performance, audience reception, and market dynamics. The goal is to guide a new movie studio in deciding what types of films to create by identifying which genres and strategies are currently most successful.

**Project Team:**
- Lorena Terah
- Sharon Kipruto
- Stephen Musyoka
- Dawa Jarso
- Salma Mwende
- Edgar Owuor

## Business Problem

Our company aims to launch a new movie studio but lacks experience in the film industry. The core objective is to determine what types of films are currently performing best at the box office and translate these findings into actionable insights for the studio head.

**Key Objectives:**
1. Identify the best-performing film genres.
2. Analyze current box office trends.
3. Identify factors contributing to a movie's success.
4. Translate findings into actionable business strategies.

## Data Sources & Understanding

We utilized a rich collection of datasets to ensure a holistic analysis:

1.  **bom.movie_gross.csv**: Box office revenue data (domestic & foreign).
2.  **tmdb.movies.csv**: Movie details, popularity, and user ratings from The Movie Database.
3.  **tn.movie_budgets.csv**: Production budgets and gross earnings (domestic & worldwide).
4.  **im.db (SQLite Database)**: Contains `movie_basics` (titles, genres, runtime) and `movie_ratings` (average rating, number of votes).

## Methodology

### Data Preparation & Cleaning
- Handled missing values and duplicates across all datasets.
- Standardized financial columns (removed `$` and `,`, converted to numeric).
- Converted date columns to datetime format and extracted release years/months.
- Created new key metrics: `profit`, `profit_ratio`, and `total_gross`.
- Merged multiple datasets to create unified analysis-ready DataFrames (`df_box`, `combined_data_with_budget`).

### Exploratory Data Analysis (EDA) & Visualizations
- **Financial Performance:** Analyzed profit ratios, top-grossing movies, and studio performance.
- **Genre Analysis:** Explored the distribution of genres and their relationship with audience ratings.
- **Temporal Trends:** Investigated box office earnings and profit trends over time and by release month.
- **Budget Impact:** Studied the correlation between production budget and worldwide gross revenue.
- **Market Dynamics:** Compared domestic vs. foreign gross earnings.

### Statistical Hypothesis Testing
We conducted rigorous tests to validate our insights:
1.  **Domestic vs. Foreign Gross:** A paired t-test confirmed a significant difference, highlighting the importance of international markets.
2.  **Studio Profitability:** An ANOVA test found no significant difference in average profits among top studios, showing brand isn't the sole profit driver.
3.  **Budget vs. Profitability:** An independent t-test revealed that high-budget films have a significantly lower profit ratio (ROI) than low-budget films.
4.  **Genre & Ratings:** An ANOVA test confirmed significant differences in average ratings across genres, with Documentaries and Dramas scoring highest.

### Predictive Modeling
A simple Linear Regression model was built to predict `worldwide_gross` based on `production_budget`.
- **R² Score:** 0.58
- **RMSE:** $138.61 Million
- **Interpretation:** For every $1 million increase in budget, worldwide gross is predicted to increase by $3.31 million. Budget is a key, but not sole, determinant of success.

## Key Insights

1. **Top Genres by Performance:** Action, Adventure, and family-friendly genres (like Animation) consistently dominate the highest grossing films. However, genres like Documentary and Drama achieve the highest average audience ratings.  
2. **The Budget Paradox:** Higher production budgets lead to higher absolute profits but a lower Return on Investment (ROI). Mid-budget films often offer the best risk-reward balance.  
3. **International Dominance:** Foreign gross revenue is statistically significantly different and often larger than domestic gross. A global appeal is crucial for blockbuster success.  
4. **Studio Strategy:** There is no significant difference in average profitability among the top studios. Success is more dependent on project selection than the studio brand alone.  
5. **Optimal Release Timing:** May, June, and July are the highest-performing months on average for releasing films, while May, November, and December see the highest total revenues.  

## Actionable Recommendations

- **For Greenlighting Projects:** Prioritize **mid-budget films** in high-performing genres like **Action, Adventure, and Animation** to optimize the balance between risk and return.
- **For Global Strategy:** Actively develop stories with **international appeal** and tailor marketing campaigns for domestic and foreign audiences separately.
- **For Release Planning:** Target a **Summer (May-July)** or **Holiday (Nov-Dec)** release window to maximize box office potential.
- **For Critical Acclaim:** To build prestige and critical reputation, invest in **Documentaries and Dramas**, which receive the highest average audience ratings.

## Technologies Used

- **Programming Language:** Python
- **Libraries:** Pandas, NumPy, Matplotlib, Seaborn, Scikit-learn, SciPy, StatsModels
- **Database:** SQLite
- **Environment:** Jupyter Notebook

## 📁 Project Structure

```
├── Data/                           # Raw data files 
├── Cleaning_and_Analysis.ipynb     # Main Jupyter Notebook
├── Notebooks                       # Individual Jupyter notebooks
├── README.md                       # Project documentation (this file)
└── (Cleaned_Data/)                 # Processed datasets (optional)
```

## 📊 Tableau Dashboard

For an interactive visualization of these insights, please refer to our Tableau dashboard:
> https://public.tableau.com/app/profile/stephen.muema/viz/MovieIndustryAnalysis_17630239953860/MovieIndustryAnalysis?publish=yes

---

**Conclusion:** This analysis provides a data-driven foundation for launching a successful movie studio, emphasizing strategic genre selection, smart budgeting, and a global market focus.