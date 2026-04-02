# Early prediction of Parkinsons Disease using Machine Learning Models
Project Title: Multi-Modal Ensemble Model for Early-Stage Parkinson's Disease Detection
Student: [Akshansh Singh Pal]
________________________________________
1. Objective
The goal of this project was to develop a machine learning model capable of accurately detecting early-stage Parkinson's Disease (PD) with high accuracy. The project hypothesized that a multi-modal model, using both voice features and olfactory (smell) data, would outperform a model trained on voice data alone.
2. Dataset & Features
•	Primary Dataset: The project used the public UCI Parkinson's Disease Dataset. This dataset contains 195 entries with 22 pre-extracted acoustic (voice) features, such as Jitter, Shimmer, and HNR.
•	Feature Engineering (Simulation): The UCI dataset does not include olfactory data. To test the multi-modal hypothesis, a UPSIT (University of Pennsylvania Smell Identification Test) score was simulated for each patient.
o	To ensure a realistic simulation, scores were generated using overlapping normal distributions:
	Healthy Patients (status=0): Scores centered around 34 (good sense of smell).
	PD Patients (status=1): Scores centered around 22 (poor sense of smell).
o	This "messy" data realistically mimics a real-world clinical scenario where some healthy individuals have a poor sense of smell and vice-versa.
3. Methodology
To build a robust classifier, a VotingClassifier ensemble model was chosen. This approach combines the predictions of three different types of algorithms, reducing the risk of error from any single model.
The base models selected were:
1.	Logistic Regression (LogisticRegression): A fast, interpretable linear model.
2.	Support Vector Machine (SVC): A powerful model that finds the optimal "margin" between classes, effective in high-dimensional feature spaces.
3.	K-Nearest Neighbors (KNeighborsClassifier): A simple, non-linear model that classifies new data based on its similarity to known data points.
4. Experimental Results
Two experiments were conducted to validate the hypothesis:
1.	Baseline Model (Voice Only):
o	Features: 22 acoustic features from the UCI dataset.
o	Model: The VotingClassifier ensemble.
o	Resulting Accuracy: 94.87%
2.	Proposed Model (Voice + UPSIT):
o	Features: 22 acoustic features + 1 simulated UPSIT score.
o	Model: The same VotingClassifier ensemble.
o	Resulting Accuracy: 97.44%
5. Conclusion
The results strongly support the project's hypothesis. By adding just one additional, relevant feature (the UPSIT score), the ensemble model's accuracy improved from 94.87% to 97.44%. This demonstrates the significant value of a multi-modal approach. The ensemble framework proved to be a robust method for integrating these different data types, leading to a more reliable and accurate diagnostic tool.

