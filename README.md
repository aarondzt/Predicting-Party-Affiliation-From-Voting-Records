# Predicting party affiliation from voting records

## Contents
* [Data source](https://archive.ics.uci.edu/ml/datasets/congressional+voting+records)
* [Data files](Data)
* [Code/report](Congress.ipynb)

## Overview
How members of the Democratic and Republican parties vote is a strong indicator of a particular political climate. In this [dataset, provided by the UCI Machine Learning Repository](https://archive.ics.uci.edu/ml/datasets/congressional+voting+records), votes on 16 key issues by the 1984 98th House of Representatives were identified as yea, nay, or unknown. 

## Goals: To answer the following questions
* What were the issues that most separated Democrats and Republicans in this Congress?
* Can an unsupervised learning algorithm (PCA) reveal a Democrat-Republican split among the observations?
* Can a more sophisticated machine learning model outperform a benchmark model that simply classifies observations with regards to the most partisan issue?

## Motivation and background
[The application of data science to political questions](https://nymag.com/intelligencer/2020/07/david-shor-cancel-culture-2020-election-theory-polls.html) has become very important to understanding and influencing the political process. Because obtaining this data can be rather difficult, I decided to start with the already-cleaned publically available dataset provided by UCI. I intend for this project to develop my understanding of the structure of political data and how machine learning models respond to them.

## Data analysis process
Given that some issues are highly partisan (e.g. 98% of Republicans and 7% of Democrats) voted for "physician-fee-freeze", I decided to compare my machine learning models to a benchmark model where all yea votes for this issue were classified as Republicans, and all nay votes as Democrats. This led to a balanced accuracy (due to there being more Democrats than Republicans; accuracy hereafter) of 95.9% . In exploratory analysis, I ran a two component PCA, and indeed, the first PC separated observations along party lines. Next, I ran three machine learning models, a logistic regression, a decision tree, and a random forest. The decision tree ended up being logically identical to the benchmark model. The logistic regression and random forest models outperformed the benchmark model, with 96.6% and 98.5% accuracy in the test set. This indicates that a more sophisticated machine learning model can be more successful at categorizing anomolous Democrats and Republicans who do not strictly vote along party lines. 

## Future directions
In the future, I am interested in utilizing a similar analytic paradigm to look at a [larger and more contemporary dataset, provided by the federal government](https://www.govtrack.us/congress/votes). This dataset also includes the names of the politicians, and it would be interesting to formally identify the most "classifiable" and "unclassifiable" politicians, and the issues that unite and divide us today.

## Project Info
<pre>
Contributors : <a href=https://github.com/aarondzt>Aaron Tan</a>
</pre>

<pre>
Languages    : Python
Tools/IDE    : Anaconda
Libraries    : numpy, pandas, matplotlib, seaborn, sklearn, statsmodels
</pre>

<pre>
Date published     : 10.29.2020
</pre>
