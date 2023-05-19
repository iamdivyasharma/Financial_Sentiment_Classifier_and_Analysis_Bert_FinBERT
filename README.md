# **Financial Sentimental Analysis. Build Financial Sentimental Classifier using BERT and FinBERT by transfer learning and Traditional Alogrithms (TF-IDF, SVM, Logistic Regression )**

ABOUT THE DATASET : 
>
The following data is intended for advancing financial sentiment analysis research. It's two datasets (FiQA, Financial PhraseBank) combined into one easy-to-use CSV file. It provides financial sentences with sentiment labels.

>
1) Preprcoessing the data and Exploratory data Analysis. 
>
2) Building Financial Sentimental classifier using  FinBERT , BERT model by transfer learning the model and using traditional models(TFIDF , SVM, LOGISTIC REGRESSION) for Financial Sentimental classification
>
NOTE : TRANSFER LEARNING : we are freezing 10 layers and training rest of the layers then evaluating our model performance in terms of F1, recall, accuracy and confusion matrix.
>
3) Comparision and conclusion 
>
># PREPROCESSING
>
Preprocessing Steps : Cleaning, removing stopwords, lemmatization
>
Next step is cleaning the data to make it suitable to load it in our models. This is an essential step as feeding raw data will not give us good results.
> cleaning steps
> 
1) All the '%' symbols are converted into text 'percent' using str.replace() function.>
2)  '$' represents currency US dollars we can convert it to 'usd' which is widely used. A function 'convert_usd' is defined to identify pattern using regular expression r'$' and converted to 'usd' using 'apply()' function >
3)  Any html tags <> in the dataset are identified by defining has_html_tags function. re.search() function will search for pattern * r"<[^>]+>" * and then return True is pattern is identified else False. apply() function is used to check in 'sentence' column in dataset 'df' and these values are stored in rows_with_html_tags variable. >
4) To identify any URL's or web addresses (starting with "http://", "https://", or "www.") in the dataframe we define function has_urls such that if re.search () function identifies pattern = r"\b(https?://|www.)\S+\b" in the text it will return value True or False otherwise. >
5) USing PhoneNumberMatcher() function in 'phonenumbers' package we identify any phone numbers in the text and return True if phone number is identified or False otherwise. then we convert all numbers to text.
6) words like 'm','mn', meaning million and 'b', 'bn' meaning billion and replace these using str.replace() function.
7) Removed punctuation using the pattern

> After cleaning data , we removed stop words
> Then first tokenizing the sentence using the 'nltk.word_tokenize()' function and then applying lemmatization on each token using the lemmatize function from the 'WordNetLemmatizer'
> 
># Exploratory Data Analysis

>Sentimental Distribution category wise 
![image](https://github.com/iamdivyasharma/Financial_Sentiment_Classifier_and_Analysis_Bert_FinBERT/assets/66716367/50f497a7-927e-45bb-b6cb-0730b6224309)
>Pie chart for  percentage distribution of each category >
![image](https://github.com/iamdivyasharma/Financial_Sentiment_Classifier_and_Analysis_Bert_FinBERT/assets/66716367/880d17df-79fe-407e-bb33-7cc473e010ab)
Length of Financial phrases >
![image](https://github.com/iamdivyasharma/Financial_Sentiment_Classifier_and_Analysis_Bert_FinBERT/assets/66716367/a92a387a-a52d-4dee-b056-d84c3234fb61)
Word COunts in Financial phrases >
![image](https://github.com/iamdivyasharma/Financial_Sentiment_Classifier_and_Analysis_Bert_FinBERT/assets/66716367/77929d9e-504c-425e-b33f-4012b292a7cc)
Box Plot of WOrd Count and Length >
 ![image](https://github.com/iamdivyasharma/Financial_Sentiment_Classifier_and_Analysis_Bert_FinBERT/assets/66716367/4b18b4ce-f3d4-43ee-be40-d04706f79dbb)
Word Cloud : more frequently a word appears in the text, the larger and more prominent it appears in the word cloud >
 ![image](https://github.com/iamdivyasharma/Financial_Sentiment_Classifier_and_Analysis_Bert_FinBERT/assets/66716367/42ac221b-3c46-4144-89d8-32d9536620aa)
 Shows  top 10 words and their counts >

![image](https://github.com/iamdivyasharma/Financial_Sentiment_Classifier_and_Analysis_Bert_FinBERT/assets/66716367/41a0809d-fb26-4bf6-920a-c7579d8b7abd)
bar chart of the top 10 bigrams and their counts >
![image](https://github.com/iamdivyasharma/Financial_Sentiment_Classifier_and_Analysis_Bert_FinBERT/assets/66716367/03108924-6283-4b86-bc79-53e4fa661e60)


bar chart of the top 10 trigrams and their counts >
![image](https://github.com/iamdivyasharma/Financial_Sentiment_Classifier_and_Analysis_Bert_FinBERT/assets/66716367/1a7264e8-f3d6-4a40-82c0-77913533c1a1)

bar chart of the top 10 words for each sentiment category >

![image](https://github.com/iamdivyasharma/Financial_Sentiment_Classifier_and_Analysis_Bert_FinBERT/assets/66716367/8eb835ad-7748-467d-89de-baed1fe23ef7)

The correlation matrix >

![image](https://github.com/iamdivyasharma/Financial_Sentiment_Classifier_and_Analysis_Bert_FinBERT/assets/66716367/abbc0114-31d9-40a0-bdec-038e0b1a2f6d)










