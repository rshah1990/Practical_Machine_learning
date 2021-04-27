# DATA DRIFT

- There are three types of data drift by source 
  - shift in indepnedent variable (Covariant shift)
  - Shift in target variable (Prior probability shift)
  - Shift in relationship between the independent & target variable (Concept Shift)
  - Internal covariate shift (an important subtype of covariate shift)
- Drift detection is very critical when you dont have feedback loop or feedback loop is delayed

## Covariant shift

- Input data distribution changes. 
- ex: Face recognition algorithms that are trained predominantly on younger faces, yet the dataset has a much larger proportion of older faces in it.
- Multiple ways to detect covariant shirt 
  - Train classification model to classify Train & Production data, ROC AUC > 0.8 represent data has been drifted 
  - Feature importance of the model will give us column which is most drifted 
  - Testing accuracy can be calulcated using Matthews correlation coefficient nothing but drift coefficent.
  - Matthews correlation coefficient is best metrics when both class is equally important, values ranges from -1 to 1. since F1 score does not consider TN.
  - We can also monitor distribution at feature level using histogram / Wasserstein & Energy Distance/Kernel density estimation

