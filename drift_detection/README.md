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

