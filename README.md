

#  Multiple Linear Regression Analysis: Predicting Highway MPG  

##  **Project Overview**  
This project applies **Multiple Linear Regression (MLR)** to predict Highway mpg (miles per gallon) of a car(`Fuel Information.Highway MPG`) based on various vehicle features. The dataset includes technical specifications of cars, such as engine type, fuel type, and transmission details.  

---

##  **Objective**  
- Identify key factors affecting highway fuel efficiency.  
- Build a robust regression model to predict Highway mpg (miles per gallon) of a car(`Fuel Information.Highway MPG`).  
- Evaluate the model’s performance and optimize feature selection.  

---
##  **Project Structure** 
```
📂 MLR Analysis/
│
├── 📄 LICENSE
│
├── 📄 README.md
│
├── 📂 data/
│   └── dataset.csv  # Your dataset
│
└── 📄 MLR_analysis.ipynb  # Google Colab notebook with the full analysis

```
##  **Dataset Information**  
The dataset includes the following features:  
- **Vehicle Specifications:** `Identification.Model Year`, `Dimensions.Height`, `Dimensions.Width`, etc.  
- **Engine Details:** `Engine Information.Engine Type`, `Torque`, `Horsepower`, etc.  
- **Fuel Information:** `Fuel Type`, `City MPG`, etc.  
- **Transmission Details:** `Number of Forward Gears`, `Transmission Type`.  

---

##  **Data Preprocessing Steps**  
-  **Handling duplicated Values:** Removed duplicated values 
-  **Encoding Categorical Variables:**  
   - Applied **Target Encoding** for `'Identification.Make'`, `'Identification.Model Year'`, `'Engine Information.Engine Type'`,`'Engine Information.Driveline'` 
   - Applied **One-Hot Encoding** for `'Fuel Information.Fuel Type'`,`'Engine Information.Transmission'`,`'Identification.Classification'`  
-  **Feature Scaling:** Standardized numerical features where necessary.  
-  **Outlier Treatment:** Used **IQR method**  to remove extreme values.  

---

##  **Exploratory Data Analysis (EDA)**  

###  **Correlation Heatmap**  
A heatmap was generated to analyze the correlation between independent variables and the target variable (`Fuel Information.Highway MPG`).  


![Image](https://github.com/user-attachments/assets/6194d804-5e56-4def-8e64-6199d23bdf45)
 **Key Observations:**  
- `Fuel Information.City mpg` is highly correlated with `Highway MPG`.  
- Some features exhibit multicollinearity, requiring feature selection.  

---

##  **Feature Selection**  
To select the best predictors:  
- **Recursive Feature Elimination (RFE):** Selected the most impactful features.  
- **Multicollinearity Check (VIF):** Removed features with **VIF > 10** to avoid redundancy.  
- **Correlation Analysis:** Chose features highly correlated with the target variable but uncorrelated with each other.  

**Final Selected Features:**  
```
['Fuel Information.City mpg', 'Identification.Model Year_encoded', 
 'Fuel Information.Fuel Type_Diesel fuel', 'Fuel Information.Fuel Type_E85', 
 'Fuel Information.Fuel Type_Gasoline']
```

---

##  **Model Building**  
- **Model Used:** Multiple Linear Regression  
- **Train-Test Split:** 80% Training, 20% Testing  
- **Evaluation Metrics:**  
  -  **R² Score:** Indicates how well the model explains variance.  
  -  **VIF Analysis:** Ensures low multicollinearity.  
  -  **RMSE:** Measures average error in predictions.  

---

##  **Results & Model Evaluation**  

| Metric  | Before Handling Outliers | After Handling Outliers |
|---------|--------------------------|-------------------------|
| R² Score  | 0.9121                    | 0.9495                   |
| RMSE      | 5.62                     | 3.21                    |
| Adjusted R² | 0.9357                     | 0.9529                   |

 **After handling outliers, the model became more generalizable with reduced errors.**  

---

##  **Residual Analysis**  

To check model assumptions, we plotted residuals to ensure they followed a normal distribution and exhibited homoscedasticity.

![Image](https://github.com/user-attachments/assets/a661264f-c6c5-468a-bbbd-3ab50f05e84e)

![Image](https://github.com/user-attachments/assets/17a0c464-8575-4a3b-89a5-1c80519de371)

 **Key Takeaways from Residual Analysis:**  
- The residuals approximately follow a normal distribution.  
- No clear heteroscedasticity, indicating stable variance.  
- Confirms that our model meets linear regression assumptions.  

---

##  **Key Takeaways**  
 - **Feature Engineering Matters:** Proper encoding and selection significantly improved model performance.  
 - **Multicollinearity is Crucial:** Reducing **VIF** led to more stable coefficients.  
-  **Outlier Handling is Important:** Post-cleaning, the model showed better predictive accuracy.  
 - **Business Impact:** This model helps **automobile manufacturers** understand which factors most influence fuel efficiency.  

---
##  **Next Steps**
Here's an updated `README.md` template with **Project Structure** and **How to Run Your Code** sections, specifically for Google Colab.

---

##  How to Run Your Code

###  Open the Google Colab Notebook
Click the link below to open the project in Google Colab:
```
[![Open In Colab](https://colab.research.google.com/assets/colab-badge.svg)](https://colab.research.google.com/github/yourusername/your_project_name/blob/main/MLR_analysis.ipynb)
```

---

###  Upload the Dataset
- Make sure to upload your dataset (`dataset.csv`) to Colab by:
  - Clicking **Files** on the left sidebar.
  - Clicking **Upload** and selecting your CSV file.

---

###  Install Dependencies in Colab
If needed, install dependencies directly in Colab by running:
```python
!pip install pandas numpy scikit-learn matplotlib seaborn
```

---

###  Run the Code
- Execute all the cells in the notebook step by step by pressing **Shift + Enter**.

---

###  Save Results
- Download your output files by right-clicking on them in the **Files** section and choosing **Download**.

---

##  **Next Steps**  
- Try **Ridge/Lasso Regression** to improve regularization.  
- Perform **Cross-Validation** for better generalization.  
- Test on **new unseen vehicle data** to validate real-world performance.  


---

##  **References**  
- **Scikit-Learn Documentation**: [https://scikit-learn.org/](https://scikit-learn.org/)  
- **Pandas Data Manipulation**: [https://pandas.pydata.org/](https://pandas.pydata.org/)  

---

##  **Contributors**  
 **Aparna S** - [LinkedIn](https://www.linkedin.com/in/aparna-s-60017a290/)  

---

