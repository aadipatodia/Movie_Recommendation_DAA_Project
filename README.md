# Graph-Based Movie Recommendation System

A Python implementation of a movie recommendation system using a custom graph data structure and the Breadth-First Search (BFS) algorithm. This project identifies users with similar tastes by analyzing their movie ratings and suggests movies they might enjoy.

---

## 🎬 Features

-   **Graph-Based Model**: Represents users and movies as nodes in a network, built from scratch using Python dictionaries.
-   **BFS for Neighbor Discovery**: Efficiently finds "nearby" users in the graph who have rated common movies.
-   **Jaccard Similarity Scoring**: Calculates a similarity score between users based on their viewing history to find the best matches.
-   **Rating Visualization**: Generates bar plots to show the rating distribution for any recommended movie, justifying why it's a good suggestion.
-   **Minimal Dependencies**: Built without specialized graph libraries like `NetworkX` to demonstrate the underlying data structures and algorithms.

---

## ⚙️ How It Works

The recommendation logic follows a four-step process:

1.  **Graph Construction**: An adjacency list (implemented as a Python dictionary) is created where users and movies are nodes. An edge connects a user and a movie if the user has rated that movie.
2.  **Neighbor Search (BFS)**: Starting from a target user, a Breadth-First Search is performed to find a set of nearby, potentially similar users.
3.  **Similarity Calculation**: The **Jaccard similarity** is calculated between the target user and each user found by the BFS. This measures the overlap in their movie tastes.
4.  **Recommendation Aggregation**: The system aggregates movies that are highly rated (4+ stars) by the most similar users. It filters out movies the target user has already seen and ranks the results to produce the final list.



---

## 💾 Dataset

This project uses the classic **MovieLens 100k Dataset**. It contains 100,000 ratings from 943 users on 1,682 movies. The script automatically downloads and unzips this dataset on its first run.

---

## 🛠️ Technology Stack

-   **Language**: Python 3
-   **Data Manipulation**: Pandas
-   **Data Visualization**: Matplotlib & Seaborn
-   **Environment**: Google Colab (or any environment with Jupyter Notebook support)

---

## 🚀 How to Run

This project is designed to be run in a Google Colab notebook.

1.  **Open Google Colab**: Navigate to [colab.research.google.com](https://colab.research.google.com).
2.  **Upload Notebook**: Click on `File` -> `Upload notebook...` and select the `.ipynb` file for this project.
3.  **Run All Cells**: In the top menu, click on `Runtime` -> `Run all`.
4.  **View Results**: The notebook will execute each cell sequentially. The first run will download the dataset. The final cells will output the top 10 movie recommendations for the default user and a bar chart showing the rating distribution for the top-recommended movie.

```python
# You can change the target user ID in this cell
TARGET_USER_ID = 196
```

# 📄 Code Overview

The core logic is contained within two main functions:

### 🔹 `get_recommendations()`
The main engine that takes a **User ID** and returns a **ranked list of movie recommendations**.  
It handles:
- BFS traversal  
- Similarity scoring  
- Result aggregation  

### 🔹 `plot_rating_distribution()`
A utility function that takes a **movie title** and generates a **bar chart** of its ratings,  
providing a **visual justification** for a recommendation.

---

# ✨ Example Output

### 🧠 Text Recommendations
Generating recommendations for User ID: 196...
Top 10 Movie Recommendations:
 1. Star Wars (1977) (Score: 10.51)
 2. The Godfather (1972) (Score: 8.45)
 3. Raiders of the Lost Ark (1981) (Score: 7.99)


### 📊 Visual Output
The script will also display a **bar chart** for the top recommended movie (e.g., **"Star Wars"**).
