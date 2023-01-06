# ESAA_Projects

# [1] Workout Recommendations
📎 file: `YB_team3_project_final_code.ipynb`  
  
I, as a member in a team of 4, carried out a project dealing with a data of comprehensive physical fitness measurement and exercise prescription. The data consists of measurements such as age, sex, height, weight, BMI, blood pressure, flexibility and a set of prescribed workout routine, warm-up(named ‘pre’), main exercises(called ‘main’), and cool-down(named ‘end’). We utilized this data to make a **personalized workout recommendation algorithms** by clustering and classification models

## 1️⃣ Preprocessing
- Since label data was a string where all the exercises are listed in the order of phase and are separate with commas, selected exercises have been converted to columns where each one represent whether the exercise is included or not.
- As result, we made 3 dataframes of each phase of workout with multi labels for classification.
- (* Our aim was to apply machine learning algorithms, so we didn’t use the deep learning algorithms for multi-class classification)  
<img width="620" alt="Screen Shot 2023-01-04 at 7 56 01 PM" src="https://user-images.githubusercontent.com/101344070/210968709-aa329619-d372-4bd3-b130-9f0b551a93c5.png">  
other preprocessing tasks such as missing value and outliers imputation was processed, and it is described in the file in much more details.

## 2️⃣ Modelling
<img width="926" alt="Screen Shot 2023-01-04 at 4 54 20 PM" src="https://user-images.githubusercontent.com/101344070/210968861-3cef89b5-98c4-4276-a766-65a2480ea226.png">

1. `Clustering`
- tried K-means, Meanshift, GMM and DBSCAN chose K-means fits the best among them based on Silhouette Coefficient and Silhouette graph
- built an algorithms that recommend top n exercises from the cluster where the center is the closest from the new input (user data) since K-means have centers of all clusters
- The constant ‘n’ is a value that the user can decide and enter

2. `Classification`
- trained model with user's physical fitness measurement values as features and whether or not each exercise is prescribed as a labels
- 54 exercises which were prescribed more than 4000 times in the train dataset was used as labels
- Considering that this case is not fatal for negative observation, random forest model was selected based on recall and accuracy, and its hyperpharameters were tuned
- Then the model predicted whether each exercise was recommended or not in the test dataset

Our final algorithm combines these two methods to recommend workout routines for each user based on their physical measurement features, and return the list of exercises which includes the result of most-recommended exercises from the closest cluster and the classification model trained by our given dataset.  

## 3️⃣ Limitation and Conclusions
- There were some columns which has most of its rows missing and we deleted the whole column for the performance.
- Since there were too many exercises in the label string. So for practical and realistic purpose, only highly recommended exercised were subject to the classification.
- There would be input errors due to errors in measurement since there were some obvious outliers that would be impossible for human.
- In spite of the limitations, we could completed algorithms that recommends personalized workout routines based on data for the purpose we initially envisioned And we also discussed a lot on the user’s need and the prospect role of the algorithms to private healthcare, if it can be further improved.
  
  
---
# [2] 

