# scrape_and_compare
## Required packages
  1. requests
  2. fuzzywuzzy
  3. sentence_transformers
  4. tensorflow
  5. tensorflow_hub
  6. bs4
## Encoding models in use- Universal Sentence Encoder, Sentence Transformers

## Domains
 - Currently our code will support only 3 domains based articles
   - The Hindu
   - NewYork Times
   - NDTV

## Functionality :
  - Takes 2 urls as input which are actually the urls of articles from 2 different sources.
  - Now for each url, we will do scraping with below approach in a single function called `scraper`
    - First we scrape entire content and convert it into a soup object
    - Later we will remove all unwanted html tags content from soup object
    - Then we will takeout only text content from the rest of the soup object and do some basic cleansing like removing too many newline characters, spaces, ads content etc..,
    - After that, we will remove duplicate sentences from the lsit using fuzzywuzzy WRatio methos and keeping threshhold value as 90(So any pair is having value above 90 then we will remove smaller one from the text content)
    - Now on top of this final list we will filter out all unwanted or not similar sentences to the context of article by using similarity score calculated based on Universal Sentence encoder embeddings.
    - At last , we return the final list of sentences for the give URL.
  - Now we will combine all the sentences in the returned list into a single sentece and then we will calculate embeddings for it based on the type of encoder that user has selected(Sentence Transformer or Universal Sentence encoder).
  - At last we caluculate the similarity score of two embeddings and returns the score.
