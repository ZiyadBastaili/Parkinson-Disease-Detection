# Parkinson Disease Detection [Flask Application](https://github.com/ZiyadBastaili/Parkinson-Disease-Detection)

### What is Parkinson’s disease (PD)?
It is the most common neurodegenerative disease after Alzheimer’s disease, with an estimated incidence of 20/100,000 and a prevalence of 150/100,000. It is characterized by speech and voice disorders.
### Causes of Parkinson’s disease?
It causes significant morbidity and results in a shortened lifespan. A major problem for researchers and clinicians is that by the time patients' symptoms become apparent enough for them to seek help, about 70-80% of their dopaminergic neurons may already be dead.
### The main challenges in treating Parkinson’s disease?
are therefore to protect the dopaminergic neurons so that either the disease is prevented or its slow progression and to provide early treatment to "save" the neurons at risk.
## Objective
The purpose of this study is to analyse and train the voice signals, extract the characteristics, train the classification models separately according to the selected characteristics method and the hyperparameter method, and examine the performance and accuracy of each model according to the method used. first digital bank in the world.
1. Examine the best classifier using the Filter method:
   * VarianceThreshold
   * Pearson correlation


2. Based on the feature selection method, compare the number of selected variables based on:
   * VarianceThreshold
   * Pearson correlation


3. Consider the effects of the hyperparameter method on the performance of the following classifiers:
   * Logistic Regression
   * RandomForestClassifie


## Architecture du système
 ![enter image description here](/static/assets/img/4.jpeg)

## source
 ![enter image description here](/static/assets/img/source.PNG)

## Dataset Information
This dataset is composed of a range of biomedical voice measurements from 31 people, 23 with Parkinson's disease (PD). Each column in the table is a particular voice measure, and each row corresponds one of 195 voice recording from these individuals ("name" column). The main aim of the data is to discriminate healthy people from those with PD, according to "status" column which is set to 0 for healthy and 1 for PD. The data is in ASCII CSV format. The rows of the CSV file contain an instance corresponding to one voice recording. There are around six recordings per patient, the name of the patient is identified in the first column.For further information or to pass on comments, please contact Max Little (littlem '@' robots.ox.ac.uk). Further details are contained in the following reference -- if you use this dataset, please cite: Max A. Little, Patrick E. McSharry, Eric J. Hunter, Lorraine O. Ramig (2008), 'Suitability of dysphonia measurements for telemonitoring of Parkinson's disease', IEEE Transactions on Biomedical Engineering (to appear).

## Attribute Information
The dataset contains 22 features extracted from 31 people, of which 23 suffered from PD. As shown in Table 1, each column denotes a particular voice feature, and each row corresponds to one of 195 voice recordings from these individuals. The dataset was created by Max Little of the University of Oxford in collaboration with the National Centre for Voice and Speech, Denver, Colorado.

 ![enter image description here](/static/assets/img/3.png)

## ABOUT THE PROJECT
 ![enter image description here](/static/assets/img/about.PNG)

## TEAM
 ![enter image description here](/static/assets/img/demo/3.PNG)

## DEMO
 #### [COLAB NOTEBOOK](https://colab.research.google.com/drive/1j1KQ96Q4U5ERD8YXG33S--f3k0DmEEkZ?usp=sharing)
 ![enter image description here](/static/assets/img/demo/9.PNG)
 ![enter image description here](/static/assets/img/demo/1.PNG)
 ![enter image description here](/static/assets/img/demo/2.PNG)
 ![enter image description here](/static/assets/img/demo/4.PNG)
 ![enter image description here](/static/assets/img/demo/5.PNG)
 ![enter image description here](/static/assets/img/demo/6.PNG)
 ![enter image description here](/static/assets/img/demo/7.PNG)
 ![enter image description here](/static/assets/img/demo/8.PNG)

