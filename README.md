# PISA-2018-Analysis
This project aims to use the power of machine learning algorithms to analyse teaching strategies indicators performance.  This research will show the impact of different teaching strategies and how they affect the model performance. 

Note: This is just a summarise version of the entire project.

# Result
The dataset used for my model is the PISA 2018 assessment – the seventh since the programme’s inception, which comprises the average score in the three domains PISA 2018 assessed: reading, mathematical, and scientific literacy

# Analysis

<img width="940" height="434" alt="image" src="https://github.com/user-attachments/assets/c61fa530-2c3b-4c31-9bbe-c18a5123a56a" />
Top 10 2018 PISA Participating Countries
Data visualisation was done to understand how each participating country performed in relation to the selected variables. The top 10 countries were visualised using a histogram. The distribution of key variables was understood because it provided insights into the characteristics of the data and informed decisions on further analysis.

<img width="940" height="511" alt="image" src="https://github.com/user-attachments/assets/cc0e1d66-39dd-4114-8dc1-bd5a60f881f8" />

Top sponsored countries

<img width="940" height="511" alt="image" src="https://github.com/user-attachments/assets/c325b5d1-8d35-495e-b9f3-0a6820a31697" />

Top countries with highest Government funding

Kazakhstan and Australia top the highest government funding plot with each country taking 50,000 unit and 35,000 units. This plot shows the investment each country is willing to support educational initiatives, infrastructures and resources. This plot will assist in understanding the quality of teaching strategy that each country can afford and implement.
Above image shows a unique statistic as many of the top countries with government funding are not topping the sponsorship list. This might mean sponsorship is not generally acceptable or seen as a means of improving educational performance by many of the top countries.

<img width="940" height="509" alt="image" src="https://github.com/user-attachments/assets/753bc6f9-f012-47c7-b6d5-d60d4df42684" />

Among the top countries that have shown massive positive sign is Kazakhstan and it is expected to see them performing very well in average score but this image reveals where they are facing challenges. They have huge number of students skipping classes which may result in poor performance. It is important to understand that good performance is a shared responsibility between teachers, students and those responsible for the institution.

<img width="940" height="499" alt="image" src="https://github.com/user-attachments/assets/0e7f566d-56fe-4c13-a0ae-515255946ea4" />

Above image is the assessment score distribution among the three subjects: Mathematics, Reading and Science. This chart shows more distribution of score around 500 marks for all subjects. We can also see Reading taking a higher frequency than others.  Generally, the three subjects have similar or close range of score among each other. 

<img width="975" height="673" alt="image" src="https://github.com/user-attachments/assets/34966510-975e-472a-908d-76157070a071" />

Above is a continuation of the process of identifying the most important features that will contribute to the model performance. This research will try to include the negative correlated features and the positive correlated features during model training and then observe the performance of the model.

<img width="940" height="840" alt="image" src="https://github.com/user-attachments/assets/5f14d506-a472-4add-8f93-821366a30a26" />

Above is used to enable the visualisation of the relationship between each pair of variables in our dataset. It combines both histogram and scatter plots, providing an overview of the dataset's distributions and correlations. From the scatterplot matrix below, the distribution was classified into good and bad. The blue dot denotes bad while the orange dot represents good.


# Machine Learning Model

# Decision Tree Model

<img width="940" height="310" alt="image" src="https://github.com/user-attachments/assets/97e09caa-ed45-4705-a435-07bca90e54a7" />

Above contains param_grid: defines the hyperparameters to be tested during the grid search. The pipeline defines the scaler and decision tree classifier. The CV=5 means 5-fold cross validation will be use. The features will be divided into 5, the training set will take 4 while the remaining will be for testing. n_jobs=-1 will unable the usage of all CPU cores available, just to hasten the search process.

		Precision	Recall	F1-Score	Support
Feature A	Bad	0.69	0.70	0.70	160
	Good	0.65	0.64	0.65	140
	Accuracy: 0.67, Cross-validation:0.72, Weighted Avg: 0.67
					
Feature B	Bad	0.70	0.63	0.66	160
	Good	0.62	0.69	0.66	140
	Accuracy: 0.66, Cross-validation: 0.73, Weighted Avg: 0.66
					
Feature C	Bad	0.75	0.69	0.72	160
	Good	0.67	0.74	0.70	140
	Accuracy: 0.71, Cross-validation: 0.76, Weighted Avg: 0.71
  
Above table is the performance of Decision Tree using three different feature set to predict the outcome of academic performance of countries in PISA 2018. Feature C enhanced the model performance ahead of other Feature set.

<img width="940" height="626" alt="image" src="https://github.com/user-attachments/assets/bd029f32-fe3a-460a-a9d1-65b978741e9f" />

