# Books Recommender System

A Book Recommendation System built using **Item-Based Collaborative Filtering** with `NearestNeighbors` (cosine similarity) and deployed using **Streamlit**.

## Features

- Recommends similar books based on user rating patterns
- Clean Streamlit interface with book cover images
- Fully containerized with Docker

## Tech Stack

- Python
- scikit-learn (NearestNeighbors)
- Streamlit
- Docker
- Pandas & NumPy

## How it works

1. Filters active users and popular books from the Book-Crossing dataset
2. Creates a user-item rating matrix (pivot table)
3. Trains a NearestNeighbors model using cosine similarity
4. Serves recommendations through a Streamlit web app

## Run Locally

```bash
# Create virtual environment
uv venv
.venv\Scripts\activate          # Windows

# Install dependencies
uv pip install -r requirements.txt

# Run the app
streamlit run app.py


# Run with Docker
docker build -t books-recommender .
docker run -p 8501:8501 books-recommender

Then open: http://localhost:8501

# Author
Yash Paprikar

