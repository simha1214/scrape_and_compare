
## Required packages
  1. pandas
  2. gensim


## Source
 - Currently our Word2Vec model is built on 2.49 lakh articles scraped from 13 different financial domains for 7+k companies. Time range is from year 1980 to 2020.

## Functionality :
  - We collected all the articles from different sources and trained the w2v model on top of them.
  - Then saved that w2v model as a pickle file(which is provided in the folder). So please copy that pickle file as well to the locaion where you are keeping this code file or else you can directly update the pickle file path in the main.py file.
  - Now please provide how many synonyms you want to get and for which word you are willing to get synonyms.
  - At last you will get a list of words with similarity scores as output of the file.
  - In case if you want to train the w2v model from scratch with your own data, we aslo provided a function which will read your input data and column name on which this model will have to train.
