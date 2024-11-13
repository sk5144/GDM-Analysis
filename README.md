
# Identify risk factors for Gestational Diabetes

#### What is Gestational Diabetes in medical terms?
Gestational diabetes is a form of diabetes that occurs during pregnancy. Diabetes, in this context, refers to elevated blood glucose levels, commonly known as blood sugar. Excess glucose in the bloodstream can be detrimental to both the mother and the developing baby. Typically, medical professionals diagnose gestational diabetes between the 24th and 28th week of pregnancy.

The scope for the Data Analysis of the Gestational Diabetes Dataset:
* Gain insights into the dataset's structure, including the number of sheets, rows, and columns.
* Decode the significance of each column within the dataset.
* Examine the numerical metrics and distribution profiles of each individual column.
* Investigate the interplay and connections among various columns to uncover relationships and correlations.
To accomplish this, we initially had to make the data is concise, meaningful, and ensure the data was free of mistakes. I use Power Query for data wrangling.

### Data Preparation
In this study, we analyzed a dataset comprising 259 columns and 600 rows, investigating various parameters related to different aspects.
1.Gestational Diabetes (GDM)
2.Glucose Challenge Test (GCT)
3.Oral Glucose Tolerance Test (OGTT)
4.Vitamin D Levels (25OHD)
5.Depression, Anxiety, and Stress Symptoms (DASS)
6.Systolic Blood Pressure (BP)
7.Diastolic Blood Pressure (BP)
8.Hemoglobin A1c (HbA1c)
These parameters provide insights into various factors related to gestational diabetes and maternal health.

### Data Cleaning
In the data cleaning process, we systematically refined the dataset and prepared it for analysis. We applied several rules to decide which columns to keep and which to remove:
1.Duplicates: We removed duplicated columns, keeping only one of each set of identical columns. For example, columns related to checking for Vitamin D deficiency were reduced to a single representative column.
2.Derived Columns: Columns that could be calculated from others were eliminated. For instance, multiple columns based on the 1-hour glucose test were condensed into a single '1h glucose' column.
3.Null or "No" Values: Columns with predominantly null or "No" values were removed. Conditions or diagnoses that were not detected in the dataset were excluded.
After the initial cleaning, we had 124 columns remaining. In the second stage, we delved deeper to assess the relevance of these columns to GDM and the health of the mother. After thorough evaluation, some columns and rows were identified as irrelevant to the study.

In the final stage of data cleaning, we focused on handling outliers, null values, and unique entries. Lab values and blood markers with null values were preserved for later calculations. Columns indicating medical diagnoses stored as "Yes/No" were replaced with "NR" for "Not Recorded" in the case of null values. Test or procedure columns with null values were set to "No" to indicate non-administration.

We standardized the Ethnicity column to match the provided codes and cleaned columns that duplicated data already found in dedicated separate columns.

Ultimately, after these cleaning stages, we retained 89 columns and some rows for further research and comparative analysis in Tableau.

#### Key Findings:
* The majority of patients belonged to the White race, with very few from other racial backgrounds.
* There were far fewer records for women diagnosed with gestational diabetes (GD) compared to those without GD.
* Records concerning fetal and maternal complications often lacked information or showed negative results.
* Columns related to glucose values in GD cases had a high number of missing entries.

#### Challenges:
* Data entry errors were a common issue.
* Most columns had categorical data.
* Many visit 3 records were missing due to patient transfers or discharges after delivery.
* Redundant columns were also deleted to streamline the dataset.
* Many columns were removed due to more than 60% null values.

### Analyzing Data Using Tableau

#### 1. Understanding Subset Representation
* In our dataset of 565 patients, 74 had GDM, which is a smaller representation.
* Comparing the much larger group without GDM to the smaller GDM group numerically could lead to inaccurate conclusions.
* However, a subset can still provide meaningful insights, and we found that GDM-diagnosed patients had a higher percentage of pregnancy-related complications.
  
