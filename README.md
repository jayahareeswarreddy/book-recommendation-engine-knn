# Book Recommendation Engine using KNN

Collaborative-filtering book recommender from the freeCodeCamp Machine Learning with Python curriculum. The original notebook filters the Book-Crossing ratings, builds a user-book matrix, and finds neighboring books with cosine-distance K-nearest neighbors.

## Problem and objective

Recommend books similar to a supplied title using other readers' ratings. The notebook retains users with at least 200 ratings and books with at least 100 ratings before building its rating matrix.

## Data

The notebook downloads the Book-Crossing data bundle from the freeCodeCamp project-data URL. The dataset is not included in this repository.

## Algorithm and implementation

The notebook uses pandas to filter and join ratings with book titles, SciPy's CSR sparse matrix representation, and scikit-learn NearestNeighbors with cosine distance. Its get_recommends(book) function returns the requested title and four recommended titles with distances.

## Results

Measured from the notebook's saved execution output. After filtering, the rating matrix covers 673 unique books and 888 unique users from 49,136 ratings. For `get_recommends("Where the Heart Is (Oprah's Book Club (Paperback))")`, the model returns:

| Recommended title | Cosine distance |
|---|---|
| I'll Be Seeing You | 0.802 |
| The Weight of Water | 0.771 |
| The Surgeon | 0.770 |
| I Know This Much Is True | 0.768 |

This matches the freeCodeCamp challenge's expected titles and distance tolerances — the notebook's own check prints **"You passed the challenge! 🎉🎉🎉🎉🎉"**.

## Run

Install the packages below, then open Book_Recommendation_Engine.ipynb in Jupyter. Run the notebook cells in order; its data-download cells use wget and unzip, which are available in Colab and many Linux notebook environments.

## Dependencies

See requirements.txt. The notebook was authored for a notebook environment; dependency versions have not been pinned.

## References

- freeCodeCamp Machine Learning with Python: https://www.freecodecamp.org/learn/machine-learning-with-python/
- Original project data: https://cdn.freecodecamp.org/project-data/books/book-crossings.zip

## Future improvements

Add a command-line or web interface, handle unknown titles with a clear message, and evaluate recommendation quality on held-out interactions.
