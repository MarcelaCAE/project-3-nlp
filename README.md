# Fake News Detection Project

## Objective of the Project
The goal of this project is to build a machine learning-based model that classifies news articles as real or fake by analyzing textual features using Natural Language Processing (NLP) techniques.


## Dataset Overview
The dataset consists of 34,151 rows and 2 columns, where each sentence is labeled as either fake (1) or real (0) news. 
It serves as the basis for training and evaluating the news classification model.

## Challenges & Solutions

The main challenge in this project was deciding between Count Vectorizer and TF-IDF Vectorizer for text feature extraction. The solution was to use both approaches with different models and select the one with the best results.


## Methodology

### **ETL (Extract, Transform, Load)**
- Create the function to load the data from the CSV file containing text and labeled data.
- Create the function to preprocess the data by standardizing it, removing non-alphabetic characters, and adjusting column names.
- Create the function to combine the words in each row into a single string, forming a list of headlines

### **Feature Extraction**
- Used vectorization to convert the training headlines into numerical representations using bigrams, for machine learning.
- Retrieved the ground truth labels from the dataset for each headline, which will be used to evaluate the model's performance.

### **Modeling**

#### **Train-Test Split**
-Performed Train Test Split (70/30) for Training and Test sets.

#### **Model Selection**

1. **First Model: SVM**
- Insights:The model performs well with 90% accuracy and a balanced F1-score, effectively distinguishing between real and fake news.
- On the SVM model, we use Count Vectorizer with biagrams for the mmodel counting the frequency of the biagrams on the headline news sentences, converting to numerical format (without taking in consideration the context of th words)

2. **Second Model: Naive Bayes (Multinominal)**
- Insights:The model performs better than SVM with  with 91% accuracy and a balanced F1-score, effectively distinguishing between real and fake news.
- On the Naive Bayes (Multinominal), we use the Tf-IDF vectorizer to convert the biagrams into numerical format  but in this case we are taking the consideration the frequency and the context, meaning that rare words will have a high importance in detecting the fake news).

### **Model Evaluation: **

1. **Confusion Matrix**  
  - SVM: The model misclassified 644 cases of fake news as real, and 409 cases of real news as fake.
  - Naive Bayes (Multinominal): The model misclassified 349 cases of fake news as real, and 528 cases of real news as fake.
  - Naive Bayes (Multinominal) showed better results in terms of acuracy with slower false positives than the SVM model.

2. **Classification Report**  
   - The model's performance on Naive Bayes (choosen model) is good, with acurate predictions for both classes with 91% acuracy and with a balanced recall and precision. 

3. **ROC CURVE**  
   - The model showed high performance with an AUC above 0.9, indicating that it effectively distinguishes between both classes, with a strong balance between precision and recall.   

3. **Conclusion**
-The Naive Bayes model outperformed the SVM model with 91% accuracy, demonstrating strong performance with accurate predictions.
-In this context, accuracy is the key metric, as our primary goal is to minimize false positives and false negatives to reduce their impact on the model's performance.

4. **Driven Questions for Business Team**
- Since our goal is to predict fake news, should we treat both false positives and false negatives with equal importance, or is it more critical, at first, to focus on reducing false negatives?
- Should we continue improving accuracy to capture both classes more effectively, or would it be more beneficial to explore new features to draw more robust conclusions and identify additional trends or patterns?
- Would it be useful to build a dashboard that displays the model's metrics/results, as well as the text features that are most influential in the predictions?

## Deliverables

1. **Python Code**  
   Conducted the analysis and data modeling using Python and Jupyter Notebook. The code includes data preprocessing, model training, and evaluation, showcasing the model's performance.

2. **Presentation**  
   A detailed PowerPoint presentation summarizing the findings and insights. It includes the confusion matrix and the model performance metrics, 

