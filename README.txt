Vehicle Silhouettes Classification — Turing Institute Dataset

Overview

This project classifies vehicle types based on silhouette features. Given a set of geometric measurements extracted from vehicle silhouettes, the goal is to predict whether the vehicle is a bus, van, saab, or opel.

This was my first machine learning project, done in my second year of university. I wrote this README later, after finishing my second project. I didn't touch the code — I wanted to leave it as it was when I first wrote it, to show how much my work has changed since then.
---------------------------------------

Dataset

The dataset is from the Turing Institute in Glasgow, Scotland. It has 18 geometric features extracted from vehicle silhouettes across four classes: bus, van, saab, and opel.

The data comes in 9 separate `.dat` files (`xaa.dat` to `xai.dat`). The code merges them automatically. To run it locally, just keep all the files inside the folder called `data/`, just like you downloaded it from the repository
---------------------------------------

What I Did

1. Loading the Data

Loaded and merged all 9 `.dat` files into one DataFrame and assigned column names manually.

2. Exploratory Data Analysis

. Checked for missing values and duplicates
. Used Z-scores to detect outliers
. Plotted histograms for selected features
. Made scatter plots to see how well the classes separate visually
. Generated a correlation heatmap

3. Encoding

Used LabelEncoder to convert the target column from class names to numbers.

4. Splitting and Scaling

. 80/20 train/test split with stratification to keep class balance
. Applied StandardScaler on the training set and used it to transform the test set
. Scaling was only used for Logistic Regression, KNN, and SVM — Decision Tree and Random Forest don't need it

5. Training and Tuning

Trained five models and tuned each one with GridSearchCV. The best parameters were then applied directly to the final models:

- Logistic Regression
- KNN
- SVM
- Decision Tree
- Random Forest
---------------------------------------

Results

Model			Test Accuracy 
SVM 			86%
Logistic Regression 	84%
Random Forest 		75%
KNN			72%
Decision Tree   	72%

SVM came out on top, with Logistic Regression right behind it. The hardest part for every model was telling saab and opel apart — they kept getting confused with each other. Bus and van were easy across the board, consistently hitting above 90% precision and recall.
---------------------------------------

Visualizations

. Histograms for selected features
. Scatter plots colored by class
. Correlation heatmap
. Bar chart comparing all five models after tuning
---------------------------------------