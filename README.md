# Netflix-Data-Analysis-with-Machine-Learning

## Abstract
This project analyzes the Netflix dataset to uncover viewer preferences and improve recommendation algorithms. The process includes data cleaning, exploratory data analysis (EDA), and the application of machine learning models such as K-Nearest Neighbors (KNN), Gaussian Naive Bayes (GNB), and XGBoost. The project also implements a recommendation system using TF-IDF vectorization and cosine similarity, comparing it with sklearn-based models for evaluation.

## Dataset Overview
The Netflix Titles dataset contains information on 8809 entries, each representing a movie or TV show, with attributes like:
1. **show_id**: Unique identifier for each title.
2. **type**: Genre of the title ('Movie' or 'TV Show').
3. **title**: Name of the title.
4. **director**: Director(s) of the title.
5. **cast**: Main actors/actresses in the title.
6. **country**: Production country.
7. **date_added**: Date added to Netflix.
8. **release_year**: Year of release.
9. **rating**: Age classification.
10. **duration**: Length in minutes or number of seasons.
11. **listed_in**: Genres of the title.
12. **description**: Brief summary of the title.

## Methodology
### 1. Data Preprocessing
- Handled missing values by filling with appropriate defaults (e.g., 'Unknown' for `director`, `cast`, and `country`).
- Converted `type` to binary format.
- Transformed categorical fields like ratings into integer codes.
- Extracted `year_added` from the `date_added` column.
- Created new features: `num_cast` (count of cast members) and `num_genres` (count of genres).
- Dropped irrelevant columns after feature extraction.

### 2. Exploratory Data Analysis (EDA)
- Visualized missing values using heatmaps.
- Analyzed content distribution by type, release year, and region.
- Generated word clouds to identify frequent themes in titles.

### 3. Machine Learning Models
#### a) K-Nearest Neighbors (KNN)
- Used features like `year_added`, `release_year`, `duration`, and `rating`.
- Achieved high accuracy and F1-score.

#### b) Gaussian Naive Bayes (GNB)
- A simple and fast classifier.
- Achieved high recall but lower precision compared to KNN.

#### c) XGBoost
- A powerful ensemble technique for classification.
- Achieved high recall but required careful tuning to avoid overfitting.

### 4. Recommendation System
- Implemented TF-IDF vectorization to measure word importance in movie descriptions.
- Calculated cosine similarity to identify similar movies.
- Generated recommendations based on similarity scores.

## Evaluation Metrics
1. **Accuracy**: Overall correctness of the model.
2. **Precision**: Accuracy of positive predictions.
3. **Recall**: Ability to detect all actual positives.
4. **F1-Score**: Harmonic mean of precision and recall.

## Results and Trade-offs
### KNN
- High accuracy and F1-score.
- Computationally expensive for large datasets.

### GNB
- High recall, suitable for identifying positives.
- Sacrifices precision for recall.

### XGBoost
- High recall, useful for critical identification tasks.
- Complex to tune but flexible and effective.

## Conclusion
Each model serves different use cases:
- **KNN**: Best for balanced precision and recall.
- **GNB**: Suitable when high recall is critical.
- **XGBoost**: Ideal for scenarios requiring flexibility and high recall.

The recommendation system enhances personalization by providing similar content suggestions based on user preferences.
