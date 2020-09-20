# DAP_Project 

Note: Single file that executes all .ipynb files is Final_code_DAP_Project_Sem1

**Data Exploration and Visualisation of Payment Incentive Programs in Medicare**
This study examines the impact of different factors such as readmission rates of patients, complications in surgery, mortality rate, hospital acquired conditions (HAC), and overall patient care provided by hospital systems, on the structure of medicare payments that they receive from the U.S. government. Most recent JSON data is extracted from a government website 1 and stored in MongoDB; after pre-processing using KNNimputer in PostgreSQL. Exploratory data analysis is done on each dataset individually and results are visualised using matplotlib.pyplot, seaborn, plotly and folium. A combined analysis is carried out by integrating all these factors and the payment reduction of all hospitals registered in United States is determined. Simple Logistic Regression model failed to classify reductions in pay- ments, so Synthetic Minority Oversampling Technique (SMOTE) was used to up sample the data followed by Recursive Feature Elimination (RFE) to build a model so often and choose the best or worst feature. Accuracy of final logistic regression classifier on test set came out to be 68% with 0.66 and 0.71 precision for no reduction and reduction in payments, respectively. Although overall accuracy of model decreased after up sampling, it has better recall, f1-score, and precision for ”Yes” class which was biased. Most important classifying predictors were identified as complications in hip/knee surgery, excess readmissions for heart attack, and total HAC score, indicating that in fact, to some extent reduction in hospitals’ payments are linked to the quality of care provided by them.

Data for this project has been extracted from federal government website managed by the Centers for Medicare & Medicaid Services, 7500 Security Boulevard, Baltimore, MD 21244 at the following link :
https://data.medicare.gov/data?tool=hospital-compare&tag=linking%20quality%20to%20payment&sort=alpha&q=

**1) Hospital-Acquired Condition Reduction Program-**
The HACRP JSON data contains the metrics of hospitals, overall HAC ratings, and a reduction in payment predictor. The total HAC score has been computed by using different individual measure scores. Payments may be reduced from hospitals with a total HAC score above the 75th percentile of the total HAC score distribution. It contains information about 3,224 hospitals based on 24 parameters like provider id, hospital name, state, payment reduction, total hac score, and w z scores.

**2) Hospital Readmissions Reduction Program-**
The HRRP JSON data contains 19,300 observations of dif- ferent measure scores with 12 variables. Excess readmissions are calculated by a ratio, obtained by dividing a hospital’s predicted 30 day readmissions numbers for heart attack (AMI), heart failure (HF), pneumonia (PN), chronic obstructive pul- monary disease (COPD), hip/knee replacement (THA/TKA), and coronary artery bypass graft surgery (CABG) by the number that is predicted, depending on a conventional hospital with identical patients.

**3) Hospital Value-Based Purchasing (HVBP) – Clinical Outcomes Domain Scores-**
The HVBP JSON data comprises of 2731 medicare hospitals data with various performance measures spread across 36 columns. It contains a list of hospitals enrolled in the VBP hospital program and their performance rates and scores for the indicators of clinical outcomes.


