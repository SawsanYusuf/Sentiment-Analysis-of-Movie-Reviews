# Sentiment Analysis of Movie Reviews

![](https://github.com/SawsanYusuf/Sentiment-Analysis-of-Movie-Reviews/blob/main/Images/istockphoto-1196964881-1024x1024.jpg)

## Objective:
The goal is to predict the sentiment for a given review 
from a user with the help of either classification or deep learning algorithms.

## Dataset: 
[IMDB Dataset | Kaggle](https://www.kaggle.com/datasets/lakshmi25npathi/imdb-dataset-of-50k-movie-reviews)

IMDB dataset having 50K movie reviews for natural language processing or Text analytics.

**Data fields:** 
* id — Unique ID of each review
* review — Text of the review
* label — Sentiment of the review; 1 for positive reviews and 0 for negative reviews

## Inspect and explore data
We encountered no issues with data types and found no null values. We did, however, identify and remove some duplicate entries. The relative frequencies of the classes in the dataset are close, indicating that the data is balanced.

![](https://github.com/SawsanYusuf/Sentiment-Analysis-of-Movie-Reviews/blob/main/Images/class%20balance.png)


## Data cleaning 
For any NLP problem it is essential the raw data is cleaned and processed in the desired format before fed into the model. Here we have converted the data into lower case and removed punctuations using string library which proved faster in than what I had seen in the reference material. Additionally the stopwords (such as “the”, “a”, “an”, “in”) were removed using the NLTK library as these words don't matter when indexing.

Another processes we applied: 
* Remove HTML tags
* Remove Urls
* Remove numbers 
* Remove symbols
* Remove emojis
* Handle chat words
* Stemming / Lemmatization

## Models
We Created a pipeline named model that contains a transformer to represent text data into vectors and a predictor.

We used different algorithms and trained them with different data and transformers. Then, we evaluate them using the accuracy and F1-Score. 

**Transformers**: 
* Bag of words
* TF-IDF
  
**Predators**:
* Naive Bayes
* Decision Tree 
* Logistic Regression 
* Random Forest 
* K-Nearest Neighbor 
* XGBOOST



