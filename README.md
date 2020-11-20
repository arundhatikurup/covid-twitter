# covid-twitter
Detecting the influence of COVID-19 on Social Media Discourse Using Twitter

## Problem Statement
Twitter has emerged as an important platform for online COVID-19 discourse. As a global and free platform for discussion, understandingthe COVID-19 discourse on Twitter can provide public health scientists, economists and policy makers insights on theimpacts of COVID-19 to reduce its negative impacts for the general population.

## Goals 
**Understand the Influence of COVID-19 on Textual Discourse**
1. Detect if COVID-19 has influenced a given textual discourse
2. Detect recurring patterns and features in COVID -19 implied discourse
3. Provide a categorization to understand how the nature of discourse varies across regions and in time
4. Perform topic modelling and trend analysis to understand different topics that drive discourse online

## Data Sources
**COVID Related Tweets**

[Source](https://github.com/echen102/COVID-19-TweetIDs)
- Publicly reports the Tweet ID of hundreds of millions of COVID-19 related Tweets
- Released by Ferrara et.al

**Non-COVID Related Tweets**

[Source](https://www.kaggle.com/kazanova/sentiment140)
- Contains 1.6 million tweets extracted using the Twitter API
- Annotated with values from 0 (negative) to 4 (positive) to detect sentiment
- Dataset was collected before COVID, ensuring that the Tweets are not COVID related

## Data Set
- Combine 35k Tweets from the COVID-Related and Non-COVID Related data set
- Append a target column for supervised classification (0 for non-COVID, 1 for COVID)
- COVID Dataset has 34 columns including  timestamp,  tweet_url,  hashtag,  lang,  hashtags,  urls,  fa-vorite_count, id, source, retweet_count, retweet_id, retweet_screen_name, possibly_sensitive, place, user_created_at,user_screen_name,    user_default_profile_image,    user_description,    user_favorites_count,    user_friends_count,user_listed_count,  user_location,  user_name,  user_screen_name,  user_statuses_count,  user_time_zone,  user_urls,user_verified, in_reply_to_screen_name, in_reply_to_status_id,in_reply_to_user_id and text.



## Pre-Processing
The COVID related dataset only contains Tweet ID's. To extract the rest of the features of the Tweets, we used an open source hydrator tool.  Many irrelevant columns were dropped, because we were analyzing textual discourse. Tweet content also had to be cleaned up by removing URL's, emojis, and mentions.

Next, we need to convert the text to a numerical representation called a feature vector, which we obtained using Google's BERT.

## Classification 
To classify a given Tweet as COVID or non-COVID, we first need to do feature extraction. We combined domain-specific features from pre-defined custom dictionaries based on our own intution (e.g. COVID, Coronavirus, Death) with BERT-based features. In total, we had 773 features, 5 from the custom dictionaries we defined and 768 from BERT.

We used the following classifiers to train our model:
- Random Forest
- Naive Bayes
- Support Vector Machines
- Artificial Neural Network

## Topic modelling - LDA
Topic modeling is a type of statistical modeling for discovering abstract topics that may occur within a text, which can help us to understand, organize, and summarize data of a large collection of text. We used Latent Dirichlet Allocation to build our topic model. LDA builds a topic per document model and words per topic model, modeled as Dirichlet distributions whereeach word has a relative weight.LDA is a matrix factorization technique. We make use of Python NLTK, WordNet,Gensim LDAModel on our COVID Tweet Dataset to achieve our objective.

To perform LDA on our dataset, extensive data pre-processing has been done:
- Tokenization: Split the text into sentences and the sentences into words. Lowercase the words and remove punctuation.
- Words that have fewer than 3 characters are removed
- All stopwords are removed
- Words are lemmatized — words in third person are changed to first person and verbs in past and future tensesare changed into present.
- Words are stemmed — words are reduced to their root form.

## References
[1] Emily Chen, Kristina Lerman, Emilio Ferrara. Tracking Social Media Discourse About the COVID-19 Pandemic:Development of a Public Coronavirus Twitter Data.In InJMIR Public Health Surveill 2020;6(2):e19273,2020.

[2]Karishma Sharma, Sungyong Seo, Chuizheng Meng, Sirisha Rambhatla, Yan Liu.  Covid-19 on Social Media:Analyzing Misinformation COVID-19 on Social Media: Analyzing Misinformation. InarXiv:2003.12309 [cs.SI]

[3]Laure Delisle, A.Berker, A.Kalaitzis, K.Majewski, J.Cornebise, M.Martin. A large-scale crowd-sourced analysis ofabuse against women journalists and politicians on Twitter. InNeurIPS- AI For Social Good Workshop, 2018.

[4]  Twitter, Inc.Q1 2020: Twitter’s Letter to Stakeholders.[5]Jacob Devlin, Ming-Wei Chang, Kenton Lee, Kristina Toutanova.  BERT: Pre-training of Deep BidirectionalTransformers forLanguage UnderstandingGoogle AI Language, 2018.

[6]  https://github.com/echen102/COVID-19-TweetIDs

[7]  https://www.kaggle.com/kazanova/sentiment140

[8]  https://en.wikipedia.org







