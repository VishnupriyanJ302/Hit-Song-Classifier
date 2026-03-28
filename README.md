# Hit Song Classifier

A machine learning project that predicts whether a song will be a "Mega Hit" (≥2 billion streams) based on audio features and metadata from Spotify's all-time top 100 songs.

## 📊 Project Overview

This binary classification project uses audio features like danceability, energy, valence, and acousticness, along with genre and release year, to predict if a song will achieve mega-hit status on Spotify.

## 🎯 Problem Statement

**Objective:** Predict whether a song will be a Mega Hit (≥2 billion streams) or Regular Hit (<2 billion streams)

**Type:** Binary Classification

## 📁 Dataset

- **Source:** Spotify All-Time Top 100 Songs
- **Size:** 100 songs
- **Features Used:**
  - Audio Features: danceability, energy, valence, acousticness, BPM
  - Metadata: genre, release year, explicit content flag
  
**Target Distribution:**
- Mega Hits (≥2B streams): 63%
- Regular Hits (<2B streams): 37%

## 🛠️ Technologies Used

- **Python 3.x**
- **Libraries:**
  - pandas - Data manipulation
  - scikit-learn - Machine learning models
  - matplotlib & seaborn - Visualization

## 🔧 Project Workflow

1. **Data Exploration & Preprocessing**
   - Created binary target variable (is_mega_hit)
   - Handled categorical variables (genre grouping and one-hot encoding)
   - Converted explicit flag to numeric

2. **Feature Engineering**
   - Grouped 39 unique genres into 5 major categories: Pop, Rock, Hip-Hop, R&B/Soul, Others
   - Applied one-hot encoding to genre categories
   - Selected 11 final features

3. **Model Training**
   - Train-Test Split: 80-20 (80 training samples, 20 test samples)
   - Models trained:
     - Logistic Regression
     - Decision Tree Classifier
     - Random Forest Classifier

4. **Model Evaluation**
   - Metrics: Accuracy, Precision, Recall, F1-Score
   - Confusion Matrix visualization

## 📈 Results

| Model | Accuracy | Notes |
|-------|----------|-------|
| Logistic Regression | 60% | Biased toward predicting Mega Hits |
| Decision Tree | 60% | Balanced but missed half the Mega Hits |
| **Random Forest** | **65%** | **Best performer - most balanced** |

### Best Model: Random Forest Classifier

**Performance by Class:**
- **Regular Hits (Class 0):**
  - Precision: 55%
  - Recall: 75%
  - Correctly identified 6 out of 8 Regular Hits

- **Mega Hits (Class 1):**
  - Precision: 78%
  - Recall: 58%
  - Correctly identified 7 out of 12 Mega Hits

**Key Insight:** Random Forest provided the most balanced predictions across both classes, making it the most reliable model for this classification task.

## 🚀 How to Run

1. **Clone the repository:**
```bash
git clone [https://github.com/VishnupriyanJ302/Hit-Song-Classifier.git]
cd hit-song-classifier
```

2. **Install dependencies:**
```bash
pip install pandas scikit-learn matplotlib seaborn
```

3. **Run the notebook:**
```bash
jupyter notebook Main.ipynb
```

4. **Execute all cells** to see the complete pipeline from data loading to model evaluation.

## 📂 Project Structure
```
hit-song-classifier/
│
├── Main.ipynb                          # Main project notebook
├── spotify_alltime_top100_songs.csv    # Dataset
├── README.md                           # Project documentation
└── .gitignore                          # Git ignore file
```

## 🔮 Future Improvements

- **Feature Engineering:** Create interaction features (e.g., energy × danceability)
- **Hyperparameter Tuning:** Optimize Random Forest parameters using GridSearchCV
- **Feature Scaling:** Apply StandardScaler to improve Logistic Regression performance
- **Cross-Validation:** Use K-Fold CV for more robust evaluation
- **Additional Models:** Try SVM, XGBoost, Gradient Boosting
- **More Data:** Expand dataset beyond top 100 songs for better generalization

## 👨‍💻 Author

Vishnupriyan_J

## 📝 License

This project is open source and available for educational purposes.

## 🙏 Acknowledgments

- Dataset: Spotify Top 100 All-Time Most Streamed Songs
- Learning resource: Self-directed ML curriculum
