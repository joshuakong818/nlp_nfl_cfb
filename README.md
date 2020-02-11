# Project 3: Web APIs & NLP

## Problem Statement

Using [Pushshift's](https://github.com/pushshift/api) API, collect 10,000 posts each from nfl and cfb subreddits. After posts are collected, use Natural Language Processing (NLP) to train logistic regression and decision tree classifiers on which subreddit a given post came from. 

## Description of Data

### Data Dictionary

|Feature|Type|Dataset|Description|
|---|---|---|---|
|title|string|combined_df|title text from post| 
|selftext|string|combined_df|body text from post| 
|merged|string|combined_df|title and selftext combined| 
|subreddit/sr_target|int|combined_df/term_df|1 indicates post came from nfl subreddit, while 0 indicates post came from cfb subreddit|
|game|string|term_df|value of 1 denotes existence of phrase 'game'|
|player|string|term_df|value of 1 denotes existence of phrase 'player'|
|football|string|term_df|value of 1 denotes existence of phrase 'football'|
|team|string|term_df|value of 1 denotes existence of phrase 'team'|
|season|string|term_df|value of 1 denotes existence of phrase 'season'|
|teams|string|term_df|value of 1 denotes existence of phrase 'teams'|
|vs|string|term_df|value of 1 denotes existence of phrase 'vs'|
|coach|string|term_df|value of 1 denotes existence of phrase 'coach'|
|games|string|term_df|value of 1 denotes existence of phrase 'games'|
|play|string|term_df|value of 1 denotes existence of phrase 'play'|
|last|string|term_df|value of 1 denotes existence of phrase 'last'|
|first|string|term_df|value of 1 denotes existence of phrase 'first'|
|yards|string|term_df|value of 1 denotes existence of phrase 'yards'|
|qb|string|term_df|value of 1 denotes existence of phrase 'qb'|
|years|string|term_df|value of 1 denotes existence of phrase 'years'|
|td|string|term_df|value of 1 denotes existence of phrase 'td'|
|good|string|term_df|value of 1 denotes existence of phrase 'good'|
|pass|string|term_df|value of 1 denotes existence of phrase 'pass'|
|pro|string|term_df|value of 1 denotes existence of phrase 'pro'|
|run|string|term_df|value of 1 denotes existence of phrase 'run'|
|playoffs|string|term_df|value of 1 denotes existence of phrase 'playoffs'|

### Source

nfl subreddit can be found here: https://www.reddit.com/r/nfl/
cfb subreddit can be found here: https://www.reddit.com/r/CFB/

### Target

logistic regression and random forests

## Model performance on training/test data

The count vectorized data was fit on logistic regression and random forest models. The accuracy scores on the training and testing data for logistic regression were higher than those from the random forests model. Therefore, the logistic regression model was selected for production.

|Model|Train accuracy|Test accuracy|
|---|---|---|---|
|Logistic regression|.92|.88| 
|Random forests|.85|.81|

## Primary findings/conclusions/recommendations

NFL subredditers were found to be more sophisticated, happier, varied, and results focused compared to their CFB counterparts. Those who posted on the NFL subreddit, posted titles with more characters on average, had posts that were generally more positive, had top words that were similar to those from the cfb subreddit, and heavily-present words that focused on results, such as, first, yards, td, and playoffs. These insights can prove rather useful for those looking to market to fans of the NFL.

## Next steps

To gather deeper insights, a better collection of stop words could have been used. While many team, player, and coach names, in addition to, jargon too specific for a class, and features that were not statistically significant were excluded, a better job excluding those aforementioned terms could have performed. Doing this would have resulted in frequent words appearing that would  have less readily been classified as being from the nfl or cfb subreddit.  