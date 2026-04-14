# Heart Disease Prediction

Logistic regression model for predicting heart disease from clinical data, with LIME explanations and bootstrap uncertainty estimates. Built on the UCI Cleveland dataset.

The point of this project was less about the prediction (logistic regression on Cleveland is well-trodden ground) and more about making the model's reasoning visible — which features drive individual predictions, and how confident the model actually is.

## Dataset

[Heart Disease UCI Dataset](https://www.kaggle.com/datasets/cherngs/heart-disease-cleveland-uci) from Kaggle, derived from the Cleveland Clinic dataset.

Citation: Cherngs. (2020). Heart Disease UCI Dataset. Retrieved from [Kaggle](https://www.kaggle.com/datasets/cherngs/heart-disease-cleveland-uci).

## Exploratory Analysis

![Correlation Heatmap](visuals/correlation_heatmap.png)

The heatmap shows which clinical features correlate with heart disease presence. Chest pain type (cp), maximum heart rate (thalach), and exercise-induced angina (exang) show the strongest associations.

## Results

Logistic regression with standard preprocessing (scaling, one-hot encoding). Accuracy: 86%, Precision: 84%, Recall: 89%.

![ROC Curve](visuals/roc_curve.png)

Bootstrap resampling gives confidence intervals on predictions — useful in clinical contexts where a point estimate without uncertainty isn't actionable.

## Explainability

LIME was used for individual prediction explanations. For example, high maximum heart rate (thalach) is typically associated with lower risk, while chest pain type (cp) can push predictions either direction depending on context.

![LIME Explanation](visuals/lime_explanation_instance5.png)

## Files

Notebooks/
└── heart_disease_analysis.ipynb       # Main analysis and model development

data/
└── heart.csv                          # UCI Cleveland dataset

visuals/                               # All saved visualizations
├── correlation_heatmap.png
├── target_distribution.png
├── boxplots_numerical.png
├── confusion_matrix.png
├── roc_curve.png
├── feature_importance_logreg.png
├── lime_explanation_instance5.png
└── uncertainty_bootstrap.png

heart_disease_analysis.py              # Script version of the notebook
README.md                              # Project documentation



---

## Tools

Python, pandas, scikit-learn, matplotlib, seaborn, LIME

## Usage

```bash
git clone https://github.com/SamInMotion/heart-disease-risk-model-xai.git
cd heart-disease-risk-model-xai
pip install -r requirements.txt
python heart_disease_analysis.py
```

##  License
This project is licensed under the MIT License.
