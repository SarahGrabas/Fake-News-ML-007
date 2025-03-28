# Fake-News-ML-007
This is our exam project for GDS. Please read the README as the first thing.

## Goal of the project
The goal of the project is to build and compare fake news detection models. 


## Files in the project
The project consists of:
- A report of our findings
- Multiple Jyputer Notebooks:
  - Cleaning_File.ipynb
  - CSV_split.ipynb
  - Graphs.ipynb
  - LengthCorr.ipynb
  - Liar_Converter.ipynb
  - LogisticReg.ipynb
  - SVM.ipynb
- CSV and TSV file to be run in the Jupter Notebook files:
  - train.tsv
  - BBC_broad_content.csv
  - news_sample.csv (This file is not used)

##Important before running any code
- The 995,000_rows.csv file has not been uploaded to github, therefore the user needs to downloads this file, as it is used when running the CSV_split.ipynb file.

Each Jyputer Notebook takes one or more of the datasets, and we will make sure to explain in depth, what the input and output of each file is. 

Below is a step by step guide for how we executed our code.


## Chronological order of how our files should be run
- CSV_split.ipynb
- Cleaning_File.ipynb
- LogisticReg.ipynb
- SVM.ipynb


### Notebooks for extra visualisation and analysis
- Graphs.ipynb
- LengthCorr.ipynb
- Liar_Converter.ipynb


## Cleaning_File.ipynb
This notebook runs the full cleaning pipeline. This includes removing all non-english articles, cleaning- and stemming the content column. 

This jupyter notebook the cleaning process of all datasets. The cleaning include, removing all articles that aren't english, cleaning and stemming. 

### Modules
- pandas
- re
- langdetech - detect
- nltk.tokenize - word_tokenize
- nltk.corpus - stopwords
- nltk.stem - PorterStemmer
- cleantext - clean 
- collections - Coutner
- pandarallel - pandarallel

### Input:
- 995,000_rows.csv
- bbc_scrape_uncleaned.csv
- liar_uncleaned.csv


### Output:
- large_corpus_cleaned.csv
- bbc_cleaned.csv
- liar_cleaned.csv
  
## CSV_split.ipynb
Purpose is to divide the large corpus into a training set(80%), validation set(10%) and a test set(10%). 
Before we split we also divide the articles into a broad category of "Fake News" and "Reliable" which we will use in the logistic regression and SVM. 

### Modules
- pandas 
- sklearn.model_selection - train_test_split

### Input:
- large_corpus_cleaned.csv
- liar_cleaned.csv
  
  995,000_rows.csv

### Output: 
- full_train_set.csv
- val_set.csv
- test_set.csv

- liar_test_set.csv
- liar_val_set.csv
- liar_test_set.csv

## logisticreg.ipynb
This notebook perfoms logistic regression on the dataset to classify the news articles. 

### Modules
- numpy
- pandas
- sklearn.feature_extraction.text - CountVectorizer
- sklearn.linear_model - LogisticRegression
- sklearn.model_selection - train_test_split
- sklearn.metrics - classification_report


## SVM.ipynb

  
  
  
  










