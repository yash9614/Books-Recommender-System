# Books Recommender System

A Book Recommendation System built using **Item-Based Collaborative Filtering** with `NearestNeighbors` (cosine similarity) and served via a **Streamlit** web application. Fully containerized with Docker.

---

## Project Pipeline

```mermaid
flowchart TD
    A[Raw Dataset<br/>BX-Books, BX-Users, BX-Book-Ratings] --> B[Data Loading & Cleaning]
    B --> C[Filter Active Users<br/>≥ 200 ratings]
    C --> D[Filter Popular Books<br/>≥ 50 ratings]
    D --> E[Merge Ratings + Books]
    E --> F[Create Pivot Table<br/>Books × Users]
    F --> G[Train NearestNeighbors Model<br/>Cosine Similarity]
    G --> H[Save Artifacts<br/>model.pkl + book_pivot + etc.]
    H --> I[Streamlit Web App]
    I --> J[Docker Container]
    
    style A fill:#e1f5fe
    style G fill:#fff3e0
    style I fill:#e8f5e9
    style J fill:#f3e5f5



# How the Recommendation Works
flowchart LR
    A[User selects a book] --> B[Find book vector<br/>in pivot table]
    B --> C[NearestNeighbors<br/>finds similar books]
    C --> D[Return Top 5<br/>similar books + posters]
    
    style C fill:#fff3e0

# Features

Item-based Collaborative Filtering
Cosine similarity with brute-force NearestNeighbors
Clean Streamlit interface with book cover images
Fully containerized with Docker
Ready for deployment

# Tech Stack
Python 3.11
scikit-learn (NearestNeighbors)
Streamlit
Pandas & NumPy
Docker

# Project Structure
├── artifacts/           # Trained model + pickled files
├── data/                # Raw Book-Crossing dataset
├── notebooks/           # Model training notebook
├── app.py               # Streamlit application
├── Dockerfile
├── requirements.txt
└── README.md


Run Locally
# Create virtual environment
uv venv
.venv\Scripts\activate

# Install dependencies
uv pip install -r requirements.txt

# Run the app
streamlit run app.py

# docker build -t books-recommender .
docker run -p 8501:8501 books-recommender

Then open: http://localhost:8501

Dataset Book Recommendation Dataset (Book-Crossing)


# Author
Yash Paprikar



