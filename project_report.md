# Project Report
#### Joey Livorno | gil15@pitt.edu | 2.6.2020

## February 6, 2020
This is my first project log of the term. Not much to report yet, but I'm excited to make some progress.

## February 6, 2020 (cont.)
I've finished setting up my project repository
- created README.md
- created LICENSE.md
- created project_report.md
- created project_plan.md and laid out a detailed plan of attack
- created .gitignore

## February 24, 2020
This is my first *actual* progress report. In this section of my project, I have accomplished much of what is encompassed by the Basic Data Processing category of Homework 2. First, I created my [jupyter notebook](https://https://github.com/Data-Science-for-Linguists-2020/Sentiment-Analysis-of-Trump-Tweets/blob/master/code/project_code.ipynb) and entitled it *Project Code*. I used the normal libraries (numpy, pandas, etc.), though I also included a useful library that I found called [TextBlob](https://https://textblob.readthedocs.io/en/dev/). This library can be used for a multitude of things related to Natural Language Processing, however I will be using it to perform quick sentiment analyses on the text of each tweet. I also import two dictionaries from a snippet of [code](https://github.com/joeylivorno/emot/blob/master/emot/emo_unicode.py) I found on GitHub user NeelShah18's page. I emailed Neel asking if it was okay to use his code, and he allowed it!

The next step was to begin the actual data manipulation. The first thing I did was read the .csv file into a dataframe, and then I printed a preview to see what I was working with. I saw that each row contained a source, the tweet itself, the data and time it was posted, the number of retweets and favorites, and whether or not it was a retweet. This was a great place to start, but the tweets needed a bit of fluffing to be completely workable. Firstly, I attempted to replace the emojis with text using Neel's code, but I ran into an error that I have not yet solved. For now, this can stay. I will attempt to make this code work for my purposes, but I may need to just find a new library. Secondly, I added two columns to each of the rows: those being polarity and subjectivity. I got these values from textblob for each tweet through the use of a lambda function, and then I joined the columns to the existing dataframe.  Finally, I needed a way to group my tweets together chronologically, and so I figured that extracting the year from the timestamp and making 'year' its own column was the best way to accomplish this. I achieved this by converting the timestamp to a python timestamp datatype and then isolating the year value. I then added these values to the dataframe.

The last step in my initial data processing, since the data was now workable as a whole, was to divide them into subcategories based on political topics. Since foreign affairs has been a hot button issue recently, I decided to begin by investigating these topics, but this is subject to change has my project evolves. I did this by extracting tweets that contained keywords that are associated with certain issues. For example, the subset 'nkorea' is made up of tweets that contain words such as 'North Korea,' 'Pyongyang,' and 'Jong-Un.' These searches left me with a fair bit of twitter data, especially just for investigating a single person. My fear though, is that I do not have enough data. In the future, my challenge will be to do one of two things: 1) find new ways to include a larger subset of tweets pertaining to certain issues (either through more keywords or in more creative ways) or 2) choosing new issues that have a larger volume of data to work with.
