# Job Opportunities using Twitter
## Twitter Sentiment Analysis using Python

[![Generic badge](https://img.shields.io/badge/Sentiment-Analysis-teal.svg?style=for-the-badge)](https://github.com/vinitshahdeo/jobtweets) 
[![Generic badge](https://img.shields.io/badge/Twitter-API-orange.svg?style=for-the-badge)](https://twitter.com/Vinit_Shahdeo) [![Generic badge](https://img.shields.io/badge/Job-Opportunities-blue.svg?style=for-the-badge)](https://github.com/vinitshahdeo/jobtweets/raw/master/report/REPORT.pdf) 

#### The project is about searching the twitter for job opportunities using popular [#hashtags](https://twitter.com/search?q=%23jobs&src=typd) and applying sentiment analysis on this.

#### Few popular hashtags - 
### `#Jobs` `#Careers` `#JobOpening`
### `#FreshHiring` `#Recruitments` `#JobOpportunities`

### Motivation

Twitter is all about enabling users to send out brief messages to large audiences. If you haven’t been taking advantage of Twitter as a job search tool, it’s time to jump in. When used intelligently, Twitter can have a profound impact on your job search success – or lack thereof. Small steps can help you turn Twitter into your own personal job search platform. Try them today and see what a difference they make in your overall job search success.

### About the Project

#### What is Sentiment Analysis?

Sentiment Analysis is the process of ‘computationally’ determining whether a piece of writing is positive, negative or neutral. It’s also known as opinion mining, deriving the opinion or attitude of a speaker.

#### Steps involved in this project

3 major steps in `jobtweets.py` code :

1. Authorize twitter API client.
2. Make a GET request to Twitter API to fetch tweets for a particular query.
3. Parse the tweets. Classify each tweet as positive, negative or neutral.

[![Made with Python](https://forthebadge.com/images/badges/made-with-python.svg)](https://github.com/vinitshahdeo/jobtweets) [![Made with love](https://forthebadge.com/images/badges/built-with-love.svg)](https://github.com/vinitshahdeo) [![Makes people smile](https://forthebadge.com/images/badges/makes-people-smile.svg)](https://github.com/vinitshahdeo)
#### Explanation

- First of all, I've created a **TwitterClient** class. This class contains all the methods to interact with Twitter API and parsing tweets. We use `__init__` function to handle the authentication of API client.

- In **get_tweets** function, I have used `fetched_tweets = self.api.search(q = query, count = count)` to call the Twitter API to fetch tweets. 'query' is basically, the hashtags.

- In **get_tweet_sentiment** I've used textblob module. 
`analysis = TextBlob(self.clean_tweet(tweet))`

- **clean_tweet** method to remove links, special characters, etc. from the tweet using some simple regex.

- I have used **sentiment.polarity** method of **TextBlob** class to get the polarity of tweet between -1 to 1.

```python
if analysis.sentiment.polarity > 0:
       return 'positive'
elif analysis.sentiment.polarity == 0:
       return 'neutral'
else:
       return 'negative'
```
- Finally, I've printing the percentage of positive, negative and neutral tweets about a **#hashtag**(query).

**Note** - You can change the hashtags by changing `query = 'WRITE YOUR OWN HASHTAG'`

```python
tweets = api.get_tweets(query = 'Job Opportunities', count = 500)
```

### Libraries Used

[![Generic badge](https://img.shields.io/badge/Python-Tweepy-blue.svg?style=plastic)](http://docs.tweepy.org/en/v3.5.0/) [![Generic badge](https://img.shields.io/badge/Python-TextBlob-blue.svg?style=plastic)](https://textblob.readthedocs.io/en/dev/)

- [Tweepy](http://docs.tweepy.org/en/v3.5.0/) - **tweepy** is the python client for the official [Twitter API](https://developer.twitter.com/en/docs).
- [TextBlob](https://textblob.readthedocs.io/en/dev/) - **textblob** is the python library for processing textual data.

### Installation

- Install **Tweepy** using pip command: `pip install tweepy`
- Install **TextBlob** using pip command: `pip install textblob`

### How to run?

- Get started with **Twitter API** by signing up for [Twitter Developer Account](https://dev.twitter.com/apps).
- In order to fetch tweets through **Twitter API**, you need to register an App through your twitter account. 
- Follow this [link](https://apps.twitter.com/) to register your app.
- Get the API keys. Need help, follow this [link](https://themepacific.com/how-to-generate-api-key-consumer-token-access-key-for-twitter-oauth/994/)
- Open `jobtweets.py` and replace '**XXXXXXXXXXXX**' with your API keys.

```python

        consumer_key = 'XXXXXXXXXXXX'
        consumer_secret = 'XXXXXXXXXXXX'
        access_token = 'XXXXXXXXXXXX'
        access_token_secret = 'XXXXXXXXXXXX'

```
- Run `python jobtweets.py`
- It may take a minute to fetch the results from **Twitter**. Make sure that you've proper internet connection.

### Project Reports

- [Download](https://github.com/vinitshahdeo/jobtweets/raw/master/report/presentation.pptx) the presentation.
- [Download](https://github.com/vinitshahdeo/jobtweets/raw/master/report/REPORT.pdf) project report.

### Useful Links

 - [Getting started with Twitter Developer Platform](https://developer.twitter.com/en/docs/basics/getting-started)
 - [How to Install PIP for Python on Windows, Mac and Linux](https://www.makeuseof.com/tag/install-pip-for-python/)
 
### Need help?

Feel free to contact me @ [vinitshahdeo@gmail.com](https://mail.google.com/mail/)

### License

MIT &copy; [Vinit Shahdeo](https://github.com/vinitshahdeo/jobtweets/blob/master/LICENSE)


[![GitHub license](https://img.shields.io/github/license/vinitshahdeo/jobtweets.svg?style=social)](https://github.com/vinitshahdeo/jobtweets/blob/master/LICENSE) 
[![GitHub forks](https://img.shields.io/github/forks/vinitshahdeo/jobtweets.svg?style=social)](https://github.com/vinitshahdeo/jobtweets/network) [![GitHub stars](https://img.shields.io/github/stars/vinitshahdeo/jobtweets.svg?style=social)](https://github.com/vinitshahdeo/jobtweets/stargazers) [![GitHub followers](https://img.shields.io/github/followers/vinitshahdeo.svg?label=Follow&style=social)](https://github.com/vinitshahdeo/)
