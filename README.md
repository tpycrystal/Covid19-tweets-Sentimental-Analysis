# Covid19-tweets-Sentimental-Analysis (07/2020 - 08/2020)  

### Import Dataset  
  Read csv : 'https://raw.githubusercontent.com/gabrielpreda/covid-19-tweets/master/covid19_tweets.csv'  
### Preprocess and prepare our text data for Sentimental Analysis
* **Select columns and preprocess**
  1. Turn user_name into categorical variable
  2. Use **"cat.codes"** : assign unique numercial value to each of the unique user names
  3. Turn Date column into Date only  
  
 * **Data Cleansing**  
   1. Remove url
   2. Converting all tweets to lowercase
   3. Remove punctuations  
   **str.maketrans( , , )** : will trans every first argument to the second arguments, and it will remove everything in the third argument
   4. Remove stopwords  
   Remove Covid-related words since these are useless for my analysis  
   
   
### Sentimental Analysis 
* **Adding Scores and Labels to the DataFrame**  
  Use **SentimentIntensityAnalyzer()** to determining whether a piece of writing is **positive, negative or neutral**. It will return score of positive, negative, neutral, 
  and coompound score. The Compound score is a metric that calculates the sum of all the lexicon ratings which have been normalized between 
  -1(most extreme negative) and +1 (most extreme positive).  
  
* **Give each Tweet a label based on the compound score**  
  Positive sentiment : (compound score >= 0.05)  
  Neutral sentiment : (compound score > -0.05) and (compound score < 0.05)  
  Negative sentiment : (compound score <= -0.05)  
 
### Plotting  
* **barplot the amount of positive, negative, and neural tweets**  
From July to August in 2020 there are more positive tweets with 70049 tweets compare to the others:  62520 Neural tweets, and 46539 Negative tweets.  
* **Daily Tweets Sentimental Analysis**  
Using plotly to plot, shows label, date, and counts of each type of tweets.    
### Conclusion  
There is a similar trend among three types of tweets. Most of the time there are more positive tweets, I did notice during 08/14 to 08/16 the amount of neural tweets exceed positive.

### Problem
The difficult I encountered is that plotly couldn't show on github. So I export the figure as a png file.
  
