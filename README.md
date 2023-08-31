# Diabetes_Severity_Classification
Categorize patient data based on diabetes severity level(high, medium, low)


I'm working with a dataset of 101766 medical records that includes 71518 unique patients. The primary objective is to make diabetes Severity predictions on an individual patient level. 
Considering Readmission as Target
No readmission: Low Severity
A readmission in less than 30 days High Severity
A readmission in more than 30 days Medium Severity,  built a multiclass classification 
To accomplish this, I grouped the records by patient number, focusing on the most recent entries, and extracted aggregated features for each unique patient.
The initial challenge was the high cardinality of the diagnosis codes. My first approach involved frequency encoding, which proved ineffective. To mitigate this issue, 
I utilized ICD-9 mappings to condense the diagnosis codes into fewer, more manageable categories.
Additionally, I observed that some medication-related variables had low variance, leading me to exclude them from the analysis. 
I also partitioned the medication features into two subsets: insulin and non-insulin medications, aiming to better isolate their respective impacts on readmission rates.
Given the highly imbalanced nature of my target variable—readmission—I employed oversampling techniques to balance the classes. After these preprocessing steps, I trained an XGBoost model. The model's performance on the test set yielded the following F1-scores:
* Class 0: F1-Score of 0.86, with Precision of 0.78 and Recall of 0.95
* Class 1: F1-Score of 0.67, with Precision of 0.77 and Recall of 0.59
* Class 2: F1-Score of 0.82, with Precision of 0.81 and Recall of 0.82
While these results are promising, further improvements could be realized through additional feature engineering, categorical variable binning, hyperparameter tuning, and the use of ensemble techniques. Due to time constraints, this is as far as I've been able to do. I have added necessary comments in my file Please Find The attached File.
