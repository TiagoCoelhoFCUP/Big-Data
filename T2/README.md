# ICU Stays Duration Predictor

As part of the BDCC course we were provided with the file EVENTS.csv.gz which contains records of several patients collected during their stay in the intensive care unit. The main objective of this work is to create a machine learning model capable of predicting the length of stay given the records collected during that stay.

Due to the high dimensionality of the file in question, I decided to upload the file to a Google Cloud Storage BigQuery table, which is able to support files of this size. This way, I can do some pre-processing through SQL queries, extract those views and work with smaller files:

The table "EVENTS_PER_ITEMID" contains information regarding the number of measurements made for each item in the original file

![image](https://user-images.githubusercontent.com/13381706/163415376-66ce4443-d009-46d7-9e2b-9304e927d84e.png)

The table "N_PATIENTS_PER_N_STAYS" has the distribution of patients by the total number of stays in the intensive care unit

![image](https://user-images.githubusercontent.com/13381706/163415540-b8ddee28-dcb9-4c74-9bd2-e38e3a8c8757.png)

 The table "ICUSTAYS" contains information regarding the stay itselft, namely the stay duration
 
 ![image](https://user-images.githubusercontent.com/13381706/163415813-f62ee0bf-d7ee-491c-a864-f88bbf43a53d.png)
 
 The "DATA" table has the minimum, maximum and average value of a given item for a given stay
 
 ![image](https://user-images.githubusercontent.com/13381706/163416141-817f8772-75a2-446a-b500-c51afe707ffa.png)

Based on these tables I sarted to pre-process the data and later trained my candidate models (LogisticRegression, KNN, DecisionTree, SVM, NaiveBays and a stacking ensemble model of the previous models) by converting the problem into a binary classification: "Short Stay" (<10 days) and "Long Stay" (>= 10 days).
The ensemble model was revealed to be the best performing one out of all of them, with an almost 92% accuracy rate. This was the model I used to make the final predictions.

![image](https://user-images.githubusercontent.com/13381706/163416973-b24ddc27-bea5-4043-928c-0c63a8d5a86b.png)


