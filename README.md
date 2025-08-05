# 🎓 Student Performance Prediction

This is a complete **End-to-End Machine Learning Project** that predicts students' math scores based on demographic and test preparation data. It includes data ingestion, preprocessing, model selection, training, evaluation, and a deployed Flask web application for predictions.

---

## 🧠 Problem Statement

Educational institutions often want to predict students' performance to provide early support. This project predicts the **math score** of students based on:

- Gender
- Race/Ethnicity
- Parental Level of Education
- Lunch Type
- Test Preparation Course
- Reading Score
- Writing Score

---

## 📊 Tech Stack

- **Programming Language**: Python 3.10+
- **ML Libraries**: scikit-learn, pandas, numpy, xgboost, catboost
- **Model Selection**: GridSearchCV & R² Score
- **Deployment**: Flask (Web Framework)
- **Utilities**: dill (for object serialization), custom logging, exception handling

---

## 🧱 Project Architecture

mlproject/
│
├── notebook/ # Dataset and exploratory notebooks
├── src/
│ ├── components/ # Core components: ingestion, transformation, training
│ ├── pipeline/ # Prediction pipeline for Flask
│ ├── exception.py # Custom exception class
│ ├── logger.py # Logging functionality
│ └── utils.py # Helper functions: save/load models, evaluation
│
├── artifacts/ # Contains saved model and preprocessor
├── templates/ # HTML templates for the frontend
├── app.py # Flask application script
├── requirements.txt # Python dependencies
└── README.md

yaml
Copy
Edit

---

## 🏗️ Workflow

### 🔹 1. Data Ingestion
- Reads CSV dataset (`stud.csv`)
- Splits into training and test sets
- Stores them in the `artifacts/` folder

### 🔹 2. Data Transformation
- Converts categorical columns to numerical using encoders
- Scales numerical columns
- Saves the preprocessor object to `artifacts/preprocessor.pkl`

### 🔹 3. Model Training
- Uses several regressors (Linear, Ridge, Lasso, Decision Tree, Random Forest, XGBoost, etc.)
- Evaluates using R² Score on test data
- Selects best performing model
- Saves the best model to `artifacts/model.pkl`

### 🔹 4. Prediction Pipeline
- Loads saved preprocessor and model
- Takes user input from the frontend
- Transforms it and returns predicted math score

---

## 💻 Flask Web App

### Run Locally:

python app.py
Then visit: http://127.0.0.1:5000

You’ll see:

Home page

Prediction form

Predicted math score on submit

📈 Models Compared
Linear Regression

Ridge & Lasso

Decision Tree

Random Forest

K-Nearest Neighbors

XGBoost

CatBoost

AdaBoost

The model with the highest R² score is saved and used for predictions.

🧪 Evaluation Metric
R² Score

Mean Absolute Error (MAE)

Mean Squared Error (MSE)

⚙️ Installation Guide
Clone the Repository

Copy
Edit
git clone https://github.com/<your-username>/mlproject.git
cd mlproject
Create and Activate Virtual Environment (optional)



python -m venv venv
venv\Scripts\activate      # Windows
source venv/bin/activate   # Linux/Mac
Install Dependencies

pip install -r requirements.txt
Run the Flask App

python app.py
📂 Dataset
The dataset is stored at:


notebook/data/stud.csv
It contains columns like:

gender

race/ethnicity

parental level of education

lunch

test preparation course

reading score

writing score

math score (target)

🧰 Key Files
File/Folder	Purpose
app.py	Flask app entry point
src/components/	Data handling, transformation, model training
src/pipeline/	Handles prediction logic
src/utils.py	Save/load models and preprocessing objects
src/logger.py	Logging configuration
src/exception.py	Custom error messages
templates/	HTML templates for the web app
artifacts/	Saved model and preprocessor objects

🧠 What I Learned
Designing ML pipeline in a modular way

Model comparison & hyperparameter tuning

Creating a custom exception + logging system

Serializing models and scalers using dill

Deploying with Flask

🌟 Future Improvements
Deploy on cloud (Heroku, AWS, etc.)

Use Streamlit instead of Flask

Add more features to dataset

Create CI/CD pipeline

🙋‍♂️ Author
Tanmay Goraksha
📍 Mumbai, India
