# Disaster-Tweets
This is the solution to the competition [Real or Not? NLP with Disaster Tweets](https://www.kaggle.com/c/nlp-getting-started) from kaggle. In this solution after going a number of notebooks and there analysis on the data I proposed a BERT-base network to classify tweets as fake or not. In this notebook you'll find wrapper class which wraps the tokenizing method for BERT, along with BERT-base architecture using hub file from tensorflow-hub. We have used [BERT-base_uncased_English_v1](https://tfhub.dev/tensorflow/bert_en_uncased_L-12_H-768_A-12/1) which consists of 12 encoding layers, 768 input embeddings and 12 attention models. We have used the module [tokenizatoion.py](https://raw.githubusercontent.com/tensorflow/models/master/official/nlp/bert/tokenization.py) from https://github.com/tensorflow/models/tree/master/official/nlp/bert for tokenization for BERT.
The dataset in this competition comprises of features:
- 'id'
- 'keyword'
- 'location'
- 'text', and
- 'target'
In these features 'id' is to distinguish between all the tweets, 'keyword' contains the certain word present in the 'text' which helps in classifying the output. 'location' is independent with respect to the users and finally target to distinguish between different tweets.
I pre-processed the data and labelled them again because some tweets were mislabeled. After then in the wrapper class, in 'build_model' method I ran the model for 4 folds using [StratifiedKFold](https://scikit-learn.org/stable/modules/generated/sklearn.model_selection.StratifiedKFold.html) from sklearn. After that using 'predict' method we predicted the classes for test data.

Check out my kaggle kernel 👉 [Disaster Tweets- BERT+TF2.0](https://www.kaggle.com/ambityga/disaster-tweets-bert-tf2-0?scriptVersionId=33430551)
