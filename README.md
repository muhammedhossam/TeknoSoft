# Movie Recommendation System

This code builds a movie recommendation system using a dataset of movies and their associated information. Here's a step-by-step breakdown of the code:

1. Import the necessary libraries: `pandas`, `numpy`, `matplotlib.pyplot`, `seaborn`, and `ast`.

2. Read the movie dataset (`tmdb_5000_movies.csv`) and the credits dataset (`tmdb_5000_credits.csv`) using the `pd.read_csv()` function.

3. Perform an initial exploration of the data by printing the first few rows of the movies dataset and accessing the 'keywords' column of the second row.

4. Merge the movies and credits datasets on the 'title' column using the `merge()` function and assign the result to a new DataFrame called `df`.

5. Drop the 'movie_id' column from the `df` DataFrame using the `drop()` function.

6. Perform feature selection by selecting specific columns from the `df` DataFrame and creating a new DataFrame called `df_fet`.

7. Clean the data by dropping duplicates and removing rows with missing values using the `drop_duplicates()` and `dropna()` functions, respectively.

8. Convert the string representation of certain columns ('genres', 'keywords', 'cast', 'crew') to lists using the `convert_to_list()` function.

9. Further process the data by removing spaces from the 'cast', 'crew', 'genres', 'keywords', and 'overview' columns using the `remove_space()` function.

10. Create a new column called 'all', which combines the 'overview', 'genres', 'keywords', 'cast', and 'crew' columns.

11. Drop unnecessary columns from the `df_fet` DataFrame and assign the result to a new DataFrame called `new_df`.

12. Convert the lists in the 'all' column to strings using the `join()` function.

13. Preprocess the text data by converting it to lowercase and removing punctuation, stop words, and lemmatizing the words using the `bag_of_words()` function.

14. Create a bag-of-words representation of the preprocessed text data using the `CountVectorizer` class from `sklearn.feature_extraction.text`.

15. Calculate the cosine similarity between the bag-of-words vectors using the `cosine_similarity()` function.

16. Define a function called `recommend()` that takes a movie title as input and recommends similar movies based on cosine similarity scores.

17. Save the `new_df` DataFrame and the similarity matrix as pickle files for future use.

This code provides a basic movie recommendation system that suggests similar movies based on textual information such as movie overview, genres, keywords, cast, and crew.
