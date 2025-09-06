# 🚗 Toyota Corolla Price Prediction using Multiple Linear Regression  

## 📌 Project Overview  
This project focuses on predicting the resale prices of **Toyota Corolla cars** using **Multiple Linear Regression (MLR)**.  
The goal is two-fold:  
- **Academic**: Practice end-to-end regression modeling (EDA, feature selection, residual analysis).  
- **Professional**: Solve a real-world business problem — predicting used car prices for better decision-making in the automotive resale market.  

---

## 📊 Dataset  
- **Rows:** 1436 (reduced to ~1432 after outlier handling)  
- **Columns:** 10 (after dropping `Id` and `Model`, 8 features used)  
- **Key Features:**  
  - `Age_08_04` → Age of the car in months  
  - `KM` → Mileage  
  - `HP` → Horsepower  
  - `Doors` → Number of doors  
  - `Cylinders` → Engine cylinders  
  - `Gears` → Number of gears  
  - `Weight` → Car weight  
- **Target Variable:** `Price`  

---

## 🔧 Methodology  
1. **Data Cleaning**  
   - Removed irrelevant columns (`Id`, `Model`).  
   - Handled influencers/outliers using **Cook’s Distance**.  
   - Final dataset size: ~1432 records.  

2. **Exploratory Data Analysis (EDA)**  
   - Pairplots, correlation heatmaps, and scatterplots.  
   - Strong negative correlation between `Age_08_04` and `Price` (-0.87).  
   - Positive correlation between `Weight` and `Price` (0.58).  

3. **Model Building**  
   - Implemented **Multiple Linear Regression** using `statsmodels`.  
   - Iteratively refined model by removing insignificant features (`Doors`).  
   - Checked multicollinearity using **VIF**.  

4. **Model Diagnostics**  
   - **Normality of Residuals** (Q-Q plot).  
   - **Homoscedasticity** (Residual vs Fitted plot).  
   - **Influential Points** detection with Cook’s Distance & Influence plots.  

---

## 📈 Results  
- **Final Model Performance**:  
  - R² = **0.875**  
  - Adjusted R² = **0.874**  
- **Key Predictors**:  
  - `Age_08_04` (older cars → lower price)  
  - `KM` (higher mileage → lower price)  
  - `HP` (higher horsepower → higher price)  
  - `Weight` (heavier cars → higher price)  

- **Example Prediction:**  
  For a 23-month-old Corolla with **KM=46986, HP=90, Cylinders=4, Gears=5, Weight=1165**,  
  the model predicts a price of **≈ 16,763 units**.  

---

## 📸 Sample Visualizations  
(Add these plots as PNGs in a `/plots` folder and link them here)  

- Correlation Heatmap  
- Pairplot of Variables  
- Residual Q-Q Plot  
- Cook’s Distance (Outlier Detection)  


![Heatmap](plots/heatmap.png)  
![Residual Plot](plots/residuals.png)  
![Cook’s Distance](plots/cooks.png)  
