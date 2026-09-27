# 💊 Drug Prescription Classification using Decision Tree

## 📌 Overview
A machine learning project that predicts appropriate drug prescriptions based on patient characteristics using a Decision Tree classifier. The model analyzes patient age, gender, blood pressure, cholesterol levels, and sodium-to-potassium ratio to recommend the most suitable medication.

## 📊 Dataset
The project uses the **Drug200 dataset** containing 200 patient records with the following features:

### **Features (Predictors)**
- **Age**: Patient's age (numeric)
- **Sex**: Gender (F/M → encoded as 0/1)
- **BP**: Blood Pressure levels (LOW, NORMAL, HIGH → encoded as 0,1,2)
- **Cholesterol**: Cholesterol levels (NORMAL, HIGH → encoded as 1,2)
- **Na_to_K**: Sodium to Potassium ratio (numeric)

### **Target Variable**
- **Drug**: One of 5 prescription drugs (drugA, drugB, drugC, drugX, drugY)

## 🚀 Features
- **Data Preprocessing**: Categorical encoding and normalization
- **Decision Tree Classifier**: Interpretable model for medical decision-making
- **Model Visualization**: Full decision tree visualization for transparency
- **Performance Metrics**: Accuracy evaluation and model interpretation
- **Feature Importance**: Understanding which factors drive prescription decisions

## 🛠️ Installation & Usage

### **Prerequisites**
```bash
pip install pandas numpy matplotlib scikit-learn
```

### **Running the Project**
1. Clone the repository:
```bash
git clone https://github.com/yourusername/Drug-Prescription-Classifier.git
cd Drug-Prescription-Classifier
```

2. Place the dataset in the project directory:
```bash
drug-prescription-classifier/
├── drug200.csv          # Dataset
├── drug_classifier.ipynb # Main notebook
├── README.md            # This file
└── requirements.txt     # Dependencies
```

3. Run the Jupyter notebook:
```bash
jupyter notebook drug_classifier.ipynb
```

## 📈 How It Works

### **1. Data Preprocessing**
```python
# Encode categorical variables
df = df.replace({'F': 0, 'M': 1})
df = df.replace({'LOW': 0, 'NORMAL': 1, 'HIGH': 2})
```

### **2. Model Training**
- **Algorithm**: Decision Tree Classifier
- **Criterion**: Entropy (Information Gain)
- **Max Depth**: Limited to 4 levels for interpretability
- **Random State**: Fixed for reproducibility

### **3. Model Evaluation**
- **Test Size**: 20% of data
- **Metric**: Accuracy Score
- **Result**: 95% accuracy on test data

## 🔍 Model Architecture

### **Decision Tree Parameters**
```python
drug_tree = DecisionTreeClassifier(
    criterion="entropy",      # Use information gain
    max_depth=4,              # Limit tree depth
    random_state=4            # Ensure reproducibility
)
```

### **Feature Importance**
The model identifies the most important features for drug prescription:
1. **Na_to_K**: Sodium to Potassium ratio
2. **Age**: Patient's age
3. **BP**: Blood pressure levels
4. **Cholesterol**: Cholesterol levels
5. **Sex**: Gender

## 📊 Results

### **Model Performance**
- **Training Accuracy**: High (exact value not shown)
- **Test Accuracy**: **95.00%**
- **Confusion Matrix**: Available for detailed error analysis
- **Classification Report**: Precision, recall, F1-scores per drug class

### **Decision Tree Visualization**
![Decision Tree Visualization](tree_visualization.png)
*The decision tree shows clear decision boundaries and logic behind prescriptions*

## 💡 Interpretation

### **Key Decision Rules**
1. **Primary Split**: Based on Na_to_K ratio threshold
2. **Secondary Splits**: Age and blood pressure
3. **Tertiary Factors**: Cholesterol and gender

### **Example Predictions**
```python
# Example patient
patient_data = {
    'Age': 45,
    'Sex': 1,        # Male
    'BP': 2,         # HIGH
    'Cholesterol': 2, # HIGH
    'Na_to_K': 15.0
}

# Predicted drug: drugY
```

## 🏗️ Project Structure
```
drug-prescription-classifier/
│
├── drug200.csv                     # Dataset
├── drug_classifier.ipynb           # Main notebook
├── README.md                       # Documentation
├── requirements.txt                # Dependencies

```

## 🔧 Customization

### **Adjust Model Parameters**
```python
# Customize Decision Tree
custom_tree = DecisionTreeClassifier(
    criterion='gini',        # Alternative to entropy
    max_depth=None,          # Unlimited depth
    min_samples_split=2,     # Minimum samples to split
    min_samples_leaf=1,      # Minimum samples in leaf
    random_state=42
)
```

### **Add New Features**
```python
# Example: Add BMI calculation
df['BMI'] = df['Weight'] / (df['Height'] ** 2)
```

## 📈 Performance Improvement Tips

### **1. Feature Engineering**
- Create interaction features
- Normalize numerical features
- Handle outliers in Na_to_K ratio

### **2. Model Enhancement**
- Try Random Forest for better generalization
- Use GridSearchCV for hyperparameter tuning
- Implement cross-validation

### **3. Evaluation**
- Add cross-validation scores
- Include confusion matrix visualization
- Calculate precision/recall per drug class

## 🎯 Use Cases

### **Medical Applications**
1. **Clinical Decision Support**: Assist doctors in prescription decisions
2. **Medical Education**: Teaching tool for understanding drug prescription factors
3. **Pharmaceutical Research**: Identify patient segments for drug efficacy

### **Business Applications**
1. **Insurance Risk Assessment**: Predict medication needs
2. **Pharmacy Inventory**: Forecast drug demand
3. **Telemedicine**: Automated preliminary recommendations

## ✉️ Contact

Your Name - https://www.linkedin.com/in/parsa-khaghani-a22847326/

Project Link: https://github.com/nowherewalrus/Drug-Prescription-Classifier.git

## ⚠️ Medical Disclaimer

**Important**: This model is for educational and research purposes only. It should **NOT** be used for actual medical diagnosis or treatment decisions. Always consult with qualified healthcare professionals for medical advice.

## 📚 References

1. Scikit-learn Documentation: [Decision Trees](https://scikit-learn.org/stable/modules/tree.html)
2. Medical Decision Support Systems
3. Pharmaceutical Research Papers

---

**Happy Classifying! 💊📊**
