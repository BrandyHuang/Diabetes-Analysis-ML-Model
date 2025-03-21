# Diabetes Analysis Using Machine Learning Models

## Project description
This project uses the Pima Indians Diabetes Database and it aims to predict type 2 diabetes
based on health metrics, including glucose, BMI, blood pressure, insulin, age, pregnancies, skin
thickness, and diabetes pedigree function (genetic risk score). Furthermore, it helps to predict
key risk factors of different age groups and see the impact of age factor in diabetes.

## Modeling Approach
* Logistic regression: logistic regression provides clear odds ratios, which can explain
  diabetes risk factors for better interpretability

* Random forest: random forest can solve the problem of multicollinearity and it is used for
  better predictive accuracy

## Key Insights

### Initial VIF Values

| Feature                     | VIF      |
|-----------------------------|---------:|
| Pregnancies                 | 3.682    |
| Glucose                     | 20.865   |
| BloodPressure               | 27.784   |
| SkinThickness               | 17.815   |
| Insulin                     | 5.842    |
| BMI                         | 34.916   |
| DiabetesPedigreeFunction    | 3.192    |
| Age_Middle-aged             | 2.285    |
| Age_Older                   | 1.797    |
| Age_Senior                  | 1.256    |

### Regression Coefficients
| Feature                   | Coef.   | Std. Err. | z       | P>|z|  | [0.025  | 0.975]  |
|---------------------------|--------:|----------:|--------:|------:|--------:|--------:|
| **const**                 | -2.5591 | 0.2470    | -10.3598 | 0.0000 | -3.0432 | -2.0749 |
| **Pregnancies**           | 0.0602  | 0.0294    | 2.0464  | 0.0407 | 0.0025  | 0.1179  |
| **Insulin**               | 0.0048  | 0.0011    | 4.5791  | 0.0000 | 0.0028  | 0.0069  |
| **DiabetesPedigreeFunction** | 0.9293  | 0.2500    | 3.7166  | 0.0002 | 0.4392  | 1.4193  |
| **Age_Middle-aged**       | 1.0220  | 0.2144    | 4.7677  | 0.0000 | 0.6019  | 1.4422  |
| **Age_Older**             | 0.9090  | 0.2960    | 3.0713  | 0.0021 | 0.3289  | 1.4890  |
| **Age_Senior**            | -0.4297 | 0.4803    | -0.8947 | 0.3710 | -1.3711 | 0.5117  |

---

#### **Dropped Features Due to High VIF**
- **BMI** (VIF: 34.92)
- **BloodPressure** (VIF: 20.71)
- **Glucose** (VIF: 13.48)
- **SkinThickness** (VIF: 5.85)

---

####  **Final Features After Dropping High VIF Terms**
`['Pregnancies', 'Insulin', 'DiabetesPedigreeFunction', 'Age_Middle-aged', 'Age_Older', 'Age_Senior']`

### Model Evaluation Point Metric
| Logistic Regression | Random Forest |
|---------|---------|
| ![Alt1](Photo/Logistic.png) | ![Alt2](Photo/RF.png) |

### Model Evaluation AUCPRC
| Logistic Regression | Random Forest |
|---------|---------|
| ![Alt1](Photo/Lo_AUCPRC.png) | ![Alt2](Photo/RF_AUCPRC.png) |

### Insights
Glucose was the strongest predictor, signaling impaired sugar metabolism, with BMI, insulin
levels, and DPF also playing key roles, however, they might be related to other factors as they
show high correlation with other factors. Age increased diabetes risk, especially after 35, but
risk factors varied by age. Young adults (18-30) had stronger associations with Skin Thickness,
middle-aged (31-45) with insulin resistance, older adults (46-60) with BMI, and seniors (61+)
with Blood Pressure, linking diabetes to cardiovascular health. These findings emphasize the
need for age-specific screening, prevention strategies, and targeted diabetes management.

## Practical Implications
These findings support targeted screening and prevention. Age-based screening improves
detection in middle-aged and older adults, reducing diabetes progression and costs. Plus,
diabetes solutions can be customized in different age groups as well. Predictive modeling
enhances risk assessment, resource allocation, and data-driven decision-making, optimizing
chronic disease management and patient outcomes.
