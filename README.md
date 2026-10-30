#  Movie Recommendation System


## Approach

Two movies are considered similar if the same users rated them in a similar way.

1. Load ratings (`u.data`) and movie details (`u.item`)
2. Merge both on `movie_id`
3. Build a movie × user rating matrix (missing ratings filled with 0)
4. Fit a k-Nearest Neighbors model with cosine distance
5. For a given movie, return its nearest neighbors as recommendations

## Dataset

MovieLens 100k by GroupLens: 100,000 ratings from 943 users on 1,682 movies.

| File | Contents |
|------|----------|
| `u.data` | user id, movie id, rating, timestamp |
| `u.item` | movie id, title, release date, genres |

Download: https://grouplens.org/datasets/movielens/100k/

## Tech Stack

- Python
- pandas, NumPy
- scikit-learn
- matplotlib, seaborn

## Setup

1. Clone the repository

   ```bash
   git clone https://github.com/<your-username>/movie-recommendation-system.git
   cd movie-recommendation-system
   ```

2. Install dependencies

   ```bash
   pip install numpy pandas matplotlib seaborn scikit-learn jupyter
   ```

3. Keep `u.data` and `u.item` in the same folder as the notebook
4. Open `Movie_Recommendation.ipynb` and run all cells

## Usage

```python
movie_recommendation('12 Angry Men (1957)')
```

Returns a list of similar movie titles.

## Project Structure

```
├── Movie_Recommendation.ipynb
├── u.data
├── u.item
└── README.md
```

## Limitations

- **Cold start:** new movies with no ratings can't be recommended
- **Sparse data:** most users rate only a few movies
- **Unreliable neighbors:** movies with very few ratings can give weak results

## Future Work

- Filter out movies with very few ratings
- Mean-center ratings per user
- User-based collaborative filtering
- Hybrid model using genre information
- Evaluation with precision@k / RMSE
- Web app using Streamlit

## Acknowledgements

Dataset provided by [GroupLens Research](https://grouplens.org/).
