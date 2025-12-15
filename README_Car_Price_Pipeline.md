# Car Price Prediction using KNN Regressor

This project builds a **Car Price Prediction system** using **K-Nearest Neighbors Regression (KNN Regressor)**.  
The goal is to predict the **Ex-Showroom Price of cars** using both **numerical and categorical features**.

A complete **machine learning pipeline** is implemented to ensure **proper preprocessing, no data leakage, and reproducibility**.

---

## 📌 Dataset
- **Dataset:** Cars dataset (`cars.csv`)
- **Target Variable:** `Ex-Showroom_Price`
- **Selected Features:**
  - Make
  - Model
  - Variant
  - Displacement
  - Cylinders
  - Valves_Per_Cylinder
  - Drivetrain
  - Cylinder_Configuration
  - Emission_Norm

---

## 🛠️ Technologies Used
- Python
- Pandas
- Scikit-learn

---

## 🔄 Data Cleaning
The following cleaning steps were applied:
- Removed `Rs.` and commas from `Ex-Showroom_Price`
- Converted `Ex-Showroom_Price` to integer
- Removed `cc` from `Displacement` and converted it to float
- Selected only relevant columns to reduce noise

---

## 🧱 Why We Used Pipeline and ColumnTransformer

### 🔹 Why Pipeline?
A **Pipeline** is used to combine **preprocessing and model training** into a single workflow.

**Benefits:**
- Ensures same preprocessing for training and testing data
- Prevents data leakage
- Makes code clean and reusable
- Suitable for real-world deployment

---

### 🔹 Why ColumnTransformer?
The dataset contains **mixed data types**:
- Numerical features
- Categorical features

`ColumnTransformer` allows applying **different preprocessing steps** to different column types.

---

## 🔢 Numerical Feature Processing
- Missing values handled using **mean imputation**
- Features scaled using **StandardScaler**

Scaling is required because **KNN is distance-based**.

---

## 🔤 Categorical Feature Processing
- Missing values handled using **most frequent imputation**
- Converted to numeric using **OneHotEncoder**
- Unknown categories ignored safely during prediction

---

## ⚙️ Final Preprocessing Flow
```
Numerical Pipeline
        ↓
Categorical Pipeline
        ↓
ColumnTransformer
        ↓
KNN Regressor
```

---

## 🧠 Model Used
- **Algorithm:** K-Nearest Neighbors Regressor
- **n_neighbors:** 5

---

## 📊 Model Evaluation
- **Metric:** Mean Squared Error (MSE)

```
Mean Squared Error: 28287770074710.06
```

> Note: Large MSE is expected due to large car price values.

---

## 🚀 Conclusion
This project demonstrates a clean and professional ML workflow using:
- Pipelines
- ColumnTransformer
- Proper preprocessing for mixed data

---

## 📂 How to Run
1. Install dependencies:
   ```bash
   pip install pandas scikit-learn
   ```
2. Place `cars.csv` in the project directory
3. Run the Python script

---

## 👤 Author
**Zaid**  
BS Computer Science  
Aspiring Machine Learning Engineer
