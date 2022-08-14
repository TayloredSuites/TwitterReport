# TwitterReport

- ## About the Project and Dataset

This is an educational project aimed at getting insights into a Twitter accounts data through the use of API query to extract information on tweet likes and retweets for the account up till the year 2017. The project centers on a dog rating twitter account, and deals with only information that is useful and permitted to the query maker. The information retrieved includes the tweet texts, retweet texts, timestamps  of replies, tweets and retweets, url of the tweets, tweet ids, to mention some of them. In addition to this, there was an [image prediciton file](https://github.com/TayloredSuites/TwitterReport/blob/main/twitter_archive_enhanced.csv) in which results from predictions run on the images from the tweets are made known. Dog types in the image prediction are run against what breed they actually are. Eventually, the project develops to center on only original tweets for ratings (i.e. tweets that are neither replies or retweets). 

- ## Relevant and required software

The major dependencies for the project are listed below:

1. [Anaconda](https://www.anaconda.com/) distribution, which contains Python libraries and co-dependencies. It has everything you need to get started
2. Python 3
3. NumPy
4. Pandas
5. Matplotlib
6. [Tweepy](tweepy.org) for the API query
7. Requests
8. JSON

- ## Summary of Data Wrangling

The project dealt with two types of issues to get it into a cleaned state:

1. Tidiness issues : The issues are based on [tidiness principles](https://cran.r-project.org/web/packages/tidyr/vignettes/tidy-data.html). In my dataset, I dealt with melting the 'doggo', 'floofer', 'puppo', and 'pupper' columns of the [twitter-enhanced-csv.csv](https://github.com/TayloredSuites/TwitterReport/blob/main/twitter_archive_enhanced.csv) file,  and merging the all three datasets ([twitter-enhanced-csv.csv](https://github.com/TayloredSuites/TwitterReport/blob/main/twitter_archive_enhanced.csv) , [tweets_json](https://github.com/TayloredSuites/TwitterReport/blob/main/tweets_json.txt) which is the API JSON text file , and the [image_predictions.tsv](https://d17h27t6h515a5.cloudfront.net/topher/2017/August/599fd2ad_image-predictions/image-predictions.tsv) for the image predictions) into one DataFrame.
2. Quality issues :
i. There were some rows that do not fulfill the no retweet condition.

ii. Changing the data type of several columns: timestamp datatype, 'rating_numerator' and 'rating_denominator' columns to float64 datatype, tweet_id to string (object) and not an integer, retweet_count and favorite_count  to int.

iii. 'rating_numerator' column of the enhanced table had a maximum value of 1776. It is an outlier. [Why?](http://knowyourmeme.com/memes/theyre-good-dogs-brent)

iv. 'rating_denominator' column of the enhanced table has a maximum value of 170. It is impossible.

v. Some dogs have entries in more than one stage.

vi. these are good dogs, Brent. And that's why they should not have a rating of 0, rather a rating of 10 seems more logical. I will assume that is a typo.

vii. there are some decimal dog ratings which need to be extracted.

viii. dropping all needless columns in the dataset.

ix. remove all needless rows from, the master table . This coincides with tidiness issue one. I changed all NaN values in the dog age columns to empty ones and went on to concatenate them.


- ## Summary of Findings

After wrangling the data (getting it cleaned, assigning columns and making it useful enough), certain questions were asked of it, and insights were returned as responses to them. 

It is noticed that tweets with high retweets will have high likes in turn. This means that the two are dependent on each other. However, the most retweeted image were not the most liked one. The retweets and likes were at their highest when the rating of a dog was 13/10.

When it came to the cutest dogs with the most ratings to prove it, it was puppies that stole the hearts of the audience. The most common dogs rated were the labrador and retriever, Which is understandable, as they are among the [most popular dogs in the world](https://www.akc.org/most-popular-breeds/) by the American Kennel Club.


- ## Limitations

A lot of the data was missing and it was indeed quite dirty data to work with. That meant that for certain findings such as dog ages, there was limited data. The same went for dog names, and it is a reason that data was not worked with.

Being a project that required API query, it only went to show that the best way to gather data is equally one with potential for challenges. Your access to the Tweepy API is dependent on the approval of access. I was fortunate to get it with ease.

- ## Contributing

Contributions are welcome. Keep in line with the code style and requirements. Also follow the format fot commit messages.

Thank you

