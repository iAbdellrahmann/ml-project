
# Student performance prediction
** the main idea of the project to demonstrate the idea of from datascience idea to production 

About the Data :
The dataset The goal is to predict math score of given student (Regression Analysis).

There are 10 independent variables (including id):

Columns:

* Gender: The gender of the student (male/female)
* Race/ethnicity: The student's racial or ethnic background (Asian, African-American, Hispanic, etc.)
* Parental level of education: The highest level of education attained by the student's parent(s) or guardian(s)
* Lunch: Whether the student receives free or reduced-price lunch (yes/no)
* Test preparation course: Whether the student completed a test preparation course (yes/no)
* Math score: The student's score on a standardized mathematics test
* Reading score: The student's score on a standardized reading test
* Writing score: The student's score on a standardized writing test

Target variable
* Math Score

* dataset link: https://www.kaggle.com/datasets/rkiattisak/student-performance-in-mathematics
* More about the data: http://roycekimmons.com/tools/generated_data/exams

## Approach of the project
1- Data Ingestion :

* In Data Ingestion phase the data is first read as csv.
* Then the data is split into training and testing and saved as csv file.

2- Data Transformation :

* In this phase a ColumnTransformer Pipeline is created.
* For Numeric Variables first SimpleImputer is applied with strategy median , then Standard Scaling is performed on numeric data.
* For Categorical Variables SimpleImputer is applied with most frequent strategy, then ordinal encoding performed , after this data is scaled with Standard Scaler.
* This preprocessor is saved as pickle file.

3- Model Training :

* In this phase base model is tested . The best model found was catboost regressor.
* After this hyperparameter tuning is performed on catboost and knn model.
* A final VotingRegressor is created which will combine prediction of catboost, xgboost and knn models.
* This model is saved as pickle file.

4- Prediction Pipeline :

* This pipeline converts given data into dataframe and has various functions to load pickle files and predict the final results in python.

5- Flask App creation :

* Flask app is created with User Interface to predict the gemstone prices inside a Web Application.

## Aws Deployment using Beanstalk and codepipline services
* image for the final endpoing deployed on aws beanstalk service
![image](https://user-images.githubusercontent.com/39285876/234405912-a37fd189-3f39-452d-b565-689e71f3ef49.png)

