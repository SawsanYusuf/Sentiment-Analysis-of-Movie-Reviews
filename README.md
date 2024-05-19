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

### ML Algorithms 
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

![](https://github.com/SawsanYusuf/Sentiment-Analysis-of-Movie-Reviews/blob/main/Images/ml%20models.png)

### LSTM Models

First, we processing the data:
1. Tokenization: We used the Tokenizer class from Keras, which also takes care of converting the words to lower case and removing punctuation.
2. Sequence conversion: Next, we converted the tokens into sequences of integers. Each unique word was assigned a unique integer.
3. Sequence padding: Because LSTM networks require input data with the same length, we used padding to ensure all sequences had the same length.

After preprocessing our data, we moved on to constructing the LSTM network. The model was created using Keras’ Sequential API, indicating that our model would be built layer by layer in a sequential manner.
The models basic structure: 
1. Embedding layer: This layer transformed our integer sequences (representing words) into dense vectors of fixed size. 
2. LSTM layers: Next, we added an LSTM layer. LSTM layers are effective in processing sequences (like text), as they can capture the temporal dependencies between elements in the sequence.
3. Dense layers: After the LSTM layers, we included a dense (fully connected) layer. We used the ‘sigmoid’ activation function. We also added dropout to these layers to avoid overfitting.

We then trained our model on our preprocessed reviews and sentiments, using a batch size of 264 and running for 10 epochs. We also included early stopping in our training to prevent overfitting.

![](https://github.com/SawsanYusuf/Sentiment-Analysis-of-Movie-Reviews/blob/main/Images/lstm.png)


## Further Work 
Using an LSTM-based neural network, we achieved impressive results in predicting our target. Future work might involve exploring different neural network architectures, using pre-trained embeddings, or applying this model to other NLP tasks.
