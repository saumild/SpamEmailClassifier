# SpamEmailClassifier

Task : Build a classification model which will be able to distinguish between spam/not spam. You should,compare the performance of few classification algorithms by your choice and choose the best performing one. You should perform k-fold cross-validation.

DataSet Details: The last column of 'spambase.data' denotes whether the e-mail was considered spam (1) or not (0), i.e. unsolicited commercial e-mail. Most of the attributes indicate whether a particular word or character was frequently occuring in the e-mail. The run-length attributes (55-57) measure the length of sequences of consecutive capital letters. For the statistical measures of each attribute, see the end of this file. Here are the definitions of the attributes:

48 continuous real [0,100] attributes of type word_freq_WORD = percentage of words in the e-mail that match WORD, i.e. 100 * (number of times the WORD appears in the e-mail) / total number of words in e-mail. A "word" in this case is any string of alphanumeric characters bounded by non-alphanumeric characters or end-of-string.

6 continuous real [0,100] attributes of type char_freq_CHAR] = percentage of characters in the e-mail that match CHAR, i.e. 100 * (number of CHAR occurences) / total characters in e-mail

1 continuous real [1,...] attribute of type capital_run_length_average = average length of uninterrupted sequences of capital letters

1 continuous integer [1,...] attribute of type capital_run_length_longest = length of longest uninterrupted sequence of capital letters

1 continuous integer [1,...] attribute of type capital_run_length_total = sum of length of uninterrupted sequences of capital letters = total number of capital letters in the e-mail

1 nominal {0,1} class attribute of type spam = denotes whether the e-mail was considered spam (1) or not (0), i.e. unsolicited commercial e-mail.

Classifiers detail : Note: Few parameters have been fine tuned for better performance results.

1. LogisticRegression - We will use lbfgs solver with 2000 iterations
2. KNeighborsClassifier - we are using Euclidean metrics with 4 neighbours to classify the given predict data point.
3. SVC - we are using rbf kernal for this classification
4. MultinomialNB - alpha value has been fine tuned to 1 for getting better resutls and fit_prior is made true.
5. RandomForestClassifier - Using 50 estimators with maxdepth of decision trees set to 50
6. MLPClassifier - Neural Network approach for solving the problem. Fine tuned a parameters for better results.


Confusion matrix and details with KFold cross validation for the best performing model

KFold Cross Validation ensures that we wont overfit the model.

1. False positive rate - Fraction of non-spam testing examples that are misclassified as spam
2. False negative rate - Fraction of spam testing examples that are misclassified as non-spam
3. Overall error rate - Fraction of overall examples that are misclassified.
