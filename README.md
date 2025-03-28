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
  - Liar_Converter.ipynb
  - LogisticReg.ipynb
  - SVM.ipynb
- CSV and TSV file to be run in the Jupter Notebook files:
  - train.tsv
  - BBC_broad_content.csv
  - news_sample.csv (This file is not used)

##Important before running any code
- The 995,000_rows.csv file has not been uploaded to github, therefore the user needs to downloads this file, as it is used when running the CSV_split.ipynb file.

Each Jyputer Notebook is build so it can be run from top to buttom unless else is mention, then will make sure that it is explained how the file should be run and what the input and output of each file is. 


## Chronological order of how our files should be run
- CSV_split.ipynb
- Cleaning_File.ipynb
- LogisticReg.ipynb
- SVM.ipynb


### Notebooks for extra visualisation and analysis
- Graphs.ipynb
- Liar_Converter.ipynb

## CSV_split.ipynb
Purpose is to remove all non-english articles from the dataset and divide the large corpus into a training set(80%), validation set(10%) and a test set(10%). 
Before we split we remove all non-english articles and divide the articles into a broad category of "Fake News" and "Reliable" which we will use in the logistic regression and SVM. 

### Modules
- pandas 
- sklearn.model_selection - train_test_split
- pandarallel - pandarallel
- langdetect - detect, DetectorFactory

### Input:
- 995,000_rows.csv

### Output: 
- full_train_set.csv
- full_val_set.csv
- full_test_set.csv


## Cleaning_File.ipynb
This jupyter notebook contains the cleaning process of all datasets (training, validation and test set), the scraped articles from BBC form assignment 2 and the liar dataset.
The cleaning include cleaning and stemming. 
When running the cleaning file, the string calculations are marked as comments, because it completely eats ups ones RAM, and therefore we do not recommend running the code. We have run it when necessary and restarted the kernel, since it takes too much processessing power.


### Modules
- pandas
- re
- nltk.tokenize - word_tokenize
- nltk.corpus - stopwords
- nltk.stem - PorterStemmer
- cleantext - clean 
- collections - Coutner
- pandarallel - pandarallel


### Input:
When cleaning every part of the training set, the filenames should be changed in the Cleaning_File.ipynb, so the correct file is read, cleaned and converted to csv.
- full_train_set.csv
- full_val_set.csv
- full_test_set.csv

- BBC_broad_content.csv

If you want to clean the liar dataset it is important to run the Liar_Convert.ipynb first, because the liar_train.csv is converted in Liar_Convert.ipynb.
- liar_train.csv


### Output:
- full_train_cleaned.csv
- full_val_cleaned.csv
- full_test_cleaned.csv
- bbc_cleaned.csv
- liar_cleaned.csv
  

## LogisticReg.ipynb
This notebook perfoms logistic regression on the dataset to classify the news articles. The file also contains a second logistic regression model that is trained on the training set and BBC articles and testet on the validation set. The cleaned liar data is also evaluated on the first logistic regression model. 

### Modules
- numpy
- pandas
- sklearn.feature_extraction.text - CountVectorizer
- sklearn.linear_model - LogisticRegression
- sklearn.model_selection - train_test_split
- sklearn.metrics - classification_report

### Input:
- full_train_cleaned.csv
- full_val_cleaned.csv
- full_test_cleaned.csv
- bbc_cleaned.csv
- liar_cleaned.csv

### Output:
- Performance for:
    - Validation set (model trained on training set)
    - Test set
    - Validation set (model trained on training set and BBC)
    - Liar data

## SVM.ipynb
This notebook perform Support Vector Machine model, SGDClassifier, on the dataset to classify the news articles. The file also contains a Grid Search, which was used for choosing parameters. The cleaned liar data is also evaluated on the model. In the end of the file we evaluate the model.


### Modules
- numpy
- pandas
- sklearn.feature_extraction.text - CountVectorizer
- sklearn.model_selection - train_test_split
- sklearn.metrics - accuracy_score, classification_report, f1_score
- sklearn.feature_extraction.text - TfidfVectorizer
- sklearn.svm - SVC
- sklearn.svm - LinearSVC

### Input:
- full_train_cleaned.csv
- full_val_cleaned.csv
- full_test_cleaned.csv
- liar_cleaned.csv

### Output:
- Performance for:
    - Validation set (model trained on training set)
    - Test set
    - Liar data
- Evaluation of the model
  
  
  










