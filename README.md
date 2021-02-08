# Fake News Analysis

Introduction
Though the term Fake News is a recent phenomenon, the concept behind it, that of misinformation and misguidance is timeless. Only recently have technological tools reached the point that the line between fact and fiction is blurred and the audience can be millions of unsuspecting people which can be a recipe for disaster. Therefore, we must have proper tools to detect fake news. Natural language processing techniques are innately well-disposed to this task.

Dataset
We have selected a dataset that is clean, having no missing values, and an ideal candidate to pass through the different natural language processing techniques.
Our dataset has 6335 observations and 4 variables. The four variables are,
•	A numeric tag labelled X
•	Title of the news article in string format
•	Text of the news article in string format
•	The label of Real or Fake as Outcome variable
This dataset has been selected from Kaggle and can be considered an accurate slice of data available on news websites. We have divided the dataset into training and testing data with training representing 67% of the data and testing 33%.

Relevance
The dataset selected has 6335 news articles. This is a good subset of articles that can be found on different news websites. We choose news articles from websites as they can be used as a template to create an effective model which can be scaled to apply on social media sites, online forums and chatrooms.
In this manner, we are able to perform classification of content as fake news and create tools which can be used to combat its spread and effects.

Methods
We will be using the following Natural Language Processing methods,
•	CountVectorizer
•	TfidfVectorizer
•	Hashing
•	Bag of Words

CountVectorizer –
The CountVectorizer provides a simple way to both tokenize a collection of text documents and build a vocabulary of known words, but also to encode new documents using that vocabulary.
It can used in the following manners:
•	To create an instance of the CountVectorizer class.
•	To call the fit() function in order to learn a vocabulary from one or more documents.
•	To call the transform() function on one or more documents as needed to encode each as a vector.
For the result an encoded vector is returned with a length of the entire vocabulary and an integer count for the number of times each word appeared in the document.
Because these vectors will contain a lot of zeros, we call them sparse. 
Importantly, the same vectorizer can be used on documents that contain words not included in the vocabulary. These words are ignored, and no count is given in the resulting vector.
After implementing CountVectorizer we obtain the following result with the accuracy of 89.3%.

TfidfVectorizer –
The TfidfVectorizer will tokenize documents, learn the vocabulary and inverse document frequency weightings, and allow you to encode new documents. We can use CountVectorizer as in we can use it with a TfidfTransformer to just calculate the inverse document frequencies and start encoding documents.
The same create, fit, and transform process is used as with the CountVectorizer.
 
After implementing TfidfVectorizer we obtain the above result with the accuracy of 85.7%.
HashingVectorizer –
Counts and frequencies can be very useful, but one limitation of these methods is that the vocabulary can become very large.
This, in turn, will require large vectors for encoding documents and impose large requirements on memory and slow down algorithms.
A clever work around is to use a one-way hash of words to convert them to integers. The clever part is that no vocabulary is required, and you can choose an arbitrary-long fixed length vector. A downside is that the hash is a one-way function so there is no way to convert the encoding back to a word (which may not matter for many supervised learning tasks).
The HashingVectorizer class implements this approach that can be used to consistently hash words, then tokenize and encode documents as needed.
We utilize some elements of web scraping along with hashing to test viability and obtain following results,
 
After implementing HashingVectorizer we obtain the above result with the accuracy of 86.9%.

Bag-of-Words –
The Bag-of-Words model is a simplifying representation used in natural language processing and information retrieval (IR). 
The Bag-of-words model is mainly used as a tool of feature generation. After transforming the text into a "bag of words", we can calculate various measures to characterize the text.
The most common type of characteristics, or features calculated from the Bag-of-words model is term frequency.
This list (or vector) representation does not preserve the order of the words in the original sentences. This is just the main feature of the Bag-of-words model. This kind of representation has several successful applications, such as email filtering.
However, term frequencies are not necessarily the best representation for the text. Common words like "the", "a", "to" are almost always the terms with highest frequency in the text. Thus, having a high raw count does not necessarily mean that the corresponding word is more important. To address this problem, one of the most popular ways to "normalize" the term frequencies is to weight a term by the inverse of document frequency.
Web scraping, web harvesting, or web data extraction is data scraping used for extracting data from websites. 
Web scraping software may access the World Wide Web directly using the Hypertext Transfer Protocol, or through a web browser. While web scraping can be done manually by a software user, the term typically refers to automated processes implemented using a bot or web crawler. 
It is a form of copying, in which specific data is gathered and copied from the web, typically into a central local database or spreadsheet, for later retrieval or analysis. In this project, we utilize multiple different packages of the Python programming language to perform web scraping.
 
After implementing Bag-of-Words method we obtain the above result with the accuracy of 90.2%.
Analysis
Method	Accuracy
CountVectorizer	89.30%
TfidfVectorizer	85.70%
Hashing	86.90%
Bag of Words	90.20%

After comparing the different NLP methods, we observe that though Bag of Words has highest accuracy at 90.2% it has certain limitations that can make it less than desirable to implement on all the different types of news articles we want to classify.
Conclusion
After implementing all the different NLP methods, we conclude that they are effective tools to classify news articles as real or fake. They act as a strong and solid foundation which can be augmented by more advanced algorithms.
