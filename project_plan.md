# Project Plan
#### Joey Livorno | gil15@pitt.edu | 2.6.2020

## Introduction
Politicians are notorious for flip-flopping on their political positions. Our president is no different. Donald Trump has cycled through countless opinions in the recent age of Big Data, and conveniently enough, this is well documented on his Twitter feed. In this project, I will attempt to analyze the sentiment of Trump's tweets as they relate to prominent issues in American politics. The goal will be to have verifiable data that either supports Trump's tendency to flip political camps, or shows that Donald Trump has remained steadfast on certain issues.

## Data
The first step to this project is acquiring the data that is needed to make the analysis, which will simply be a collection of Trump's tweets. Luckily, there is a website that provides access to all of the President's tweets in the form of a csv file. This is the primary collection of data that I will be using.

The csv file contains about 40,000 tweets, dating back to 2009. Each row of data contains the source of the tweet (i.e., IPhone, Android, Web App, etc.), the contents of the tweet, the date it was posted, the retweet and favorite counts, whether or not it was a retweet, and an ID that makes the tweet unique. I will take several steps to clean up the data. Firstly I will narrow the contents down to just his own tweets, meaning retweets will be removed. I may decide to include these for alternate tests, but for now I only want to consider things that Trump said himself. Next, I will need to create a tokenized version of each tweet that removes punctuation, as I will only be considering the lexical items of each tweet and do not want the other strings diluting the data. Finally I will need to remove the words from the tokenized tweets that do not add anything practical to the sentiment of the tweets. Words like "the", "is", "he", and "she" would all be removed.

I also have the option of moving the rows into more specific DataFrames by the political topic that they refer to. For example, any tweets that contain the words "Russia" or "Putin" might be put into a single DataFrame. I'm not sure if this will add any convenience, but I will consider it.

## Analysis
At this point, the data is ready to be analyzed. The research question that I wish to answer is: Does the sentiment of Donald Trump's tweets regarding certain issues over time suggest that his political stances have flipped? My initial hypothesis is that he has flipped camps on many issues, though I do not know to what degree he has.

In order to run a Sentiment Analysis, I will need a standard collection of words to compare the tweets to. In sentiment analysis, each of these words are given a sentiment score, usually on a ternary scale of -1 to 1 (-1 being negative, 0 being neutral, and 1 being positive). Once I have this, I can simply use it as a reference manual as I parse through the tweets, scoring each word and giving each tweet an overall score. I plan on storing these sentiment scores in the original DataFrame so that they may be easily referenced later on.

Another alternative option is to use a Python library that has sentiment analyis capabilities. After doing some online research, one library capable of doing this is called textblob. I may just end up using this as a backup reference to make sure my own code is functional, as I think that using a library to do all the work for me defeats the purpose of the assignment.

## Presentation
The final step will be to arrange my findings in a clean and orderly jupyter notebook file and present them. Here is a list of goals that I wish to achieve for this step:
- commit and push my work much more often so that I have a clear history of my progress
- make descriptive comments that outline in pseudocode every step of my project's code
- elaborate on my findings periodically with the use of markdown cells
- find a use for a graph type that I have not used yet
- create a set of notecards that will help me deliver a clear and extemporaneous speech (I learned in my public speaking class last semester that note cards == success)

## Conclusion
From this project, I hope to gain experience with the Python libraries we have talked about so far, as well as new ones that I will discover that may help me with my analysis. I will measure my overall success by assessing my ability to manipulate data, my ability to write effective code that will answer my research question, and my ability to use statistical methods to draw real-world conclusions based on my analysis by the time I have completed the course.
