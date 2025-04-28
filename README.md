## Overview
This project builds a predictive model to estimate Blood Alcohol Content (BAC) using the **Widmark Formula**. 
It combines user demographic information and drinking behavior to predict estimated BAC levels and classify intoxication stages.

Using real-world survey data (NHANES), we apply machine learning (XGBoost) to refine BAC estimations based on features like:
- Sex
- Age
- Weight
- Average number of drinks per day
- Drinking frequency

---

## How It Works
1. **Data Preparation**:
   - Load cleaned NHANES alcohol usage and body measurements data.
   - Clean and preprocess features.
2. **Widmark Formula Application**:
   - BAC is estimated using the classic Widmark formula with personalized inputs.
3. **Model Training**:
   - An XGBoost Regressor is trained to predict BAC.
   - Evaluation metrics: R² score and Mean Squared Error (MSE).
4. **Feature Analysis**:
   - Feature Importance (XGBoost gain)
   - Feature Correlation Heatmap
5. **User Interaction**:
   - Users can input their sex, age, weight, and number of drinks.
   - Model predicts estimated BAC and classifies intoxication level.

---

## Intoxication Classification

| BAC Level | Status |
|:---|:---|
| < 0.02 | Sober |
| 0.02 – 0.05 | Tipsy |
| 0.05 – 0.08 | Buzzed |
| 0.08 – 0.10 | Legally Impaired |
| 0.10 – 0.15 | Drunk |
| 0.15 – 0.30 | Very Drunk |
| 0.30 – 0.40 | Severe Alcohol Poisoning |
| > 0.40 | Fatal Risk |

---

## Why XGBoost?

XGBoost (Extreme Gradient Boosting) was chosen for this project because:

- **High Performance**: XGBoost is known for its exceptional predictive accuracy, especially in regression tasks like BAC estimation.
- **Handles Missing Values**: Survey data often contains missing or noisy entries. XGBoost can automatically handle missing values during training.
- **Feature Importance**: XGBoost provides built-in ways to measure feature importance, helping explain how age, sex, drinking habits, and weight affect BAC.
- **Fast and Efficient**: The 'hist' tree method used in this project allows XGBoost to build models very quickly, even on large datasets.
- **Robust to Overfitting**: With parameters like regularization (`lambda`, `alpha`) and tree depth control, XGBoost can reduce the risk of overfitting to noisy health survey data.

Overall, XGBoost provided a strong balance between accuracy**, speed, and interpretability for modeling real-world alcohol consumption patterns and predicting BAC levels.

---

## Technologies Used
- Python 3.11+
- Pandas
- NumPy
- Matplotlib / Seaborn (Visualization)
- XGBoost (Machine Learning)
- Jupyter Notebook (VS Code Extension)

---

## How to Run Locally
1. Clone this repository:

```bash
git clone https://github.com/laniel123/Widmark-Formula-Model.git
cd Widmark-Formula-Model
```

2. Install requirements:

```bash
pip install -r requirements.txt
```

3. Open `formula model.ipynb` in Jupyter / VS Code.
4. Run all cells.
5. (Optional) Interact with the user BAC prediction tool at the end!

---

## Project Status
✅ Model trained and evaluated.  
✅ User input prediction working.  
✅ Feature importance and correlation analysis included.  

Planned Future Improvements:
- Introduce blood alcohol metabolism over time (absorption + elimination).
- Add more nuanced physiological factors.

---

## Acknowledgments
- NHANES (National Health and Nutrition Examination Survey) Data
- Classic Widmark BAC Estimation Formula
- XGBoost Python Library

---

> **Disclaimer**: This project is for educational purposes only and does not replace professional BAC testing or legal standards.