![Screenshot 2023-10-10 153603](https://github.com/KrishnaVidja/GDM_Tableau/assets/106781881/3759114b-060c-47cf-9b44-e24689527d72)

#### 2. Assessing Patients' Health During the First Visit
* Women with high blood pressure (BP) had nearly double the risk of being diagnosed with GDM compared to those with normal BP (8% vs. 4.8%).
* Having a BMI over 30 during the initial visit increased the likelihood of GDM diagnosis by 1.5 times.
* Individuals with elevated HBA1C values during their first visit were ten times more likely to develop GDM.
* Patients with low Vitamin D levels had a 7% higher likelihood of being diagnosed with GDM. These physical health indicators showed strong correlations with later GDM diagnosis, although causation couldn't be definitively established due to the lack of insight into individual risk factors.
* Hypercalcemia during pregnancy, although uncommon, can result in significant health risks for both the mother and the baby. The incidence of hypercalcemia was three times higher among patients with GDM (19% vs. 6%).

![Screenshot 2023-10-10 153634](https://github.com/KrishnaVidja/GDM_Tableau/assets/106781881/0c43c8fc-4489-4672-a43d-0558b7f098fe)

#### 3. Evaluating Liver and Kidney Health
* Patients diagnosed with GDM exhibited a greater prevalence of liver damage indicators, with 33% of them showing signs of liver injury or disease, while only 11% of those without GDM displayed such signs.
* Elevated levels of Creatinine and Albumin, early markers of pregnancy-induced hypertension, were observed in 6.7% of GDM patients compared to 3.1% of non-GDM patients. This suggests a higher risk of developing conditions like pre-eclampsia among those with GDM.
* An increased presence of C-Reactive Protein (CRP), a marker of low-grade inflammation, was found in 47% of GDM patients in contrast to 36.5% of non-GDM patients. This elevation in CRP levels may elevate the likelihood of fetal growth restrictions and complications during neonatal development in GDM-affected pregnancies.
  
![Screenshot 2023-10-10 153705](https://github.com/KrishnaVidja/GDM_Tableau/assets/106781881/b0297c9d-bc59-4f41-84f4-1087dae635c8)

#### 4. Complications During Labor and Birth
* Higher Rate of C-Sections: In pregnancies with GDM, a significant 47.3% of cases required a Cesarean section (C-section) for delivery. This rate was noticeably higher than the 31.03% of pregnancies without GDM that needed C-sections. This means that having GDM made C-sections 1.5 times more likely for expectant mothers. C-sections are surgical deliveries and are often recommended when there are complications or risks during labor.
* Increased Emergency Procedures: Patients with GDM faced a higher likelihood of needing emergency procedures during labor. About 17.6% of pregnancies with GDM required these procedures, whereas only 8.8% of pregnancies without GDM experienced such emergencies. This means that the presence of GDM doubled the chances of requiring immediate medical interventions during childbirth.
* Higher Risk Pregnancy: When GDM was diagnosed in a patient, their pregnancy was 1.5 times more likely to be categorized as high-risk. Approximately 19% of pregnancies in the GDM group fell into the high-risk category, compared to 11% of pregnancies in the non-GDM group. High-risk pregnancies typically involve increased medical monitoring and intervention due to potential complications, making them more challenging to manage.
  
![Screenshot 2023-10-10 153747](https://github.com/KrishnaVidja/GDM_Tableau/assets/106781881/e60068bf-7eea-45c9-a3b0-5a5b3870ae2a)

In summary, regardless of whether they had Gestational Diabetes, individuals with a high BMI and poor cardiovascular fitness experienced less favorable outcomes. Nevertheless, those diagnosed with Gestational Diabetes exhibited a higher percentage of individuals at risk of heart disease and pregnancy complications. This suggests that insulin resistance and elevated blood glucose levels are likely the key indicators of overall health during pregnancy.
