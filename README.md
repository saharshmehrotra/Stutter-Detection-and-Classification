# Stutter Detection and Classification

Stuttering is a neuro-developmental speech disorder that interrupts the flow of speech due to involuntary pauses and sound repetitions. It has profound psychological impacts that affect social interactions and professional advancements. 

Automatically detecting stuttering events in speech recordings could assist speech therapists or speech pathologists track the fluency of people who stutter (PWS). It will also assist in the improvement of the existing speech recognition system for PWS. 

In this project, the SEP-28k dataset is utilized to perform comparative analysis to assess the performance of various machine learning models in classifying the five dysfluency types namely Prolongation, Interjection, Word Repetition, Sound Repetition and Blocks.

## Contributions:

 1. Developing robust machine learning models for classifying the five classes of Stutter- Interjection, Prolongation, Blocks, Sound Repetitions and Word Repetitions.
 2. Conducting analysis on the impact of various features extracted manually as well as using pre-trained models.
 3. Performing comparative analysis on each class of stutter using various machine learning models.

## Dataset
The SEP-28k dataset, published by Apple Machine Learning Research, is used for training and evaluation.It consists of audio recordings from six podcast shows and is annotated with various dysfluency types. The dataset is multi-label and multi-class, with annotations done by at least three annotators.

Annotations: The SEP-28k dataset includes annotations for audio clips, labeled by at least three annotators. These labels cover various categories such as 'Unsure', 'PoorAudioQuality', 'Music', 'DifficultToUnderstand', 'Interjection', 'Prolongation', 'Blocks', 'WordRep', 'SoundRep', 'NoStutteredWords', 'NoSpeech', and 'NaturalPause'. Each 3-second clip can have multiple labels, making the dataset both multi-label and multi-class. 

<p align="center">
    <img width="550" alt="image" src="https://github.com/Ramitha-V/Stutter-Detection-and-Classification/assets/162662008/bd132e26-b6da-4016-a542-19843db8c81a">
</p>

## Preprocessing:
The following preprocessing steps were done before proceeding further:
- Deleted audio clips not exactly 3 seconds long.
- Ensured all audio clips had a 16kHz sampling rate.
- Reduced classes from 11 to fewer due to lack of meaningful contribution.
- Dropped the 'Unsure' column.
- Removed clips labeled as music (introductory or concluding music).
- Dropped the 'Music' column.
- Removed clips labeled as 'DifficultToUnderstand' by two or more annotators.
- Dropped the 'DifficultToUnderstand' column.
- Class Imbalance was handled

## Feature Extraction:
The following features were extracted:
- MFCCs (Mel-Frequency Cepstral Coefficients): Capture the power spectrum of audio signals.
- Zero Crossing Rate: Measure the rate at which the signal changes sign.
- Jitter: Measure the frequency variation from cycle to cycle.
- Shimmer: Measure the amplitude variation from cycle to cycle.

## Model Training:
 After the extracted features are concatenated into an array, these features are given to the  models for training. Here individual models have been considered for each class- namely, K-Nearest Neighbors (KNN), Support Vector Machine (SVM), Random Forest, Decision Tree and Naive Bayes. All the above mentioned models are trained for all the classes and the model which gives the highest accuracy is chosen for that particular class.

 ## Hyperparameter Tuning:
 Hyperparameter tuning and cross validation techniques were applied on each of the models i.e., KNN, Logistic Regression, Decision Tree, Random Forest, and SVM, and just cross validation (with 10-fold cross-validation) for Naïve Bayes as it is a non-parametric model.

## Evaluation Metrics:
Both training and testing were done on the SEP-28k dataset where the train to test ratio is 70:30. The main evaluation metric considered for choosing the models for each class is accuracy, as the data for each class was balanced. Other metrics considered are F1-score, accuracy, precision, recall, confusion matrix and ROC-AUC.

## Deployment:
https://github.com/Ramitha-V/Stutter-Detection-and-Classification/assets/162662008/0f9b8ac6-bcea-439d-857a-e8e0754d3081
