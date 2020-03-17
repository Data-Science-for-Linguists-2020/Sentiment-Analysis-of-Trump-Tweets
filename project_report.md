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
This is my first *actual* progress report. In this section of my project, I have accomplished much of what is encompassed by the Basic Data Processing category of Homework 2. First, I downloaded a .csv copy of Donald Trump's Twitter feed from the [Trump Twitter Archive](http://www.trumptwitterarchive.com/about), a website that tracks the tweets of Trump and many other prominent politicians that was created by Brendan Brown. I then created my [jupyter notebook](https://https://github.com/Data-Science-for-Linguists-2020/Sentiment-Analysis-of-Trump-Tweets/blob/master/code/project_code.ipynb) and entitled it *Project Code*. I used the normal libraries (numpy, pandas, etc.), though I also included a useful library that I found called [TextBlob](https://https://textblob.readthedocs.io/en/dev/). This library can be used for a multitude of things related to Natural Language Processing, however I will be using it to perform quick sentiment analyses on the text of each tweet. I also imported two dictionaries from a snippet of [code](https://github.com/joeylivorno/emot/blob/master/emot/emo_unicode.py) I found on GitHub user NeelShah18's page. I emailed Neel asking if it was okay to use his code, and he allowed it!

The next step was to begin the actual data manipulation. The first thing I did was read the .csv file into a dataframe, and then I printed a preview to see what I was working with. I saw that each row contained a source, the tweet itself, the data and time it was posted, the number of retweets and favorites, and whether or not it was a retweet. This was a great place to start, but the tweets needed a bit of fluffing to be completely workable. Firstly, I attempted to replace the emojis with text using Neel's code, but I ran into an error that I have not yet solved. For now, this can stay. I will attempt to make this code work for my purposes, but I may need to just find a new library. Secondly, I added two columns to each of the rows: those being polarity and subjectivity. I got these values from textblob for each tweet through the use of a lambda function, and then I joined the columns to the existing dataframe.  Finally, I needed a way to group my tweets together chronologically, and so I figured that extracting the year from the timestamp and making 'year' its own column was the best way to accomplish this. I achieved this by converting the timestamp to a python timestamp datatype and then isolating the year value. I then added these values to the dataframe.

The last step in my initial data processing, since the data was now workable as a whole, was to divide them into subcategories based on political topics. Since foreign affairs has been a hot button issue recently, I decided to begin by investigating these topics, but this is subject to change has my project evolves. I did this by extracting tweets that contained keywords that are associated with certain issues. For example, the subset 'nkorea' is made up of tweets that contain words such as 'North Korea,' 'Pyongyang,' and 'Jong-Un.' These searches left me with a fair bit of twitter data, especially just for investigating a single person. My fear though, is that I do not have enough data. In the future, my challenge will be to do one of two things: 1) find new ways to include a larger subset of tweets pertaining to certain issues (either through more keywords or in more creative ways) or 2) choosing new issues that have a larger volume of data to work with.

## March 16, 2020
This is my second project report. In this report, I will discuss the final steps I took to prepare my data for analysis, the analyses I have begun, and the license that I have created/how I plan to share the data.

#### Final Data Processing
Much of the processing had already been completed in the first section of my report, though I made some key changes in this one. First, I added a new field that holds the tokenized and lowercased form of the tweet content. This will allow me to find keywords much more accurately. After this, I changed the subsets to only search for these lowercased forms of words, and I ended up finding more matches. Finally, I printed some basic statistics of the data like size and shape, and then pickled the final form of the data.

#### Analysis
The first section of analysis in my code is for exploratory purposes. I retrieved the statistics about various points in the data such as retweets, favorites, and the volumes of tweets per year, and I used charts to visualize my findings.

The second section was a more linguistic analysis of the data. I grouped the tweets by year and then found the averages of the polarities of the tweets for each group. Using a bar graph, I could make some preliminary judgements regarding the sentiment of Trump's tweets, specifically that they have been trending negatively in recent years. Next, I did the same for the subsets of the tweets (russia, iran, north korea). Here, I found that the sentiment of a certain year's tweets was consistent with political events from that time. For example, I found that Trump tweeted rather positively of Russia while Obama was in office, and negatively of them while he was in office, but only when it suited him. Specifically, I found that in 2019, the same year as the [Mueller Report](https://en.wikipedia.org/wiki/Mueller_Report) was released, the sentiment of Trump's tweets towards Russia drastically increased. Very interesting to say the least...

#### Data and Licensing
For my [license](https://github.com/Data-Science-for-Linguists-2020/Sentiment-Analysis-of-Trump-Tweets/blob/master/LICENSE.md), I used A [GNU General Public License](https://www.gnu.org/licenses/gpl-3.0.en.html). I chose this license because it is a requirement of NeelShah18's [license](https://github.com/NeelShah18/emot/blob/master/LICENSE) that I use the same one if including it in my data.

As far as my actual data, the Trump Twitter Archive is free to use (and it doesn't seem to have a license anywhere), and I give credit to its founder [Brendan Brown](https://github.com/bpb27) throughout my code documentation. Because of this, I am justified in creating the derivative dataset in which I include polarity, subjectivity, tokenized content, etc.

#### Sharing
To share my data, I have included a copy of the original .csv file in my 'data/' directory, along with a pickled form of the derivative dataset I created. My license specifies that anyone will be allowed to use my data so long that they state any changes made, disclose the source, and use the same license. 
