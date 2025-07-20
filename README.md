💳 Credit Card Fraud Detection – Data Mining Techniques

📁 Dataset
* **Source:** Kaggle (Simulated credit card transactions)
* **Generation Tool:** Sparkov Data Generation with Python "faker" library
* **Total Records:** 1.856 million transactions
* **Split:** 1.30M training, 556k testing
* **Features:** 23 variables including:
   * Transaction details (date, time, amount, merchant)
   * Demographics (gender, age, location)
   * Geographic data (lat/long, city population)
* **Target Variable:** is_fraud (binary classification)

🔍 Data Exploration Insights
* **Class Imbalance:** 1,289,169 legitimate vs 7,506 fraudulent transactions
* **Fraud Patterns:**
   * Peak activity on Mondays
   * Higher amounts in shopping/grocery categories
   * Males show higher fraud frequency and amounts
   * Distance distribution: Bell curve (30-70 miles peak)
* **Geographic Hotspots:** New York leads in fraud cases
* **Category Analysis:** Personal care, health fitness show lower fraud rates

🧹 Data Preprocessing
* **Data Quality:** No missing values found
* **Privacy Protection:** Removed sensitive customer data columns
* **Feature Engineering:**
   * Label encoding for categorical variables
   * Temporal features from transaction timestamps
* **Imbalance Handling:** Hybrid approach using SMOTE + Random Undersampling

🤖 Model Architectures
| Model | Description | Key Characteristics |
|-------|-------------|-------------------|
| **Random Forest** | Ensemble of decision trees | Bootstrap sampling, feature randomness |
| **Naive Bayes** | Probabilistic classifier | Assumes feature independence |
| **XGBoost** | Gradient boosting | Sequential error correction, regularization |
| **MLP** | Neural network | Multi-layer perceptron with backpropagation |

📊 Performance Results (Imbalanced Data)
| Model | Accuracy | Precision | Recall | F1-Score | AU-ROC | PR-AUC |
|-------|----------|-----------|---------|----------|---------|---------|
| Random Forest | 1.00 | 0.96 | 0.80 | 0.86 | 0.80 | 0.76 |
| Naive Bayes | 0.99 | 0.62 | 0.73 | 0.65 | 0.73 | 0.35 |
| **XGBoost** | **1.00** | **0.92** | **0.82** | **0.85** | **0.82** | **0.74** |
| MLP | 1.00 | 0.83 | 0.50 | 0.50 | 0.50 | 0.34 |

🔧 Sampling Strategies & Results
| Strategy | Best Model | Precision | Recall | F1-Score | AU-ROC | PR-AUC |
|----------|------------|-----------|---------|----------|---------|---------|
| 20% Over + 20% Under | XGBoost | 0.96 | 0.89 | 0.92 | 0.89 | 0.90 |
| 20% Over + 30% Under | XGBoost | 0.96 | 0.90 | 0.93 | 0.90 | 0.91 |
| **20% Over + 40% Under** | **XGBoost** | **0.95** | **0.91** | **0.93** | **0.91** | **0.92** |

📈 Key Performance Metrics
* **Precision:** Minimizes false alarms (important for customer experience)
* **Recall:** Catches actual fraud cases (critical for loss prevention)
* **F1-Score:** Balanced measure of precision and recall
* **AU-ROC:** Overall discrimination capability
* **PR-AUC:** Performance on imbalanced data

🧰 Technology Stack
* **Programming:** Python
* **Data Processing:** pandas, numpy
* **Machine Learning:** scikit-learn, XGBoost
* **Sampling:** SMOTE (Synthetic Minority Over-sampling)
* **Visualization:** matplotlib, seaborn
* **Deep Learning:** TensorFlow/Keras (for MLP)

✅ Key Findings
* XGBoost and Random Forest consistently outperform other models
* Ensemble tree-based methods excel at fraud detection
* Hybrid sampling (20% over + 40% under) yields best results
* Trade-off exists between precision and recall with deeper sampling
* Model performance improves significantly after addressing imbalance

🚀 Future Enhancements
* **Advanced Models:** Deep learning architectures (LSTM for sequential patte
