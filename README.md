# 🏏 Cricket Match Outcome Predictor (T20I)
---

## 📌 Overview

This project builds a machine learning model to predict the **outcome of T20 International cricket matches** based on pre-match and in-match features like team composition, venue, toss result, weather, and performance statistics. The model determines whether the **bat-first team will win** the match.

---

## 🧠 Key Features

- Predicts match outcome: **bat-first win or loss**
- Uses real-world **ball-by-ball data** (from 2003–2023)
- Handles team names, toss winner, runs, weather, and venue
- Clean and modular notebook for EDA, training, and evaluation
- Supports **custom user input predictions**
- Includes model serialization (`.joblib`) for reuse/deployment

---

## 📁 Dataset

- **Source**: [Kaggle – Ball by Ball IT20 Dataset](https://www.kaggle.com/datasets/jamiewelsh2/ball-by-ball-it20)
- **Period Covered**: 2003–2023
- **Preprocessing**:
  - Aggregated match-level features from ball-level records
  - Simulated `Weather` and `Time` columns (optional extensions)
  - Filtered out any players over 50 (none present in data)
  - Converted team/venue names into label-encoded format

---

## 📊 Features Used

| Feature           | Description                            |
|-------------------|----------------------------------------|
| `Venue`           | Encoded venue name                     |
| `Bat First`       | Encoded name of team batting first     |
| `Bat Second`      | Encoded name of second batting team    |
| `Toss Winner`     | Encoded team who won the toss          |
| `Team1 Runs`      | Total runs by team batting first       |
| `Team2 Runs`      | Total runs by chasing team             |
| `Target Score`    | Required target for 2nd innings        |
| `Weather`         | Simulated match condition              |
| `Time`            | Simulated Day/Night match              |

---

## ⚙️ Model

- **Type**: Gradient Boosted Trees (XGBoost)
- **Library**: `xgboost`
- **Target Variable**: `Bat_First_Won` (0 = loss, 1 = win)
- **Evaluation**:  
  ![image](https://github.com/user-attachments/assets/57acf72a-c566-4e55-8148-151f7911413f)


---

## 🧪 Files in This Repository

| File                              | Description                                      |
|----------------------------------|---------------------------------------------------|
| `data/processed_matches.csv`     | Cleaned and feature-engineered dataset            |
| `model/xgb_match_predictor.joblib` | Trained model for prediction                    |
| `notebooks/02_TrainModel.ipynb`  | Full notebook: EDA + training + evaluation        |
| `requirements.txt`               | All dependencies used in the project              |
| `README.md`                      | This file                                         |

---

## 🚀 How to Run

1. ✅ Install dependencies:
```bash
pip install -r requirements.txt
```
2. ✅ Run the Jupyter notebook:
```bash
jupyter notebook notebooks/02_TrainModel.ipynb
```
🔮 Future Improvements
Integrate live weather API for real-time predictions

Use player-wise form and synergy (via embeddings)

Build a web app using Streamlit or Flask

🧑‍💻 Author
Name: Your Full Name Here

Email: your@email.com

Submitted for: SMC Labs BD Summer’25 Internship Case Study
