# Twitter - Coronation of King Charles III
The code of this repository was used to create a social media analysis on the topic "Coronation of King Charles III".
This project is part of the seminar "Current topics in Machine Learning: Social Media as Research Data" (SS 2023) at the University of Passau.
The seminar was supervised by Prof. Dr. Florian Lemmerich and Max Klabunde.
If not stated otherwise, the code of this repository is written by Lukas Krodinger.

## Data
Twitter states in their [Developer Agreement and Policy](https://developer.twitter.com/en/developer-terms/agreement-and-policy) that one is not allowed to publish the data without permission. Therefore, the used data is not available in this repository.

## Requirements
In order to use the code of this repository you need the following things:
- Twitter bearerToken
- Anaconda environment 'twitter-coronation'

### Twitter bearerToken
You need a Twitter bearerToken in order to interact with the Twitter API.
You can create such a token by creating an app for an [access plan](https://developer.twitter.com/en) of your choice.
The token has to be saved in a file named 'TwitterClient.py'. Therefore, you can create a copy of demoTwitterClient.py, rename it and insert your token there.

### Anaconda environment 'twitter-coronation'
In order to run the notebooks you need several packages. The easiest way to set everything up is as follows:
1. Download and install [Anaconda](https://www.anaconda.com/download)
2. Run 'conda env create -f environment.yml' to create a anaconda environment with all dependencies
3. Run 'conda activate twitter-coronation' to activate the environment
4. Run 'jupyter notebook' to start a jupyter server

## Usage
All notebooks can be run in arbitrary order.
The following usage examples require [recent search](https://developer.twitter.com/en/docs/twitter-api/tweets/search/api-reference/get-tweets-search-recent). Make sure that your plan supports this API endpoint and that you have enough contingent available.

### Analyse Tweets
In order to analyse tweets you can do the following steps:
1. Run twitterDownloader.ipynb for a search term of your choice
2. Optional: Run twitterFilterer.ipynb to filter the data for your needs
3. Run twitterAnalysis.ipynb to get a simple sentiment and topic analysis for your data

### Analyse Users
In order to analyse user data you can do the following steps:
1. Create a txt file with one Twitter username per line for each user you want to download
2. Run userDownloader.ipynb using load_users_usernames to download the initial users
3. Run followingDownloader.ipynb to download all following users of your initial ones
4. Run egoNet.ipynb to create a (ego) network for your users and following users
5. Use a graph visualisation tool (e.g. [Gephi](https://gephi.org/)) to evaluate, post-process and visualize the users' relations
