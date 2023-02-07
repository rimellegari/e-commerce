# e-commerce

This project has as an objetive to analyze a Brazilian ecommerce dataset.
It's divided in two parts the first one is dedicated to EDA and data cleaning in order to get a deeper knowledge of the provided information.
The second part is dedicated to dive into customer reviews, scores and build a sentiment analysis model in order to classify a review as positive or negative comment.
Two methods to create word vectors were used: bag of words and TF-IDF, as for the sentiment analysis 3 different models were tested: Logisical Regression, Multinomial Naive Bayes and Random Forest.
TF-IDF was the best method for creating word vectors and despite having very similar results, Logistical Regression had better performance metrics with the following results:
Accuracy = 88.77%, AUROC = 88.37% and F1-Score= 88.77%
