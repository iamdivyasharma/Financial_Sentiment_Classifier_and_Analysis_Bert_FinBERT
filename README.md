# **Financial Sentimental Analysis. Build Financial Sentimental Classifier using BERT and FinBERT by transfer learning and Traditional Alogrithms (TF-IDF, SVM, Logistic Regression )**

ABOUT THE DATASET : 
>
The following data is intended for advancing financial sentiment analysis research. It's two datasets (FiQA, Financial PhraseBank) combined into one easy-to-use CSV file. It provides financial sentences with sentiment labels.


WHAT WE ARE DOING:
>
1) Preprcoessing the data and Exploratory data Analysis. 
>
2) Building Financial Sentimental classifier using  FinBERT , BERT model by transfer learning the model and using traditional models(TFIDF , SVM, LOGISTIC REGRESSION) for Financial Sentimental classification
>
NOTE : TRANSFER LEARNING : we are freezing 10 layers and training rest of the layers then evaluating our model performance in terms of F1, recall, accuracy and confusion matrix.
>
3) Comparision and conclusion
-___________________# PREPROCESSING__________________________________________________
Preprocessing: Cleaning, removing stopwords, lemmatization
>
Next step is cleaning the data to make it suitable to load it in our models. This is an essential step as feeding raw data will not give us good results.

1) All the '%' symbols are converted into text 'percent' using str.replace() function.>
2)  '$' represents currency US dollars we can convert it to 'usd' which is widely used. A function 'convert_usd' is defined to identify pattern using regular expression r'$' and converted to 'usd' using 'apply()' function >
3)  Any html tags <> in the dataset are identified by defining has_html_tags function. re.search() function will search for pattern * r"<[^>]+>" * and then return True is pattern is identified else False. apply() function is used to check in 'sentence' column in dataset 'df' and these values are stored in rows_with_html_tags variable. >
4) To identify any URL's or web addresses (starting with "http://", "https://", or "www.") in the dataframe we define function has_urls such that if re.search () function identifies pattern = r"\b(https?://|www.)\S+\b" in the text it will return value True or False otherwise. >
5) USing PhoneNumberMatcher() function in 'phonenumbers' package we identify any phone numbers in the text and return True if phone number is identified or False otherwise. then we convert all numbers to text.
6) 


 
 

