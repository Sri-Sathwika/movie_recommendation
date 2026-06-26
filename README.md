# 🎬 Movie Recommender System

A **Content-Based Movie Recommendation System** built using Python and machine learning techniques that recommends movies based on their content similarity. The system analyzes movie metadata such as genres, keywords, cast, director, and plot overview to suggest movies that share similar characteristics.

---

## 📌 Project Overview

This project implements a **content-based filtering recommendation system** using the **TMDB 5000 Movies Dataset**. Unlike collaborative filtering systems that rely on user ratings, this recommender generates suggestions by analyzing the intrinsic features of movies.

The recommendation pipeline involves:

* Data cleaning and preprocessing
* Feature engineering
* Natural language processing (NLP)
* Text vectorization using Bag-of-Words
* Similarity computation using Cosine Similarity

Given a movie title as input, the system returns the top 5 most similar movies.

---

## 🚀 Features

* Content-based movie recommendation engine
* Uses movie metadata including:

  * Genres
  * Keywords
  * Plot overview
  * Top 5 cast members
  * Director
* Text preprocessing and stemming
* Bag-of-Words feature extraction
* Cosine similarity-based recommendations
* Fast and scalable similarity search

---

## 📂 Dataset

This project uses the **TMDB 5000 Movie Dataset** from Kaggle.

Dataset:

* `tmdb_5000_movies.csv`
* `tmdb_5000_credits.csv`

Source:
https://www.kaggle.com/datasets/tmdb/tmdb-movie-metadata

---

## 🛠️ Technologies Used

* Python
* Pandas
* NumPy
* Scikit-learn
* NLTK
* Pickle

---

## 📊 Project Workflow

```text
TMDB Dataset
      ↓
Data Cleaning
      ↓
Feature Selection
      ↓
Feature Engineering
      ↓
Text Preprocessing
      ↓
Stemming
      ↓
Bag of Words Vectorization
      ↓
Cosine Similarity Matrix
      ↓
Movie Recommendation Engine
```

---

## ⚙️ Data Preprocessing

### Dataset Merging

The movies and credits datasets were merged using the movie title.

### Feature Selection

The following features were selected:

* `movie_id`
* `title`
* `overview`
* `genres`
* `keywords`
* `cast`
* `crew`

### Feature Engineering

* Extracted genre names
* Extracted keyword names
* Selected the top 3 cast members
* Extracted only the director from the crew data
* Combined all features into a unified textual representation called `tags`

Example:

```text
space future sciencefiction
christophernolan
matthewmcconaughey
annehathaway
```

---

## 🧠 Natural Language Processing

The following NLP techniques were applied:

* Tokenization
* Lowercasing
* Stop-word removal
* Porter Stemming
* Bag-of-Words vectorization

Example:

```text
love
loved
loving
```

becomes:

```text
love
```

---

## 🔢 Feature Extraction

Movie metadata was transformed into numerical vectors using **CountVectorizer**.

Parameters used:

```python
CountVectorizer(
    max_features=5000,
    stop_words='english'
)
```

This produced a feature matrix of shape:

```text
4806 × 5000
```

where:

* Rows represent movies
* Columns represent the most important words in the corpus

---

## 📐 Similarity Calculation

Movie similarity was computed using **Cosine Similarity**.

The cosine similarity score measures the angle between two movie vectors:

* Similarity = 1 → Identical movies
* Similarity = 0 → Completely unrelated movies

The final similarity matrix dimensions:

```text
4806 × 4806
```

---

## 🎯 Recommendation Algorithm

The recommendation process follows these steps:

1. Find the selected movie's index.
2. Retrieve similarity scores with all movies.
3. Sort the scores in descending order.
4. Exclude the movie itself.
5. Return the top 5 most similar movies.

---

## 📌 Example Recommendation

### Input

```text
Interstellar
```

### Output

```text
1. Silent Running
2. Guardians of the Galaxy
3. Space Cowboys
4. Apollo 13
5. A.I. Artificial Intelligence
```

---

## 🧪 Machine Learning Concepts Used

* Content-Based Filtering
* Feature Engineering
* Natural Language Processing
* Bag-of-Words
* Sparse Matrices
* Vector Space Representation
* Cosine Similarity
* Unsupervised Learning

---

## 📁 Project Structure

```text
movie-recommender/

├── data/
│   ├── tmdb_5000_movies.csv
│   └── tmdb_5000_credits.csv
│
├── notebooks/
│   └── movie_recommender.ipynb
│
├── models/
│   ├── movies.pkl
│   └── similarity.pkl
│
├── README.md
└── requirements.txt
```

---

## 🔮 Future Improvements

* Add movie posters using TMDB API
* Build a FastAPI backend
* Develop a Next.js frontend
* Deploy using Vercel and Render
* Add search autocomplete
* Compare CountVectorizer with TF-IDF
* Implement hybrid recommendation systems

