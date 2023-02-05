# Hospital Data Analysis

Did you know that the first hospital in the US was established in 1751? It was called the Pennsylvania Hospital and was founded in Philadelphia by Benjamin Franklin and Dr. Thomas Bond. The founders created this hospital to serve all people. It was the first hospital in the colonies and set the standard for modern American hospitals. 

Today, there are thousands of hospitals in the US, serving millions of patients each year and playing a critical role in keeping communities healthy and strong.

In this article, we'll be exploring the world of hospitals and how they operate. From the laboratory tests they perform to the way they treat different ethnicities. We'll take a look at what hospitals are doing right and what areas may need improvement.

## The Data

The dataset represents 10 years (1999 – 2008) of clinical care for 130 Hospitals in the US. 
 
The dataset can be found [here.](https://www.kaggle.com/code/iabhishekofficial/prediction-on-hospital-readmission/data?select=diabetic_data.csv)

The purpose of this project is to provide any helpful insight as a Data Analyst at a hospital. 

## Insights

1.	Majority of patients (> 5000) are staying in the hospitals on average 7 days or less. 

2.	The top 3 medical specialties performing the most procedures are Obstetrics, Thoracic surgery, and Proctology. 

3.	Hospitals are conducting similar amounts of laboratory tests for multiple race groups.

4.	The more lab procedures a patient undergoes, the more days they spent at the hospital.

5.	Two patients underwent more than 90 lab procedures, and neither was readmitted or had diabetes.

## The Analysis

#### 1.	What is the allocation of hospital stays in terms of time?

With the use of a histogram to represent the data, we can categorize patients based on the duration of their hospital stay.

![image](https://user-images.githubusercontent.com/120342460/216101986-28e52e55-9624-435b-804b-d2caeac23827.png)

According to the histogram, it appears that the majority of patients, around 5000 or more, have hospital stays of 7 days or less. This could be seen as positive as it allows for a higher turnover rate and accommodates more patients seeking treatment.

<img src="images/histogram.health.png?raw=true"/>

#### 2.	Which medical fields have the greatest average number of procedures performed?

It is worth mentioning that in order to find the medical specialties with the highest average number of procedures performed, it is necessary to use aggregate functions such as the average. The use of the HAVING clause allows for filtering by this average, in this case by selecting a value greater than 2 procedures.

![image](https://user-images.githubusercontent.com/120342460/216172738-3038a6cd-f385-4292-ba79-a339fdf9470f.png)

According to the data, the three medical specialties with the highest number of procedures performed are Obstetrics, Thoracic Surgery, and Proctology.

<img src="images/num_procedures.health.png?raw=true"/>

#### 3.	What is the average number of laboratory procedures performed among different races?

In order to determine the average number of laboratory procedures performed by race, we need to utilize the JOIN clause to combine data from two separate tables within the database. The health table holds the health information for each patient, while the demographics table includes information such as race, gender, and age for each patient.

![image](https://user-images.githubusercontent.com/120342460/216175463-2f684ca8-7d02-4188-88af-0afd923b42c3.png)

As we can see, hospitals are carrying out similar amount of laboratory tests for different races. This is an indication that hospitals are treating all races fairly.

<img src="images/lab_procedures.health.png?raw=true"/>

#### 4.	What is the relationship between the number of lab procedures and time spent at the hospital?

To better understand the number of lab procedures, we need to determine the MIN, AVG, and MAX.

![image](https://user-images.githubusercontent.com/120342460/216786303-e1b8197c-be9a-4e7a-b74a-b03dd15669ff.png)

- MIN = 1
- AVG = 43
- MAX = 99 

To answer this question, we used the CASE WHEN syntax. 
In the query below, we categorized the number of lab procedures by few, average, and Many. 

- Few = 0 – 24 lab procedures
- Average = 25 - 54 lab procedures
- Many = 55 or more lab procedures

![image](https://user-images.githubusercontent.com/120342460/216785860-3cc318ed-beb3-4b02-b325-bf87863e2cb7.png)

We can see that the more lab procedures a patient undergoes, the more days they spent at the hospital. 

Patients who have less than 25 procedures tend to stay on average 3 days at the hospital. On the other hand, patients who have more than 55 procedures stay on average 5-6 days. 

<img src="images/hospitaldays.health.png?raw=true"/>

#### 5.	Summary of top 20 patients who have received the highest number of medications and undergone the most lab procedures.

The CONCAT syntax allows us to merge certain data and present a summary for each patient. This query enables us to view the patient's race group, readmission status, number of medications, lab procedures, and whether they’re diabetic or not. 

![image](https://user-images.githubusercontent.com/120342460/216841711-45a5381e-83b7-4fb0-a0f4-0e2888469222.png)

The top two patients on the list underwent more than 90 lab procedures and received an equal number of medications. Neither was readmitted or had diabetes.

The third patient on the list underwent 90 lab procedures and was diabetic.

Further investigation is required to better understand the top three patients who underwent a significant amount of lab procedures.

<img src="images/summary.health.png?raw=true"/>

To focus on the top three patients, we aim to determine the number of diagnoses they have.

![image](https://user-images.githubusercontent.com/120342460/216841719-860c95ec-10e2-4b85-9f3c-2929aed673ef.png)

The top two patients also have the same number of diagnoses. To go deeper, the next step would be to examine the type of medications and illnesses. However, for this analysis, this information is valuable.

<img src="images/diagnoses.health.png?raw=true"/>

## Closing Remarks

America’s hospitals have always been at the forefront of caring for the sick and injured, ever since the first one was established in 1751. Today, they continue that tradition by ensuring they remain as open and welcoming to new ideas as they can.

If you found this information helpful and would like to stay updated with more insightful content like this, be sure to follow me on [LinkedIn!](https://www.linkedin.com/in/vaniacortez/)



