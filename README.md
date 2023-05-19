
# **Advancing Financial Sentiment Analysis: Exploiting the Power of BERT and FinBERT for Constructing a Robust Sentiment Classifier, and Comparative Analysis with Traditional Algorithms (TF-IDF, SVM, Logistic Regression)**

ABOUT THE DATASET : Download the dataset using cmd :  kaggle datasets download -d sbhatti/financial-sentiment-analysis
>
1) Preprcoessing the data and Exploratory data Analysis. (Preprocessing_and_EDA.ipynb)
>
2) Building Financial Sentimental classifier using  FinBERT , BERT model by finetuning and transfer learning(freezing 12 layers and then finetuning) the model and using traditional models(TFIDF , SVM, LOGISTIC REGRESSION) for Financial Sentimental classification
>
NOTE :
>TRANSFER LEARNING : we are freezing 12 layers and training rest of the layers then evaluating our model performance in terms of F1, recall, accuracy and confusion matrix.
>By freezing the BERT layers, you essentially keep the pre-trained BERT weights fixed and prevent them from being updated during the training process. This can be useful when you have limited training data or when you want to leverage the pre-trained representations of BERT for your specific task without modifying them.
>During training, only the weights of the classification layer will be updated, allowing the model to learn task-specific patterns and make predictions based on the fixed BERT representations. The frozen BERT layers act as a feature extractor, providing contextualized word representations to the trainable classification layer.
>**If you want to fine tune the model , simply do not freeze the layers and train the model ,remove the code that freezes the layers. By default, all the layers of the model will be trainable.**

>

>
># PREPROCESSING
>
Preprocessing Steps : Cleaning, removing stopwords, lemmatization
> Drop missing values and convert data to lower case
> remove stop words
> Then tokenizing the sentence using the 'nltk.word_tokenize()' function and then applying lemmatization on each token using the lemmatize function from the 'WordNetLemmatizer'
> 
># Exploratory Data Analysis

># **Sentimental Distribution category wise**
> 
![image](https://github.com/iamdivyasharma/Financial_Sentiment_Classifier_and_Analysis_Bert_FinBERT/assets/66716367/50f497a7-927e-45bb-b6cb-0730b6224309)
># **Pie chart for  percentage distribution of each category**
>
![image](https://github.com/iamdivyasharma/Financial_Sentiment_Classifier_and_Analysis_Bert_FinBERT/assets/66716367/880d17df-79fe-407e-bb33-7cc473e010ab)
># **Length of Financial phrases**
>
![image](https://github.com/iamdivyasharma/Financial_Sentiment_Classifier_and_Analysis_Bert_FinBERT/assets/66716367/a92a387a-a52d-4dee-b056-d84c3234fb61)
># **Word COunts in Financial phrases**
>
![image](https://github.com/iamdivyasharma/Financial_Sentiment_Classifier_and_Analysis_Bert_FinBERT/assets/66716367/77929d9e-504c-425e-b33f-4012b292a7cc)
># **Box Plot of WOrd Count and Length**
>
 ![image](https://github.com/iamdivyasharma/Financial_Sentiment_Classifier_and_Analysis_Bert_FinBERT/assets/66716367/4b18b4ce-f3d4-43ee-be40-d04706f79dbb)
># **Word Cloud : More frequently a word appears in the text, the larger and more prominent it appears in the word cloud**
>
 ![image](https://github.com/iamdivyasharma/Financial_Sentiment_Classifier_and_Analysis_Bert_FinBERT/assets/66716367/42ac221b-3c46-4144-89d8-32d9536620aa)
># **Shows  top 10 words and their counts** 
>
![image](https://github.com/iamdivyasharma/Financial_Sentiment_Classifier_and_Analysis_Bert_FinBERT/assets/66716367/41a0809d-fb26-4bf6-920a-c7579d8b7abd)
># **Bar chart of the top 10 bigrams and their counts** 
> 
![image](https://github.com/iamdivyasharma/Financial_Sentiment_Classifier_and_Analysis_Bert_FinBERT/assets/66716367/03108924-6283-4b86-bc79-53e4fa661e60)


># **bar chart of the top 10 trigrams and their counts**
![image](https://github.com/iamdivyasharma/Financial_Sentiment_Classifier_and_Analysis_Bert_FinBERT/assets/66716367/1a7264e8-f3d6-4a40-82c0-77913533c1a1)

># **bar chart of the top 10 words for each sentiment category**

![image](https://github.com/iamdivyasharma/Financial_Sentiment_Classifier_and_Analysis_Bert_FinBERT/assets/66716367/8eb835ad-7748-467d-89de-baed1fe23ef7)

># **The correlation matrix**

![image](https://github.com/iamdivyasharma/Financial_Sentiment_Classifier_and_Analysis_Bert_FinBERT/assets/66716367/abbc0114-31d9-40a0-bdec-038e0b1a2f6d)
>
>
>
># **BERT - FREEZED 6 layers and then FINE TUNED**
> 
>Classification Report 
>
![bert_freezed_report](https://github.com/iamdivyasharma/Leveraging_BERT_FinBERT_Building-Robust-Sentiment-Classifier-and-comparing-with-Traditional-Algos/assets/66716367/0dc8b1e6-0cf1-4887-bd77-f8a3f0cfbc99)
>
> Confusion Matrix
> 
![bert_freezed_matirx](https://github.com/iamdivyasharma/Leveraging_BERT_FinBERT_Building-Robust-Sentiment-Classifier-and-comparing-with-Traditional-Algos/assets/66716367/92a6f8d9-9e8f-40c3-a62a-ac2e553ecd0f)
>

>**F1 Score:0.6605896975027725**



># **BERT - FINE TUNED**
>
>BERT Fine-tuned Classification Report 
>
![report_bert](https://github.com/iamdivyasharma/Leveraging_BERT_FinBERT_Building-Robust-Sentiment-Classifier-and-comparing-with-Traditional-Algos/assets/66716367/928668b8-ccd1-4318-b498-efb409ec89e0)
>
> BERT Fine-tuned Confusion Matrix
> 

![matrix_bert](https://github.com/iamdivyasharma/Leveraging_BERT_FinBERT_Building-Robust-Sentiment-Classifier-and-comparing-with-Traditional-Algos/assets/66716367/ad620a04-03d1-4ecd-8405-c1a8bda6c192)

>**F1 Score: 0.7392649042485108**








