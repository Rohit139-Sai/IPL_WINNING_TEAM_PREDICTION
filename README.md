# 🏏 IPL Winning Team Prediction using Machine Learning

This project was developed as part of **SystemTron ML Internship – Week 3 Task**.

It focuses on predicting the **winner of an IPL match** using a machine learning classification model, based on features such as:

* Team 1
* Team 2
* Toss winner
* Venue
* City
* Season

The goal is to build a model that can **predict the winning team** accurately based on these match-level inputs.

---

## ⚙️ Tech Stack

This project uses the following tools and technologies:

* **Python** – Programming language
* **Pandas** – Data handling
* **NumPy** – Numerical processing
* **Matplotlib & Seaborn** – Exploratory Data Analysis
* **Scikit-learn** – ML training & evaluation
* **Pickle** – Saving and loading trained models
* **Google Colab** – Development environment

---

## 📁 Dataset Overview

The dataset contains **historical IPL match data** from 2008 to 2019.

### 📌 Columns Used:

| Column        | Description                          |
| ------------- | ------------------------------------ |
| `team1`       | First team in the match              |
| `team2`       | Second team in the match             |
| `toss_winner` | Team that won the toss               |
| `venue`       | Venue of the match                   |
| `city`        | City where the match was played      |
| `season`      | Year of the match                    |
| `winner`      | ✅ Target: Actual winner of the match |

### 🔴 Dropped Columns:

* `umpire1`, `umpire2`, `umpire3` – Not relevant
* `result`, `dl_applied`, `id` – Not needed for prediction

---

## 🔍 Steps Followed in the Project

### 📥 1. Imported Required Libraries

Libraries such as pandas, numpy, matplotlib, seaborn, scikit-learn, and pickle were used for data analysis, visualization, model building, and saving.

### 📂 2. Loaded the Dataset

The IPL match dataset (`matches.csv`) was loaded using pandas and cleaned using `.drop()` and `.dropna()` to remove unused columns and missing values.

### 🧹 3. Cleaned the Dataset

* Removed null rows
* Standardized team names (e.g., "Delhi Daredevils" → "Delhi Capitals")
* Limited data from 2008 to 2019 for model consistency

### 📊 4. Exploratory Data Analysis (EDA)

Used bar graphs and seaborn countplots to visualize:

* Total matches per season
* Wins per team

### 🔁 5. Feature Selection

Selected relevant features: `team1`, `team2`, `toss_winner`, `venue`, `city`, `season` for the input (X) and `winner` for the output (y).

### 🔠 6. Encoded Categorical Features

Used `OneHotEncoder` inside `ColumnTransformer` to convert categorical columns to numeric, and `handle_unknown='ignore'` to prevent future input mismatch.

### 🧪 7. Train-Test Split

Split the dataset into 80% training and 20% testing using `train_test_split()`.

### 🤖 8. Trained the Model

Trained a `RandomForestClassifier` on the training data to predict the winning team.

### 📈 9. Evaluated the Model

Evaluated the model using:

* Accuracy Score
* Confusion Matrix
* Classification Report

### 🔮 9.1 Predicted Past Champions

Grouped matches by season and winner to extract the **most successful team each year** from 2008–2019.

---

## 💾 10. Saved the Model

Saved the trained model (`ipl_model.pkl`) and the transformer (`transform.pkl`) using Pickle.

```python
pickle.dump(model, open('ipl_model.pkl', 'wb'))
pickle.dump(ct, open('transform.pkl', 'wb'))
```

---

## 🧪 Sample Prediction

A sample 2025 final prediction:

```python
team1 = 'Royal Challengers Bangalore'
team2 = 'Punjab Kings'
toss_winner = 'Punjab Kings'
venue = 'Narendra Modi Stadium'
city = 'Ahmedabad'
season = 2025
```

**🏆 Predicted Winner:** Royal Challengers Bangalore

---

## 👤 Author

**Dasari Sai Ram**
B.Tech in Civil Engineering
SRKR Engineering College
SystemTron ML Intern – Week 3 Task

🔗 [www.systemtron.in](http://www.systemtron.in)

---

## 📌 Acknowledgement

This project was created as a part of the **SystemTron Machine Learning Internship – Week 3 assignment**.
It helped me explore classification problems and use real-world sports data for predictive analytics.

---

## 📄 License

This project is open-source and intended for learning and demonstration purposes only.

---

Would you like me to generate this as a `.md` file you can upload to GitHub or share directly?
