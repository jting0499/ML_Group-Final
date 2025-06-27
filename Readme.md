
# 📘 Project Overview

This project addresses the business-critical issue of customer churn in online retail. Using a dataset with over 5,000 records and multiple behavioral and transactional variables, the goal is to **predict whether a customer is likely to churn**.

Following the CRISP-DM framework, the team:
- Explored data and identified key features affecting churn.
- Built and evaluated three classification models: Logistic Regression, Decision Tree, and Random Forest.
- Selected **Random Forest** as the final model due to its best overall performance in F1 Score, accuracy, and recall.

**Final Objective:** Deploy a reliable churn prediction model that supports targeted retention strategies through model-triggered CRM actions.

---

# 💻 How to Set Up and Run the Code

1. **Clone the repository**:
   ```bash
   git clone https://github.com/jting0499/ML_Group-Final.git
   ```

2. **Create a virtual environment (optional but recommended)**:
   ```bash
   virtualenv venv
   source venv/bin/activate  # on Windows: venv\Scripts\activate
   ```

3. **Install dependencies**:
   ```bash
   pip install -r requirements.txt
   ```

4. **Run Jupyter Notebook**:
   ```bash
   jupyter notebook \
    --notebook-dir="." \
    --ip=0.0.0.0 --port=3225
   ```

5. **To test the model locally (after training)**:
   ```bash
   fastapi dev main.py
   click: click http://127.0.0.1:8000
   to website: http://127.0.0.1:8000/dashboard
   ```

---

# 🔁 Instructions to Replicate the Model Training

1. **Load dataset**  
   - Source: [Kaggle Online Retail Customer Churn Dataset](https://www.kaggle.com/datasets/hassaneskikri/online-retail-customer-churn-dataset)

2. **Data preprocessing steps**:
   - Drop irrelevant columns (`Customer_ID`)
   - Convert target to binary integer (`Target_Churn`)
   - One-hot encode categorical features (`Gender`, `Promotion_Response`)
   - Apply scaling to numerical features using `StandardScaler` or `MinMaxScaler`

3. **Split data**:
   - Use `train_test_split()` with `random_state=42` and stratify by churn

4. **Train models**:
   - Logistic Regression 
   - Decision Tree
   - Random Forest 
   - Register model using `registerAJrjModel(model, metadata)`

5. **Evaluate models**:
   - Metrics: `Accuracy`, `Recall`, `Precision`, `F1 Score`, `RMSE`
   - Choose Random Forest as final based on:
     - F1 Score: **0.593**
     - Recall: **0.632**
     - Precision: **0.558**
     - Accuracy: **0.540**

---

# 🚀 Endpoint Details for Demo

- **Dashboard URL**: `http://127.0.0.1:8000/dashboard`
- **Local demo instruction**:
   - Launch FastAPI or Flask app via:
     ```bash
     fastapi dev main.py
     ```
   - Use `/test` endpoint for real-time inference
   - Input format:
     ```json
     {
       "Age": 32,
       "Tenure": 180,
       "DaysSinceLastOrder": 220,
       ...
     }
     ```

   - **Output**:
      ```json
      {
         1
      }
      ```