Above image, the Y-axis is named True Labels which is the actual classes while the X-axis named Predicted Labels represents the predicted classes from the classifier. 
For the matrix elements in Figure 17, the top-left (True Negative), with elements (110) represents the number of occurrences that were actually 'Bad' and were correctly predicted as 'Bad'. The top-right (False Positive), with element (50) represents the number of occurrences that were actually 'Bad' instead were wrongly predicted as 'Good'. The bottom-left (False Negative), with element (37) represents the number of occurrences that were 'Good' instead were wrongly predicted as 'Bad'. The bottom-right (True Positive), with element (103) represents the number of instances that were actually 'Good' and were correctly predicted as 'Good'

# Randomforest Model

<img width="700" height="281" alt="image" src="https://github.com/user-attachments/assets/a4acca25-233b-4305-9808-eb4e38ae6706" />

Fig 19 n_estimator is the count of trees in the forest. The more the trees means more performance but also it demands high computational cost. max_depth will be 10, 20 level while min_samples_split means the grid will test the model using 2, 5, 10 for splitting purpose. This also helps in prevent overfitting.
	Performance
Classification	Precision	Recall	F1-Score	Support
Feature A	Bad	0.77	0.68	0.72	160
	Good	0.68	0.76	0.72	140
	Accuracy: 0.72, Cross-validation: 0.75, Weighted Avg: 0.73
					
Feature B	Bad	0.79	0.65	0.71	160
	Good	0.67	0.80	0.73	140
	Accuracy: 0.72, Cross-Validation Score: 0.79, Weighted Avg: 0.73
					
Feature C
	Bad	0.87	0.63	0.73	160
	Good	0.68	0.89	0.77	140
	Accuracy: 0.75, Cross-Validation Score: 0.81, Weighted Avg: 0.78
  
Above table Result of Random forest with feature A, B, C
Table  shows Feature C performed better than others. The accuracy of feature set C is at 75% with Weighted avg of 78%.

<img width="940" height="648" alt="image" src="https://github.com/user-attachments/assets/0bb0d865-509f-43ea-b857-90da11babb2c" />

For the matrix elements in above image, the top-left (True Negative), with elements (101) represents the number of instances that were actually 'Bad' and were correctly predicted as 'Bad'. The top-right (False Positive), with element (59) represents the number of occurrences that were actually 'Bad' instead were wrongly predicted as 'Good'. The bottom-left (False Negative), with element (15) represents the number of occurrences that were actually 'Good' instead were wrongly predicted as 'Bad'. The bottom-right (True Positive), with element (125) represents the number of instances that were actually 'Good' and were correctly predicted as 'Good'

<img width="940" height="532" alt="image" src="https://github.com/user-attachments/assets/f5d88003-a344-4dc8-bbfa-39ff5d4b11ac" />

Above image is the result of the contribution of Feature C. It shows each teaching strategy contributed to the outcome of academic performance in PISA 2018. The aim of this plot is for the policy makers to know the teaching strategy to prioritise when dealing with academic performance.


# Classification Report Discussion
To achieve the aims and objectives of this research, three feature set is selected and applied on three models. The result of the classification report shows the following:
Feature A: This set contains all the teaching strategies extracted from the data analysis. This research applied this feature on the three models and the F1-score reads: KNN 65% for Bad, 70% for Good, Random Forest 72% for bad 72% for Good, Decision Tree 70% for Bad 60% for Good.

Feature B: This set contains all teaching strategies except for CLSIZE and Sponsorship. This is done because this research would like to observe the impact of the absence of these two teaching strategies on the models. There F1-score reads: KNN 68% for Bad 71% for Good, Random Forest 71% for Bad 73% for Good, Decision Tree 66% for Bad 66% for Good.

Feature C: This set contains all teaching strategies except for Sponsorship. This set is necessary because during analysis Sponsorship shows a completely different countries are the ones using this strategy not many of the high performing countries. F1-score reads: KNN 68% for Bad 77% for Good, Random Forest 73% for Bad 77% for Good, Decision Tree 72% for Bad 70% for Good.
Overall, Random Forest shows a good performance and was able to analyse properly how each teaching strategy affect academic performance.


# Conclusion
Effective teaching strategies are important in shaping student learning experiences and academic outcomes. Understanding the contributions of some of the strategies may policymakers in low-performing countries in PISA assessment to come up with strategic plans that can aid their education system. Through Machine Learning models, a comparative analysis was carried out to investigate teaching strategies in high-performing countries. This study revealed that k-Nearest Neighbors (KNN), random forest, and decision tree can be used to classify the average score of students into good or bad with minimal false positives and false negatives.


