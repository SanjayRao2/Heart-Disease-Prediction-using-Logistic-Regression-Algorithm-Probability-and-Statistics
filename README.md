# Heart-Disease-Prediction-using-Logistic-Regression-Algorithm-Probability-and-Statistics
The objectives of this study are to determine the main risk factors for heart disease and to create a model that can accurately predict, based on a patient's demographics, whether they have heart disease or not

DATA SOURCE, DEFINITIONS & MAIN FEATURES OF DATASET
• Data was collected from the UCI machine learning repository
(https://archive.ics.uci.edu/ml/datasets/Heart+Disease).
• Research was conducted at four different medical clinics, and the Cleveland Clinic database
is used in this project for further analysis.
• The Heart Disease column has integer values ranging from 0 (no presence) to 4. The
Cleveland database experiments have focused on just trying to discriminate between
presence (values 1,2,3,4) and absence (value 0).
• The Cleveland database was "processed" in one file.
• The data set includes 303 individuals, and each patient has 14 measurements: 5 cardiac
activity measurements, 8 demographic and risk factors, and the response variable (heart
disease).
• This project focuses on the below listed eight demographic risk variables and how they
relate to heart disease.
o sex (male or female)
o age (years)
o chest pain type (typical angina, atypical angina, non-angina pain, asymptomatic)
o fasting blood sugar (high if measurement is >120 mg/dl or low if measurement is
<120 mg/dl)
o resting blood pressure (measured in mm Hg)
o serum cholesterol (measured in mg/dl)
o maximum heart rate during exercise (beats per minute) and
o exercise induced angina (yes or no)
• Refer to below snapshot for reference which indicates the study conducted at four different
clinics (the Cleveland clinic dataset is used in this project for detailed analysis):
Database
Heart Disease Category
Total
0 1 2 3 4
Cleveland 164 55 36 35 13 303
Hungarian 188 37 26 28 15 294
Switzerland 8 48 32 30 5 123
Long Beach 51 56 41 42 10 200


METHOD USED – LOGISTIC REGRESSION
Refer to below details regarding logistic regression model definition, principles, Formula of Logistic
Regression (sigmoid function) and model’s usage:
• Logistic regression is a statistical method for analyzing a dataset in which there are one or
more independent variables that determine an outcome. The outcome is measured with a
dichotomous variable (in which there are only two possible outcomes).
• In logistic regression, the dependent variable is binary or dichotomous, i.e. it only contains
data coded as 1 (TRUE, success, pregnant, etc.) or 0 (FALSE, failure, non-pregnant, etc.).
The below snapshot indicates the difference between linear & logistic regression outcomes.
• Logistic regression is a useful analysis method for classification problems, where you are
trying to determine if a new sample fits best into a category.
• Despite its name, logistic regression is more of a classification model than a regression
model. For situations involving binary and linear classification, logistic regression is a
straightforward and more effective approach. It is a widely used categorization method in
business.
• The main distinction between logistic regression and linear regression is that the range of
logistic regression is constrained to values between 0 and 1.
• Moreover, logistic regression displaces linear regression by not requiring a linear connection
between input and output variables. This is due to applying a nonlinear log transformation
to the odds ratio.
• Formula of Logistic Regression (Sigmoid function):
• Logistic regression is mainly used in:
• Medical Diagnosis
• Credit Risk Analysis
• Fraud Detection
• Marketing


DATA CLEANING
• The original dataset does not contain any column names. So, the column names were manually
inserted based on each column feature and in line with description provided in dataset.
• The 8 variables used for analysis in this project are as below:
o sex (male or female)
o age (years)
o chest pain type (typical angina, atypical angina, non-angina pain, asymptomatic)
o fasting blood sugar (high if measurement is >120 mg/dl or low if measurement is <120 mg/dl)
o resting blood pressure (measured in mm Hg)
o serum cholesterol (measured in mg/dl)
o maximum heart rate during exercise (beats per minute) and
o exercise induced angina (yes or no)
• The variables sex, chest pain type, fasting blood sugar, and exercise induced angina is converted
into factors in R for detailed analysis.
• In addition, the response variable for heart disease was initially coded as an integer (0,1,2,3,4).
The same is re-coded into ‘absence’ (0) versus ‘presence’ (1,2,3,4) as per description provided
in the dataset.
• The 303 observations in the dataset were all included for analysis because there were no missing
values in any of these observations.

 EXPLORATORY DATA ANALYSIS
5.1 Pervasiveness of Heart Disease in Different Age of Non-patients & Heart disease-patients
• The below histograms for presence and absence of heart disease have different distribution
shapes which indicates that age does have a relationship with heart disease.
• These graphics indicates that there are more older people with heart disease than younger
people with heart disease.


REQUIREMENTS FOR LOGISTIC REGRESSION MODEL
The below listed dataset requirements for logistic regression were verified before proceeding with
detailed statistical analysis:
• The dependent variable should be dichotomous, meaning it should take on one of two values
(e.g., 0 or 1, yes or no, true or false). The independent variables (also known as predictors or
features) can be continuous, categorical, or a combination of both. The dependent variable in
this dataset is binary (i.e. Absence-0, Presence-1).
• The sample size should be large enough to ensure that the logistic regression model is stable
and reliable. In general, there should be at least 10 observations for each predictor variable. In
this dataset, there are total 8 predictor variables used. In view of this, the 303 nos. of observations
in this dataset can be considered as decent / adequate.
• The dataset should be free of missing data, outliers, and other errors that could bias the results.
All the observations available in this project dataset are free from missing data.
• The independent variables should be independent of each other, meaning that there should be
no multicollinearity (i.e., high correlation) between them. The correlation was performed for all
the 8 independent variables in order to confirm the collinearity among those variables and it was
observed that, that the predictor variables used for further analysis are not colinear.
• The dataset should be balanced, meaning that the proportion of observations in each category
of the dependent variable should be roughly equal. There are 164 observations in the dataset
without heart disease and 139 observations with heart disease patients. Hence, we can consider
that the proportion of observations of non-patient v/s heart-patient is roughly equal.
Subsequently, the QQ plots were generated and verified to check the distribution of various
variables such as, age, resting blood pressure, serum cholesterol, max heart rate during
exercise. It was observed from this graphs that, the data was roughly normally distributed. refer
to below plots for quick reference.


STATISTICAL ANALYSIS RESULTS – INTERPRETATION
The correlation was performed for all the 8 independent variables in order to confirm the collinearity
among those variables and it was observed that, that the predictor variables used for further
analysis are not colinear. Refer to below snapshot for quick reference.
7.1 Model Analysis Results – Training Dataset
The logistics regression was performed in R using ‘glm’ function which is part of the "stats" package.
• All 8-predictor variables (risk factors) were used for the initial analysis.
• The data was split in to 80% ~ 20% for model training and testing respectively.
• The logistic regression was performed on 80% training dataset. Refer to below snapshot
which indicates the analysis results.
• It can be seen that, the p-value for age, serum cholesterol & fasting blood sugar is higher
than the acceptable significance level of 0.05 which indicates that, these 3-predicrtor
variables are not related (not contributing) for ‘heart disease’ dependent variable prediction.
• This result is interesting since based on the visual data analysis above, it was noticed that,
the age is contributing significantly for the heart disease prediction (i.e. it was observed that,
the heart disease cases were reported more in the older people than young people).
However, based on the below results from logistic regression model; it is clear that, the age
is not the contributing factor for the heart disease dependent variable.
In continuation with above analysis results, the 3-predictor variables (i.e. age, serum cholesterol &
fasting blood sugar) which were found not contributing for heart disease prediction were removed
from the further analysis.
Subsequently, the logistic regression was performed again on the 80% training data. Find below
analysis results for quick reference.
All the remaining independent variables p-value is below significance level of 0.05 as it can be seen
from the below analysis results.

Receiver Operating Characteristic (ROC) Results
Refer to below “Receiver Operating Characteristic” plot:
• The ROC plots the model’s Sensitivity (ability to correctly predict people with heart disease
as having heart disease, equivalent to the true positive rate) v/s
Specificity (ability to correctly predict people without heart disease as not having heart
disease, equivalent to the true negative rate).
• The threshold value for model is 0.5, so the observations with predicted probabilities < 0.500
will be classified as not having heart disease and observations with predicted probabilities
> 0.500 will be classified as having heart disease.
• The specificity is observed as ‘0.811’ and sensitivity of the model is reported as ‘0.778’.
• The ‘Area Under Curve (AUC)’ value is “0.7944” which indicates that, the model will correctly
predict a heart disease diagnosis from a negative diagnosis 79.44% of the time when new
dataset / observations are used with this model.

CONCLUSION
• The model's output may be used to identify whether someone has heart disease based on
the various risk factor (predictor variables used in above statistical analysis) parameters or
not.
• There are certain predictions in this model that are uncontrollable, but there are others that
might be utilized to affect someone's lifestyle decisions.
• The logistic regression model showed to be useful, given the accuracy rate of 0.80 on the
test set. Heart disease was found to be significantly predicted by sex, the kind of chest
discomfort, resting blood pressure, the highest heart rate attained during activity and
exercise-induced angina.
• More research is necessary since the distribution of chest pain type did not match the known
signs of heart disease.
• Age, cholesterol, and fasting blood sugar were determined to be unimportant factors and
were therefore excluded from the final model.
