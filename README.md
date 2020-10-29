# Starbucks Capstone Challenge
Project in Data Scientist Nanodegree of Udacity

### Table of Contents

1. [Installation](#installation)
2. [Project Motivation](#motivation)
3. [File Descriptions](#files)
4. [Results](#results)
5. [Licensing, Authors, and Acknowledgements](#licensing)

## Installation <a name="installation"></a>

Other than Python 3, we are using Surprise for this project. You can install it using pip install surprise.

## Project Motivation<a name="motivation"></a>

It is the Starbuck's Capstone Challenge of the Data Scientist Nanodegree in Udacity. The Starbucks data set contains description of offers, demographic of customers and their transactions. We want to make a recommendation engine that recommends Starbucks which offer should be sent to a particular customer.


## File Descriptions <a name="files"></a>


The data is contained in three files:
- `portfolio.json` - containing offer ids and meta data about each offer (duration, type, etc.)
- `profile.json` - demographic data for each customer
- `transcript.json` - records for transactions, offers received, offers viewed, and offers completed

Here is the schema and explanation of each variable in the files:

`portfolio.json`
- id (string) - offer id
- offer_type (string) - the type of offer ie BOGO, discount, informational
- difficulty (int) - the minimum required to spend to complete an offer
- reward (int) - the reward is given for completing an offer
- duration (int) - time for the offer to be open, in days
- channels (list of strings)

`profile.json`
- age (int) - age of the customer
- became_member_on (int) - the date when customer created an app account
- gender (str) - gender of the customer (note some entries contain 'O' for other rather than M or F)
- id (str) - customer id
- income (float) - customer's income

`transcript.json`
- event (str) - record description (ie transaction, offer received, offer viewed, etc.)
- person (str) - customer id
- time (int) - time in hours since the start of the test. The data begins at time t=0
- value - (dict of strings) - either an offer id or transaction amount depending on the record

The code is divided into two files:

Data_Feature_Engineering.ipynb : Has all data cleaning and wrangling.
AI_Models_Recommendations.ipynb  : Has all  code for our recommender system.

## Results<a name="results"></a>

The main findings of the code can be found at the post available **[here](https://medium.com/@hema.chhatpar/starbucks-anyone-29a406da3dc)**.

The goal of this project is to build a recommendation engine that suggests the best offers to present to a customer.

We decide to build a recommender system for sending best offers to the customer. Since the recommender systems come with a cold start problem, we find best offer for new users by choosing the most popular offer among users and the best offer for starbucks in terms of gains it provides to the company.

We used Surprise to build and evaluated different algorithms and chose the best(SVD) one based on lowest RMSE(0.57). 

We also found that Discount Offer of 2 dollars off when you spend 10$ seems to be most popular among users and also the best in terms of gain for Starbucks.

## Licensing, Authors, Acknowledgements<a name="licensing"></a>

Thanks to Starbucks for the sample data.
