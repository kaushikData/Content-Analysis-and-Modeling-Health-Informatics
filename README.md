# Content Analysis and Modeling - Health Informatics

Objective: Content analysis of chief complaints is performed to help hospitals understand the types of patients visit their hospital and predicted the length of stay of the patient at various stages at the hospital. These two models were requirements from local Los Angeles hospitals and this research is done in collaboration with Dr. Sriram Dasu, Data Science and Operations department, University of Southern California.

Data is from local Los Angeles hospitals. Data consists of patients' information like chief complaint, sex, age, acuity and expected wait time at the hospital, etc.

## Data Preprocessing - check codes/ICD preprocessing dataset notebook.

1. Chief Complaints (text) is preprocessed by removing punctuations, converting to lower case, removing stopwords and removing digit. These operations are performed after careful testing and observation of complaints data.

2. ICD codes (International Statistical Classification of Diseases and Related Health Problems) are given by a hospital. The first level of codes is derived and class names are generated with the help of Wikipedia (https://en.wikipedia.org/wiki/International_Statistical_Classification_of_Diseases_and_Related_Health_Problems). 

## Topic Modelling using LDA - check codes/ICD Chief Complaint Topic Model - ICD's are avoided

1. Bigrams and Trigrams are generated from Cheif Complaints vocabulary.
2. Topic Classification is implemented and clusters are visualized. However, coming up with a number of clusters (hyperparameter for topic model) was difficult and some clusters didn’t make sense.

Hence, ICD codes are considered in later notebooks for content analysis.

## Classification of each patient to an ICD code (22 classes) - check codes/ICD - SVM - LR - Analysis notebook.

1. Used Support Vector Machine, Naive Bayes and Logistic regression to built classic Natural Language Processing models. 

2. Visualized features using the eli5 package and assessed features for each class.

3. For each word in the vocabulary, generated ICD 22 dimensional probability vector, which is used later in the hierarchical cluster for content analysis.

## Classification using deep learning models - LSTM and BERT - check codes/ICD - SVM - LR - Analysis

1. Trained deep learning models (LSTM and BERT) on NVIDIA® GeForce® RTX™ 2060 6 GB GPU. 

2. However, the performance of these models was the same as conventional NLP models (SVM, LR, Naive Bayes). Hence conventional models were prefered for this dataset.

## Discovered shortcuts used by different doctors using custom-built word embedding - check codes/ICD shortcut detection - NER - POS notebook.

1. Detected shortcut or similar words using similarity between embedding vectors

2. Some of the discovered words are {rt - r - right, left - l, fx - fracture, ped - pedestrian, abd - abdominal, yrs - yr - years, mth - month, hrs -  hours}

## Generated hierarchical clusters of probabilistic ICD word vectors generated from codes/ICD - SVM - LR - Analysis. - check codes/ICD word probabilistic hierarchical clusters notebook

1. For each hospital, vocabulary is generated from patients' chief compaint. 
2. For each word, the ICD probability vector is generated from the previously created NLP Multiclass Support Vector Machine model.
3. Generated dendrogram and visualized hierarchal clusters to find the type of patients visits the hospital.



