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
- Google Facets is another tool which helps in comparing statistics for train & production data 

## Prior probability shift

- prior probablity shift focus on change in distribution of target variable 
- this is mainly in the algo where p(x/y) is calculated, ex: Naive Bayes 
- If the training set has equal prior probabilities on the number of spam emails that you receive (i.e. the probability of an email being spam is 0.5), then we would expect 50% of the training set to contain spam emails and 50% to contain non-spam.
- If, in reality, only 90% of our emails are spam (perhaps not unlikely), then our prior probability of the class variables has changed


## Concept drift 

- its very diffuclt to measure, relation between features & target changes 
- ex: they way user was mapping any claim is changed 

## Internal Covariate Shift

- suspected influence of covariance shift in the hidden layers of deep neural networks
- the way we normalize input data , similar way we need to normalize input to hidden layer 
- batch normalization layer helps to reduce training time & help in hyperparemeter optimization

