# Breast Cancer Classification using Machine Learning Models

### Objective
This project applied multiple **machine learning algorithms** to the `BreastCancer` dataset from the **mlbench** package in R to predict whether a tumor is **benign** or **malignant** based on patient cell features.  

---

### Dataset
- **Source:** `mlbench` R package  
- **Size:** 699 records  
- **Target Variable:** `Class` (benign or malignant)  
- **Features:** 9 cytological attributes (e.g., Clump Thickness, Cell Size, Bare Nuclei, etc.)

---

### Data Processing
1. Converted all factor variables (except `Class`) to numeric.  
2. Replaced missing values in `Bare.nuclei` with the column mean.  
3. Removed the `Id` column as it didn’t contribute to prediction.  
4. Used **10-fold cross-validation (2 repetitions)** for model evaluation via the `performanceEstimation` package.  

---

### Models Evaluated
| Model | Description |
|--------|--------------|
| Logistic Regression | Baseline statistical model |
| Neural Network | Feedforward NN with hidden units (sizes 1–3) |
| Random Forest | Ensemble model with 50 trees |
| Support Vector Machine (SVM) | Radial kernel |
| Gradient Boosting (GBM) | Models with 50 and 100 trees |

---

### Evaluation Metrics
Each model was evaluated using:
- **Accuracy**
- **Precision**
- **Recall**
- **F1 Score**

| Model | Accuracy | Precision | Recall | F1 Score |
|--------|-----------|------------|---------|-----------|
| Random Forest | 0.966 | 0.978 | 0.970 | **0.974** |
| SVM | 0.967 | 0.984 | 0.965 | **0.974** |
| GBM (100 trees) | 0.967 | 0.978 | 0.971 | 0.974 |
| Logistic Regression | 0.964 | 0.973 | 0.974 | 0.973 |
| Neural Network (size = 3) | 0.957 | 0.970 | 0.965 | 0.967 |


---

### Model Comparison
- **Random Forest** and **SVM** achieved perfect classification (100% accuracy) on the test set.  
- **GBM** performed strongly but had minor misclassifications.  
- **Neural Networks** showed more variability depending on hidden layer size.  

Figures from the report show:
- **Figure 1:** Cross-validation performance distributions  
- **Figures 3–5:** Confusion matrices comparing SVM, Random Forest, and GBM  
- **Figure 6–7:** Feature importance comparisons between models:contentReference[oaicite:1]{index=1}

---

### Insights
- Ensemble and margin-based methods (RF, SVM) were most stable and accurate.  
- Neural networks underperformed slightly due to small dataset size and variance.  
- `Bare.nuclei`, `Cl.thickness`, and `Cell.size` were top predictive features across models.  

---

### Files in This Folder
| File | Description |
|------|--------------|
| [`Breast_Cancer_Classification_Result.pdf`](./Breast_Cancer_Classification_Result.pdf) | Project report summarizing model comparison and insights |
| [`Breast_Cancer_Classification_Rscript.pdf`](./Breast_Cancer_Classification_Rscript.pdf) | Full code output and visualizations from R |

---

### Tools & Packages
**Language:** R  
**Libraries:** `mlbench`, `caret`, `performanceEstimation`, `randomForest`, `e1071`, `gbm`, `nnet`, `ggplot2`

---

### Key Takeaways
- **Random Forest** was the most balanced and consistent performer.  
- **SVM** matched RF in accuracy but showed slightly higher variance.  
- Reliable preprocessing (handling missing values and encoding) significantly improved model stability.  

---

*Completed as part of STAT 615 — Data Mining for Analytics (Spring 2025) at St. Cloud State University.*
