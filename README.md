# Parkinson On and Off Detection [Heroku Application](https://parkinson-on-off.herokuapp.com/)
### Materials and Methods

1. Data Collection and Experimental Procedure

   In this study, the data was collected from 16 different patients who were suffering from Parkinson&#39;s disease. Table 1 below shows the details about the height weight and age of all the subjects who were enrolled in the data collection procedure. Prior written approval was taken from the above subjects before enrolling them in the data extraction procedure.  For the data collection, the patients were asked to perform two courses of &quot;Walking&quot;, one when induced with dopaminergic drug and one in the normal state without the presence on any drug. The complete data extraction procedure was carried out at Department of Neurology, Haeundae Paik Hospital, Inje University, Busan South Korea. During the data extraction procedure for both the courses, the subjects were fastened with two knee worn triaxial accelerometer sensors. The triaxial accelerometer used in the study was small and lightweight in nature and had a dimension of 35mm x 35mm x 13 mm and weighed mere 13.7g. The sensitivity of the accelerometer sensor used in the data collection procedure was -8g to 8g which was capable to measure the movement metric of the subject in all the directions: anterior-posterior, mediolateral and vertical.

Table 1: Details of the Subjects

| **Subject** | **Age** | **Gender** | **Height** | **Weight** |
| --- | --- | --- | --- | --- |
| Subject 1 | 62 | Male | 153 | 63 |
| Subject 2 | 67 | Female | 155 | 58 |
| Subject 3 | 53 | Female | 161 | 61 |
| Subject 4 | 47 | Male | 163 | 57 |
| Subject 5 | 70 | Female | 151 | 39 |
| Subject 6 | 67 | Female | 154 | 50 |
| Subject 7 | 66 | Female | 157 | 59 |
| Subject 8 | 56 | Male | 172 | 59 |
| Subject 9 | 48 | Male | 174 | 74 |
| Subject 10 | 58 | Male | 179 | 81 |
| Subject 11 | 60 | Male | 162 | 65 |
| Subject 12 | 68 | Male | 168 | 63 |
| Subject 13 | 62 | Male | 174 | 60 |
| Subject 14 | 35 | Male | 182 | 78 |
| Subject 15 | 68 | Male | 147 | 41 |
| Subject 16 | 69 | Male | 158 | 56 |

