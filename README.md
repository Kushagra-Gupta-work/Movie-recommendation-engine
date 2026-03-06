# Movie Recommendation Engine

**Simple content-based movie recommender (single Python script).**

This repository contains a compact content-based movie recommendation script that computes similarity between movies using textual metadata (keywords, cast, genres, director) and returns movies similar to a chosen title. No frontend or web app is included — the project is implemented as a standalone Python script that reads a CSV dataset.

---

## Repository contents

- `movie_recommender_completed.py` — main script that:
  - loads `movie_dataset.csv`
  - combines selected textual features (`keywords`, `cast`, `genres`, `director`)
  - vectorizes combined text with `CountVectorizer`
  - computes cosine similarity and prints similar movie titles.
- `movie_dataset.csv` — movie metadata used by the script.
- `README.md` — this file.

---

## How it works (implementation summary)

1. The script reads `movie_dataset.csv`.  
2. It selects features: `keywords`, `cast`, `genres`, `director`. Missing values are filled with empty strings.  
3. A `combined_features` column is created by concatenating the selected fields.  
4. `CountVectorizer` converts `combined_features` to a count matrix.  
5. Cosine similarity is computed on the count matrix.  
6. The script looks up a movie (variable `movie_user_likes`) and prints the top similar movies in descending similarity order.

*(This flow follows the code in `movie_recommender_completed.py`.)*

---

## Requirements

- Python 3 (recommended) — see the *Note* below about a small Python 2-style print usage in the script.  
- Libraries:
  - `pandas`
  - `numpy`
  - `scikit-learn`

Install dependencies with:

```bash
pip install pandas numpy scikit-learn
