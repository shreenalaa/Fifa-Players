⚽ FIFA Player Wage Prediction

This project predicts FIFA player wages using machine learning techniques. We explore numerical and categorical data, handle outliers, perform feature engineering, and test both linear and polynomial regression models.

📝 Dataset

Source: FIFA players dataset (fifa_players.csv)

Rows: 19,178 players

Columns: 29 features including:

wage_eur 💰 (target variable)

Player stats: overall, potential, skill_dribbling, attacking_finishing, movement_reactions, etc.

Personal info: age, height_cm, weight_kg, nationality_name 🌎

🔧 Data Preprocessing

Handle Missing Values ❌

Dropped rows with null values

Removed records where wage_eur is zero

Normalize Object Columns ✨

Converted all string columns to lowercase

Replaced spaces with underscores _

Handle Outliers 📊

Limited wage_eur to below €100,000

Clipped other features like overall, potential, attacking_crossing, skill_long_passing to reduce extreme values

Feature Reduction 🗑️

Dropped irrelevant or highly correlated features to avoid overfitting:

movement_reactions, goalkeeping_*, movement_*, age, defending_*, height_cm, weight_kg

Categorical Encoding 🔤

Encoded nationality_name (163 unique values) for modeling

📊 Exploratory Data Analysis (EDA)

Correlation Heatmaps 🖌️

Showed strong relationships between wage_eur and features like overall, potential, and movement_reactions

High correlation between overall and movement_reactions → dropped movement_reactions

Distribution Plots 📈

wage_eur distribution before and after clipping

Feature distributions to understand player performance spread

Bar & Scatter Plots 🔍

Examined the relationship between wages and features like overall, attacking_crossing, skill_long_passing

🤖 Modeling
1️⃣ Linear Regression

Features: Selected numerical attributes (overall, potential, attacking & skill stats)

Results:

Train R²: ~0.395

Test R²: ~0.384

Observations: Low variance but high bias → model underfits the data

2️⃣ Polynomial Regression (Degree = 2)

Features: Expanded all numerical features to polynomial combinations

Results:

Train R²: ~0.696

Test R²: ~0.675

Observations: Better performance but slight overfitting (train-test difference ~20%)

🔑 Highlights

✅ Data Cleaning: Removed nulls and extreme outliers to improve model accuracy

✅ Feature Engineering: Selected key features, dropped less relevant ones to reduce noise

✅ EDA: Visualizations to understand relationships between stats and wages

✅ Modeling: Tried both linear and polynomial regression

✅ Polynomial Features: Captures non-linear relationships between player stats and wages

📌 Insights

Player overall rating and potential strongly influence wages

Attacking skills like crossing, finishing, and volleys correlate with higher wages

Linear regression captures basic trends, but polynomial regression improves predictions for top players

🚀 Next Steps

Explore regularization (Ridge, Lasso) to reduce overfitting in polynomial regression

Encode nationality_name more effectively (one-hot vs embedding)

Add more player features (position, club, league) to improve accuracy

Deploy the model in a web app to predict FIFA player wages dynamically

📦 Libraries Used

numpy 🔢

pandas 🐼

matplotlib & seaborn 📊

scikit-learn 🤖