2. Methodology

 ![enter image description here](https://i.ibb.co/wWhk1W5/nnn.png)

Figure 1: Complete Process of the Experiment

Figure 1 above shows the complete process for the development of the System to detect the On and Off stage of a Parkinson&#39;s patient. The complete flow of the experiment is divided into 4 different sections namely, data collection procedure, feature engineering, machine learning model training and validation, and performance evaluation. In the data collection step, the acceleration data from both right and left knee is captured using the wearable sensors and merged into the database. The next step in the process is the Feature Engineering step which can be considered as one of the most important ones. In the feature engineering step, two different kinds of features are extracted from the accelerometer data, namely, statistical features and gait parameters. In the third step machine learning models are developed by using 4 different algorithms namely, random forest classifier, support vector machine, k nearest neighbors and Naïve Bayes classifier. Finally, in the last segment a qualitative analysis was performed on the predictive power of all the 4 algorithms based on accuracy, precision, recall and confusion matrix to choose the best classifier with respect to distinguishing on and off state of patients suffering from Parkinson&#39;s disease.

The data collection was performed on 16 subjects each for two courses. During the data collection procedure, the patients were fastened with wearable devices on both the knee which were used for extracting the accelerometer data. Each course lasted for 4 – 5 minutes approximately. Both the sensors that were used in study sampled data at the frequency of 32 Hz. The complete data of all the 16 patients had 190208 samples for both the On and Off courses.

The data that was received from the accelerometer sensors contained abundant of noise. Therefore, for removing the noise a &quot;Low Pass Butterworth filter&quot; was used. The Butterworth filter of 4th order was used with a cutoff frequency of 15Hz. The order of the filter was chosen on the basis of blocking the maximum noise and the cutoff frequency was decided on the basis of exploratory data analysis.

2.1. Feature Engineering

In the feature engineering step two different sets of features were developed, namely statistical features and gait parameter features. For the calculation of features, data of each course of each patient was initially divided. Further data from each course were again grouped at the rate of 320 (10 Seconds) samples.  The calculation procedure was implemented in such a way that the features were calculated for all the samples of a course for a particular data fold of 320 samples to maintain optimum variance between the feature values.

**Table 2.** Statistical Features

| Feature | Equation | Description |
| --- | --- | --- |
| Mean |   | The mean of the feature was calculated for each subject for all the samples in each fold i.e. 320 samples. |
| Standard Deviation |   | The standard deviation of the signal is calculated for each subject for all the samples in each fold i.e. 320 samples. |
| Median Absolute Deviation |  Where,  is the median of X | The median absolute deviation was calculated each subject for all the samples in each fold i.e. 320 samples. |
| Minimum | min(X) | The minimum of the signal was for calculated each subject for all the samples in each fold i.e. 320 samples. |
| Maximum | max(X) | The maximum of the signal was for calculated each subject for all the samples in each fold i.e. 320 samples. |
| Energy Measure |   | The energy measure of the signal was calculated for each subject based on all the samples in each fold i.e. 320 samples. |
| Inter Quartile Range |   | The interquartile range was calculated on each subject by considering each fold that is 320 samples of data as the complete set. |
| Signal Magnitude Area |   | The signal magnitude area is been calculated by considering all the axis of the accelerometer and gyroscope and is calculated for each subject by considering the samples in each fold. |
| Skewness |   | The skewness for all the samples of a fold for a particular subject was calculated on the basis of the Fisher-Pearson standardized moment coefficient |
| Kurtosis |   | The kurtosis (peakedness) is calculated for individual signals. |

**Table 3.** Gait Parameter Based Feature

| Feature | Description |
| --- | --- |
| Step Length | The distance between the heel of one foot to the heel of other foot. |
| Stride Length | The distance covered between two steps, one with each foot |
| Step Time | The time taken by a person for completing one step |
| Stride Time | The time taken by a person to complete one stride length |
| Step Velocity | The speed at which a step length is covered. |
| Stride Velocity | The speed at which a Stride length is covered. |

Table 2 plotted depicts the statistical features that have been developed in the study for the detection of the &quot;On and Off&quot; state in a patient suffering from Parkinson&#39;s disease. The implementation of statistical features in the proposed study provides us with the ability to identify some discriminant features even if they lack obvious interpretability but still pose to be important ones for determining intrinsic patterns for the decision making. Table 4 on the other hand plots some gait-based features which have been derived from the course data based on the 320 samples data fold.

2.2 Machine Learning Algorithm and Evaluation Metrics

The development of machine learning algorithms for the detection of On and Off is very important to understand the patterns in the gait data of patients when in on stage and Off Stage. Moreover, the algorithms leveraged in the work will also allow us to extract the semantic information from the data collected from the tri axial accelerometer devices. Therefore, in this work multiple machine learning algorithms were developed and a comparative analysis was performed to determine the best possible algorithm based on the evaluation metrics. The initial hypothesis for the detection of the On and Off state from the gait data stated that the recall of both the two classes must be higher that 85% and the misprediction rate in both the classes must be equivalent. Table 4 depicted below shows all the hyperparameters that were used for the development of the machine learning model.

| Classifier | Specifications |
| --- | --- |
| Random Forest | n\_estimators: 500,criterion=&#39;gini&#39;_,_ max\_depth:8, min\_samples\_split=8, min\_samples\_leaf=10 |
| Support Vector Machine | kernel=&#39;rbf&#39;, degree=3, gamma=&#39;auto\_deprecated&#39;, C=1.0, tol=0.001, cache\_size=200 |
| K – Nearest Neighbors | n\_neighbors=50, weights=&#39;uniform&#39;, algorithm=&#39;auto&#39;, leaf\_size=40, p=2, metric=&#39;minkowski&#39; |
| Naïve Bayes | Gaussian |

The evaluation of the machine learning algorithms was done by considering accuracy, average recall, average precision and average f1 score as the evaluation metrics. Accuracy in the particular task allows is used to understand the overall accuracy in both the On Class and the Off Class. In the current scope of the work, the recall is being calculated for each class where it provides the information regarding the number of data samples that the model has correctly identified for a particular class. Therefore, in the study average recall is been calculated which determines the average percentage of correct predictions in each class. Also, the precision of the predictions has been derived which determines the confidence of a particular prediction to belong to a particular class. Further, for the evaluation purpose, average precision was derived which allowed us to identify the average of all the precision scores for each class. Finally, f1-score was derived which provides a weighted average between both precision and recall of each class and therefore penalizes the score for all the wrongly predicted samples of a particular class. Further during the learning procedure, the complete data of 16 subjects that is 32 courses were divided into the ratio of 70:30 where data from 22 subjects were used for the training and data of 10 subjects for the validation/testing.

3. Results

The machine learning algorithms developed in the work pursued some astounding and effective results in terms of determining the correct state of a patient suffering from Parkinson&#39;s disease. Table 5 depicted below provides a comparative analysis between all the 4 machine learning algorithms, that were used for the learning process and the evaluation metrics. The scores mentioned in Table 5 are based on the data of the validation set. From the scores, it can be duly observed that the Random Forest outperformed all the other classifiers.

**Table 5** Comparative Analsis between multiple classifiers

| Metric | Random Forest | SVM | KNN | Naïve Bayes  |
| --- | --- | --- | --- | --- |
| Accuracy | 0.9672|0.9311| 0.8672 |0.8844|
|Average Recall|0.9735|0.9225|0.8425 | 0.8667|
|Average Precision |0.96.92 |0.9358 |0.8556 |0.8533 |
|Average F1 Score |0.97.43 |0.93 |0.8502 |0.8621 |

 ![enter image description here](https://i.ibb.co/Mh0Pkzj/215.png)
Figure 2: Confusion Matrix

Figure 2 plotted above shows the confusion matrix that has been derived using the classification results of the test data. Therefore, we can see that the confusion matrix that has been derived from the classification results on the test data has full accordance with the initial hypothesis that the number of correct predictions in each class needs to be above 85% that is the recall of each class needs to be above 85% and maintain a fixed classification rate across each class.
