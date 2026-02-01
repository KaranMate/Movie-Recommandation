1️⃣ Data Collection

Used a movie dataset containing title, genres, and overview

Removed duplicates, null values, and irrelevant columns

Prepared clean textual data for feature extraction

2️⃣ Text Processing & Feature Engineering

Combined important text features (overview + genres)

Applied TF-IDF Vectorization to convert text into numerical vectors

This helps measure similarity between movies based on content

3️⃣ Similarity Calculation

Used Cosine Similarity to calculate similarity scores between movies

Higher similarity score = more related movies

Stored similarity-ready matrices for fast retrieval

4️⃣ Model Optimization & Pickle Files

Saved processed objects using Pickle:

df.pkl → cleaned movie data

tfidf.pkl → TF-IDF vectorizer

tfidf_matrix.pkl → feature matrix

indices.pkl → movie title to index mapping

Improves performance and avoids recomputation

5️⃣ Streamlit Web Application

Built an interactive UI using Streamlit

Features:

Movie search dropdown

Multi-genre filtering

Adjustable number of recommendations

Similarity score display

Fast loading using caching

6️⃣ Recommendation Process

User selects a movie

System finds similar movies using cosine similarity

Optional genre filters applied

Top recommended movies displayed with details

7️⃣ Technologies Used

Python

Pandas, Scikit-learn

TF-IDF Vectorizer

Cosine Similarity

Streamlit

Pickle

8️⃣ Project Outcome

Successfully built a content-based movie recommendation system

Efficient, scalable, and user-friendly

Can be extended with posters, ratings, or hybrid recommendations

📌 Project Architecture Diagram
flowchart TD
    A[User] -->|Search Movie / Select Genres| B[Streamlit Web App]

    B --> C[Pickle Files Loader]

    C --> D[df.pkl<br/>Cleaned Movie Data]
    C --> E[tfidf_matrix.pkl<br/>TF-IDF Feature Matrix]
    C --> F[indices.pkl<br/>Movie Index Mapping]

    B --> G[Recommendation Engine]

    G --> H[Cosine Similarity<br/>Computation]
    H --> I[Top-N Similar Movies]

    I --> J[Genre Filtering Logic]
    J --> K[Final Recommendations]

    K -->|Titles, Genres,<br/>Similarity Score| B
    B -->|Display Results| A
