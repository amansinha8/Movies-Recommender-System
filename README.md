# Movie Recommendation System

This project is a content-based movie recommendation system that uses data from the TMDb API. The system recommends movies similar to a selected title based on their genres, keywords, cast, crew, and overview.

---

## Features

1. **Data Preprocessing**:
   - Merged datasets (`tmdb_5000_movies.csv` and `tmdb_5000_credits.csv`) based on the movie title.
   - Selected and cleaned columns: `movie_id`, `title`, `overview`, `genres`, `keywords`, `cast`, `crew`.
   - Converted JSON-like data in columns to lists of relevant values using `ast.literal_eval`.

2. **Data Transformation**:
   - Combined multiple columns (`overview`, `genres`, `keywords`, `cast`, `crew`) into a single `tags` column.
   - Applied text preprocessing:
     - Removed spaces and converted text to lowercase.
     - Stemmed words to their base form using `PorterStemmer`.

3. **Feature Extraction**:
   - Used the `CountVectorizer` to create feature vectors for text data.
   - Limited features to the top 5000 most frequent words, removing English stop words.

4. **Similarity Calculation**:
   - Calculated pairwise cosine similarity between movie vectors to find similar movies.

5. **Recommendation Functionality**:
   - Developed a recommendation function that:
     - Retrieves the top 5 similar movies for a given movie.
     - Fetches movie posters using the TMDb API.

6. **Web Application**:
   - Built an interactive web app using **Streamlit**:
     - Allows users to select a movie from a dropdown list.
     - Displays recommended movies with their posters.

7. **Pickle Serialization**:
   - Saved the processed data and similarity matrix using `pickle` for quick loading in the Streamlit app.

---

## Requirements

Install the required libraries using:
```bash
pip install pandas numpy scikit-learn nltk streamlit requests
