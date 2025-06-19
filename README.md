# **Fish Species Predictor - Deployed on Heroku** 

This project is a **machine learning-based fish species classification model**, trained on the **Fish Market dataset**. The model predicts the species of a fish based on its physical attributes. The entire application is deployed on **Heroku**, allowing users to make predictions via a web interface.

---

## Project Overview
- **Problem Statement**: Given fish measurement data (Weight, Length, Height, Width), predict the species of the fish.
- **Model Type**: **Classification** (Multi-class prediction of fish species).
- **Machine Learning Algorithm**: `RandomForestClassifier`
- **Frontend**: HTML + CSS + JavaScript
- **Backend**: Flask API (Python)
- **Deployment Platform**: Heroku  
- **Live App URL**: [Currently unavailable (link)](https://fish-predictor-2025-65a68cbab75e.herokuapp.com/)  
  *Note: The app is currently inactive as Heroku has discontinued its free tier. Please contact me if you'd like a live demo or deployment support.*
---

## Project Structure
```
 Fish Species Predictor
├── 📂 templates          # Frontend files (HTML, CSS)
│   ├── index.html       # User input form
├──  app.py            # Flask backend (loads model, serves predictions)
├──  requirements.txt   # Python dependencies
├──  Procfile          # Heroku process definition
├──  fish_species_classifier.pkl  # Trained model file
├──  scaler.pkl        # StandardScaler for input normalization
├──  label_encoder.pkl # Encodes fish species labels
└──  README.md         # Project documentation (this file)
```

---

## How It Works
### 1 Model Training
- The model was trained using the **Fish Market dataset** from [Kaggle](https://www.kaggle.com/aungpyaeap/fish-market).
- Features: `Weight`, `Length1`, `Length2`, `Length3`, `Height`, `Width`
- The data was **standardized** using `StandardScaler()`, and labels were **encoded** using `LabelEncoder()`.
- A `RandomForestClassifier` was trained and saved as `fish_species_classifier.pkl`.

### 2 Flask API
- The Flask app (`app.py`) loads the trained model and exposes a **REST API**.
- It receives input data from the **frontend form** and returns a **predicted fish species**.

### 3 Frontend (User Interface)
- Users enter **fish measurements** in a simple web form (`index.html`).
- The form sends data to the Flask backend, which returns a prediction.

### 4 Deployment on Heroku
- The app was containerized and deployed on **Heroku**.
- Used `gunicorn` as the WSGI server.
- `Procfile` specifies the entry point for Heroku:
  ```
  web: gunicorn app:app
  ```

---

## How to Run Locally
### 1 Clone the Repository
```bash
git clone https://github.com/Arsney091289421/Fish-classify-pred.git
cd Fish-classify-pred
```

### 2 Create a Virtual Environment
```bash
python -m venv venv
source venv/bin/activate  # On Windows, use `venv\Scripts\activate`
```

### 3 Install Dependencies
```bash
pip install -r requirements.txt
```

### 4 Run Flask App
```bash
python app.py
```
- Open `http://127.0.0.1:5000/` in your browser.

---

## Deployment on Heroku
### 1 Install Heroku CLI
```bash
brew tap heroku/brew && brew install heroku  # For macOS
```
or  
```bash
choco install heroku-cli  # For Windows
```

### 2 Deploy to Heroku
```bash
heroku login
heroku create fish-predictor-2025
git push heroku main
heroku open
```

---


