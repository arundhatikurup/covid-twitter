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
