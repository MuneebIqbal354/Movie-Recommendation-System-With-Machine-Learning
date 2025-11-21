# Movie Recommendation System Using Machine Learning

**Project Overview**

In an era of information overload, decision fatigue is a significant challenge. This project implements a Machine Learning-based **Movie Recommender System** designed to curate personalized content for users. 

By leveraging predictive modeling and heuristics, the system filters through thousands of options to suggest movies that align with a user's specific tastes and viewing history, effectively minimizing search time and maximizing entertainment value. This is a web-based application built using **Streamlit**, capable of analyzing user interests to generate real-time movie suggestions.

---

## Recommendation Paradigms

Understanding the logic behind recommendation engines is crucial. This project explores the three primary methodologies:



[Image of collaborative vs content-based filtering diagram]


### 1. Content Based Filtering
This method relies on the intrinsic attributes of the items (movies) and the user's profile.

* **Mechanism:** Creates feature vectors (embeddings) based on attributes like genre, director, cast, or keywords.
* **Logic:** *"If you liked Movie A (Action/Sci-Fi), you will likely enjoy Movie B (Action/Sci-Fi)."*
* **Pros:** Highly personalized; does not require data from other users.
* **Cons:** **Over-specialization** (The "Filter Bubble"). The system may fail to recommend diverse content outside the user's established preferences.

### 2. Collaborative Filtering
This method relies on user-item interactions and community data rather than item attributes.

* **Mechanism:** Identifies clusters of users with similar rating patterns using mathematical matrices (User-Item Matrix).
* **Logic:** *"User A and User B have similar tastes. User A liked Movie Z, so User B will probably like it too."*
* **Pros:** Capable of recommending entirely new categories of content (Serendipity).
* **Cons:**
    * *Computational Cost:* Processing large $N \times N$ matrices is resource-intensive.
    * *The Cold Start Problem:* Cannot recommend new items that have no ratings yet.
    * *Popularity Bias:* Tends to favor widely known blockbusters.

### 3. Hybrid Systems
* **Mechanism:** Combines Content-Based and Collaborative approaches to mitigate the limitations of each.
* **Tech Stack:** Often utilizes advanced techniques like `word2vec` and deep learning embeddings.

---

## Technical Concept: Cosine Similarity

The core mathematical concept driving the similarity engine in this project is **Cosine Similarity**.

1.  **Vectorization:** Textual data (movie tags, overview, cast) is converted into numerical vectors (NumPy arrays).
2.  **Measurement:** We measure the cosine of the angle between two non-zero vectors in a multi-dimensional space.
3.  **Interpretation:**

> * **Value = 1 ($0^\circ$):** The vectors point in the same direction (Perfect Similarity).
> * **Value = 0 ($90^\circ$):** The vectors are orthogonal (No Similarity).
> * **Value = -1 ($180^\circ$):** The vectors are diametrically opposed.

---

## 📊 Dataset & Demo

**Source:** The model is trained on the [TMDB 5000 Movie Dataset](https://www.kaggle.com/tmdb/tmdb-movie-metadata?select=tmdb_5000_movies.csv).

### Application Screenshots




## Installation Guide

Follow these steps to set up the project locally.

### 1. Clone the Repository
```bash
git clone 
cd Movie-Recommender-System-Using-Machine-Learning
```

### 2. Environment Setup

It is recommended to use a virtual environment to manage dependencies.

```bash
conda create -n movie python=3.7.10 -y
conda activate movie
```


### 3. Install Dependencies
```bash
pip install -r requirements.txt
```

4. Generate Models

Run the Jupyter Notebook to process the data and generate the `model.pkl` file.

```bash
#run this file to generate the models
Movie Recommender System Data Analysis.ipynb
```

5. Launch Application

Start the Streamlit server:
```bash
streamlit run app.py
```
