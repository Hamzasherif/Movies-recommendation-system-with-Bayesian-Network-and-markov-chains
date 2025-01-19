
# Movie Recommendation System

This project is a Python-based movie recommendation system leveraging **Bayesian Networks** and **Markov Models** to predict user preferences and suggest movies. The system integrates data from multiple sources and preprocesses it to create a pipeline for analysis and recommendations.

## Features
- **Data Integration**: Merges data from multiple CSV files (movies, links, ratings, and tags).
- **Bayesian Network**: Models relationships between features like genres, tags, user IDs, and ratings.
- **Markov Model**: Builds a genre sequence model for predicting user preferences based on past behavior.
- **Recommendation Generation**: Provides personalized movie recommendations based on user history and model inference.
- **Visualization**: Displays the Bayesian Network structure using NetworkX.

## Datasets
The project uses the following datasets:
- `movies.csv`: Contains movie details, including genres.
- `links.csv`: Links movies to external databases.
- `ratings.csv`: User ratings for movies.
- `tags.csv`: User-assigned tags for movies.

## Installation
1. Clone the repository:
   ```bash
   git clone https://github.com/your-username/movie-recommendation-system.git
   cd movie-recommendation-system
   ```
2. Install the required Python libraries:
   ```bash
   pip install -r requirements.txt
   ```

## Usage
1. **Preprocess Data**: Load and merge datasets to create a unified data structure.
2. **Build Models**:
   - Fit a Bayesian Network for rating predictions.
   - Construct a Markov Model for sequential genre analysis.
3. **Generate Recommendations**:
   - Use Bayesian inference to predict ratings for unseen movies.
   - Employ the Markov Model to recommend genres/movies based on user history.
4. **Visualize**:
   - Plot the Bayesian Network structure to understand the relationships.

### Example Code
Below is a snippet demonstrating how to generate recommendations:

```python
# Predict ratings for unseen movies
query_result = infer.map_query(variables=['rating'], evidence={'userId': 62, 'genres': 114, 'tag': 110})
print(query_result)

# Generate recommendations using Markov Model
recommendations = generate_movie_recommendation(markov_model, current_genre)
for movie_id in recommendations:
    print(f"Recommended Movie ID: {movie_id}")
```

## Visualization
The Bayesian Network is visualized as a directed graph:

![Bayesian Network](path-to-network-image.png)

## Dependencies
- Python 3.x
- pandas
- pgmpy
- sklearn
- networkx
- matplotlib

## Contributing
Contributions are welcome! Feel free to open an issue or submit a pull request.


## Acknowledgments
- [pgmpy](https://pgmpy.org): Python library for probabilistic graphical models.
- [MovieLens Datasets](https://grouplens.org/datasets/movielens/): Source of movie data.

---
