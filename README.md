Movie Recommendation System 

 1. Data Loading

The MovieLens 1M Dataset was used to develop the movie recommendation system. The dataset contains three files: ratings.dat, users.dat, and movies.dat. The files were loaded into Pandas DataFrames containing user ratings, user information, movie titles, and movie genres.

 2. Data Inspection and EDA

The loaded data was examined using dataset shape, sample records, data types, statistical information, and missing-value checks. Exploratory Data Analysis was performed using rating distributions, ratings per user, ratings per movie, and the most-rated movies. This helped understand user rating behavior and movie popularity.

 3. Data Cleaning

The datasets were checked for missing values and duplicate records. Rating values were verified to ensure that they were within the valid 1–5 range. Invalid rating records were removed where necessary, and the cleaned data was used for further processing.

 4. Feature Engineering

The rating data was divided into training and testing data. Using the training data, movie-level features were created: Average Rating and Rating Count. Movie information was then combined with these features, and the original Genres information was retained for recommendation.

5. Vectorization

Since a movie can belong to multiple genres, the genre information was converted into numerical form using MultiLabelBinarizer. Each genre became a separate binary feature, allowing the system to compare movies based on their genre characteristics.

6. Scaling

The numerical features Average Rating and Rating Count were standardized using StandardScaler. This made the numerical features comparable and prevented the larger-valued Rating Count feature from dominating the similarity calculation.

7. Model Development and Training

A content-based recommendation system was developed using the engineered movie features. The numerical movie-feature matrix was created and Cosine Similarity was calculated between all movies. Movies with higher similarity scores are considered more similar and are selected as recommendations.

 8. Validation and Testing

An 80% training and 20% testing split was used. The training data was used to create the movie features, while the test data was kept for evaluation. Two baseline approaches—**Global Average Rating** and **Movie Average Rating—were evaluated using **MAE and RMSE.

 9. Experimentation and Comparison

The baseline approaches were compared using MAE and RMSE to understand their rating-prediction performance. The content-based recommendation system was also tested using different movie titles. The generated recommendations and similarity scores were inspected to verify that the system produced similar movies.

10. Model Saving

The completed recommendation components were saved using Joblib as:
movie_recommendation_
