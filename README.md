# 🌌 Hunting for Exoplanets using Machine Learning

This project was created as part of the **Udemy Certification Course** under **Spartificial Innovations Pvt. Ltd.**  
It demonstrates the application of **machine learning techniques** to detect **exoplanets** — planets orbiting stars outside our solar system — using **astronomical time series data**.  
The goal is to understand how **machine learning models** can analyze **light curves** to identify stars with exoplanets.



##  Overview
Exoplanets are detected when a planet passes in front of its host star, causing a slight dip in the star’s brightness — a phenomenon called the **transit method**.  
This project analyzes **light curves** collected from the **Kepler Space Telescope**, consisting of thousands of observations of star brightness over time.

Using this data, the project builds **machine learning models** to classify stars as either **having exoplanets** or **not**, based on their light curves.



##  Theoretical Background

### 1. Light Curves and Transit Method
- A star’s brightness measurement over time forms a **light curve**.  
- A dip in the light curve corresponds to a planet transiting and partially blocking the star’s light.

### 2. Machine Learning Classification
- The goal: classify stars based on features extracted from light curves.  
- **K-Nearest Neighbors (KNN)** algorithm is used for classification in this project.

### 3. Challenges
- Handling **imbalanced classes**, as stars without exoplanets heavily outnumber those with exoplanets.  
- Managing **outliers** in the flux data which can skew model performance.


##  Computational Approach

### 1. Data Preparation
- Data imported from the **Kepler dataset** containing time series flux values for **5087 stars**.  
- Missing values were checked and found to be absent.  
- Extreme **outliers in flux data** were identified and removed to improve model robustness.  
- Class labels were simplified to **binary (0 for no exoplanet, 1 for exoplanet).**

### 2. Machine Learning Model: K-Nearest Neighbors (KNN)
- Selected because of its **simplicity and effectiveness** for classification problems.  
- **Euclidean distance** is used to compute similarity between data points.  
- The value of **K (number of neighbors)** is tuned to optimize model accuracy and performance.

### 3. Handling Data Imbalance
- Initially, the model was trained on the **imbalanced dataset** to observe baseline performance.  
- Applied **RandomOverSampler** to balance the minority class (stars with exoplanets) by duplicating samples.  
- Retrained and evaluated the model on the **balanced dataset** for improved results.


##  Libraries Used
- **Pandas & NumPy:** Data manipulation and numerical operations.  
- **Matplotlib & Seaborn:** Data visualization including light curves and performance metrics.  
- **scikit-learn:** KNN classifier and related tools for model building and evaluation.  
- **imblearn:** For handling imbalanced data using oversampling techniques.

---

## Results and Observations
- The model showed **high accuracy**, but other metrics (precision, recall, F1-score) revealed sensitivity to class imbalance initially.  
- After **oversampling** the minority class, model performance improved across all metrics, making predictions more reliable.  
- Optimal **K value** was found to be **1** for this dataset based on error rate analysis.  
- Visualization of **confusion matrices** and **ROC curves** confirmed better classification post-balancing.

---

##  Conclusion
This project illustrates applying **machine learning** to real **astrophysical data** to classify stars by the presence of exoplanets.  
Handling **imbalanced data** and **outliers** is critical to building robust models in such scientific tasks.
