# 🎬 Movie Recommender System

A content-based movie recommendation system that suggests similar movies using machine learning. Built with Python, Scikit-learn, and Streamlit.

## Features

- Recommends 5 similar movies based on genres, keywords, cast, crew, and plot
- Interactive web interface with movie posters
- Uses cosine similarity on 5000+ movies from TMDB dataset

## Installation

```bash
# Clone the repository
git clone https://github.com/yourusername/movie-recommender-system.git
cd movie-recommender-system

# Install dependencies
pip install -r requirements.txt
```

## Dataset

Download [TMDB 5000 Movie Dataset](https://www.kaggle.com/tmdb/tmdb-movie-metadata) and place files in the input directory:
- `tmdb_5000_movies.csv`
- `tmdb_5000_credits.csv`

## Usage

### Train the Model
```bash
python notebook86c26b4f17.py
```

This generates `movie_list.pkl` and `similarity.pkl` in the model folder.

### Run the App
```bash
streamlit run app.py
```

Open browser at `http://localhost:8501`, select a movie, and get recommendations!

## How It Works

1. **Data Processing**: Merges movies and credits data, extracts genres, keywords, top 3 cast, and director
2. **Feature Engineering**: Combines all features into a single text column
3. **Vectorization**: Uses CountVectorizer (5000 features, removes stop words)
4. **Similarity**: Calculates cosine similarity between all movies
5. **Recommendation**: Returns top 5 most similar movies

## Technologies Used

- Python, Pandas, NumPy
- Scikit-learn (CountVectorizer, Cosine Similarity)
- Streamlit
- TMDB API (for movie posters)

## API Setup

Get your TMDB API key from [here](https://www.themoviedb.org/settings/api) and replace in `app.py`:

```python
api_key = "YOUR_API_KEY_HERE"
```

## Project Structure

```
movie-recommender-system/
├── notebook86c26b4f17.py    # Model training script
├── app.py                    # Streamlit app
├── requirements.txt          # Dependencies
├── model/
│   ├── movie_list.pkl       # Processed data
│   └── similarity.pkl       # Similarity matrix
└── input/
    ├── tmdb_5000_movies.csv
    └── tmdb_5000_credits.csv
```

## Requirements.txt

```
pandas
numpy
scikit-learn
streamlit
requests
```

## Author

Your Name - [GitHub](https://github.com/yourusername)

