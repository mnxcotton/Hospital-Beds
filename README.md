# Hospital Bed Management

## Background: 
Many hospitals are often dealing with finding enough hospital beds for the flux of patients who are admitted into the institution. According to online articles from NPR and JAMA Network, many hospitals in the U.S. in recent years face hospital bed shortage. A recent example that magnified this issue is from the COVID-19 pandemic. 

This project uses simulated hospital datasets to explore hospital activity and apply machine-learning methods to bed-availability and patient-length-of-stay questions.

## Data Source and Dataset
The datasets are from Kaggle’s [Hospital Beds Management dataset](https://www.kaggle.com/datasets/jaderz/hospital-beds-management), which represents a simulated medium-sized hospital.

- `Patients.csv`: Patient demographics, arrival and departure times, and service satisfaction scores.
- `Services_weekly.csv`: Weekly bed availability, admissions, and refused patients, grouped by hospital service.
- `Staff.csv`: Staff identifiers and job-position information.
- `Staff_schedule.csv`: Staff attendance information by week.

The patient arrival and departure fields were converted to datetime values to calculate length of stay. Staff schedules were aggregated by week, service, and job position, then joined with weekly service data. The resulting data was pivoted to create numeric staffing features; missing values were filled with zero. The predictive data was split into training and testing sets, using an 80/20 split.

## Research Objectives:
- Explore datasets on patients, hospital services, bed allocation, and staffing.
- Examine patterns in weekly hospital activity and patient characteristics.
- Predict hospital bed availability using a Random Forest model.
- Explore whether patient age and satisfaction can be used to predict length of stay.
- Identify which features are most important to the bed-availability model.


## Methods
- **Exploratory analysis:** Principal component analysis (PCA) was applied to standardized weekly activity features and reduced to two components for visualization.
- **Clustering:** K-Means clustering grouped patients into three clusters using age and satisfaction.
- **Length-of-stay model:** A neural network used patient age and satisfaction to predict length of stay.
- **Bed-availability model:** A Random Forest model used weekly patient activity, staffing, and related features to predict available beds.
- **Evaluation:** Predictive performance was assessed on the test set using mean squared error and, where reported, R-squared. Random Forest feature importance was also examined.

Analyses were performed in Python using Pandas, Scikit-learn, TensorFlow, Matplotlib, and NumPy.


## Limitations
The patient clustering also showed patterns connecting age and satisfaction, but these patterns should not be interpreted as causal.

The results are based on simulated hospital data and the features included in the analyses. The length-of-stay model used only age and satisfaction, which were not sufficient for useful prediction in this analysis. Additional variables, such as diagnoses, admission urgency, and more detailed staffing information, could be explored in future work. The reported model scores should also be interpreted in light of the dataset and the project’s train-test evaluation.

## Findings


## Note
This repository is a portfolio summary of a completed academic project. The full source code and dataset are not included. 
© 2026 Maria Nguyen. Academic portfolio work. Please do not submit or represent this work as your own.
