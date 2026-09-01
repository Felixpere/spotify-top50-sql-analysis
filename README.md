
#  Decoding the Hits: Analyzing the Spotify Top 50 (2019)

##  Business Problem

With fierce competition in the music industry, data-driven decisions are crucial. 
Resonance Studios challenged our team to uncover what musical traits define a global hit on Spotify.

**Hypotheses:**
- Songs with high danceability and energy are more likely to chart globally.
- Big-name artists are overrepresented in the top 50.
- Shorter songs (under 3.5 minutes) perform better on streaming platforms.

We used SQL aggregations and visual analysis to test and support these hypotheses.

---

##  Dataset

- **Source:** [Kaggle – Top 50 Spotify Songs 2019](https://www.kaggle.com/datasets/leonardopena/top50spotify2019)
- **Records:** 50
- **Features:** Track name, artist, genre, energy, valence, BPM, popularity, and more.

---

##  Data Cleaning & Preparation

Performed in `sql-spotify-top50/spotify_proyect_clean-06.ipynb` using Python (pandas):

- Renamed columns to `snake_case`.
- Cleaned `track_name` of special characters using regex.
- Grouped sub-genres into broader categories for consistency.
- Dropped rows with missing `artist_id` or `genre_id` to protect relational integrity.
- Removed duplicates and stripped whitespace from text fields.

---

##  Database Structure

Implemented in MySQL using `project spotify tables.sql`, with the analysis queries in `sql-spotify-top50/Spotify_Mysql_queries.sql`.

**Tables:**
- `artists (artist_id, artist_name)`
- `genres (genre_id, genre_name)`
- `track (track_id, track_name, artist_id, genre_id, bpm, energy, valence, etc.)`

**ERD available in:** `sql-spotify-top50/RDE.png`

Relational integrity enforced via foreign key constraints.

---

##  Technologies Used

- Python (pandas, seaborn, matplotlib)
- MySQL + Workbench
- Jupyter Notebook
- Git + GitHub
- Google Slides (presentation)

---

##  Exploratory Data Analysis & Visuals

EDA was conducted using scatterplots, bar charts, histograms, and heatmaps.

- Most tracks fell within high ranges of energy, valence, and danceability.
- Pop and Latin were dominant genres.
- Track durations centered around 3.2–3.5 minutes.

We produced over 4 high-quality visualizations that revealed key genre and feature correlations.

---

##  SQL Insights

SQL queries performed:
- JOINs between `track`, `artists`, and `genres`
- Aggregates by genre: AVG(valence), AVG(danceability)
- Filtered Top 10 tracks by tempo, valence, and popularity
- GROUP BY queries to analyze genre and artist distribution
- Subqueries to highlight standout combinations

---

##  Project Structure

```
.
├── top50.csv                                     # source dataset (Kaggle, Top 50 2019)
├── project spotify tables.sql                    # relational schema (MySQL)
└── sql-spotify-top50/
    ├── spotify_proyect_clean-06.ipynb            # cleaning, EDA and visualisations
    ├── Spotify_Mysql_queries.sql                 # analysis queries
    ├── RDE.png                                   # entity-relationship diagram
    ├── common genres valance danceability.csv    # query output
    ├── most popular tracks energy_danceability.csv
    └── high popular tracks dominant genres based on avarage energy , popularity and danceability.csv
```

> This structure ensures reproducibility and separation of concerns between cleaning, analysis, and database scripts.

---

##  Presentation Link

📽️ **[Google Slides – Final Presentation](<https://docs.google.com/presentation/d/10UWSDfKleWiMfXCu0Amp-nke_DkmER0I/edit#slide=id.p1>)
