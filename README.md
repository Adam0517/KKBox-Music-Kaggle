# KKBox's Music 

## Overview

KKBox is an Asia music streaming service which is similar with Spotify. KKBox wants to predict the chances of a user listening to a song
repetitively after the first observable listening event within a time window was triggered. If there are recurring listening event triggered within a month after the user's very first observable listening event, its target is marked i, and 0 otherwise. Then, we got the data from below link,

Data Source: https://www.kaggle.com/c/kkbox-music-recommendation-challenge/data

## Step1 - Merge Datasets

There are four datasets, members, songs, train, and test data. Used Ipython called `kkbox_datacleaning` to merge them.

### Train/Test dataset

* Merge Songs with Train/Test data by song_id
* Then, merge above dataset with members by members ID

## Step2 - Missing Values 

We made a table to take a look at how much missing value we faced. Then, we went through each feature and thought how to deal with it.

### Gender 

From dataset, we could find that there are three different values in this feature.(Male,Female, Unknown)
We would fill Unknown into NaN cells of gender.

### Composer

We found that there are "Composer Unknown" and "Unknown", so we would fill NaN with "Unknown" and change "Composer Unknown" into "Unknown".

### Source_Screen_name

We found that there are two extra category "People global" and "People local" in test dataset, so we would combine these two into "Unknown" in test dataset. We would also fill "Unknown" into NaN cells.

### Song Length

We would calculate the mean of song length of train dataframe and then fill it into NaN cells for train and test dataframe.

### Genre ids

We would fill 0 into NaN cells and there are some of cells with "|" to present several styles. Then, we decided to just take first one stlye if there is a "|" in that cell.

### Lyricist 

There are around 45% missing value in Lyricist column for train and test dataframe. Moreover, it already has "Unknown" and "-" in Lyricist column. We decided to delete this feature from Train and test dataset because the rate of NaN, "Unknown", and "-" is almost 50%.

### Source_type/ Source System Tab/ Language/ Artist Name

Fill "Unknown" into NaN cells.

## Step3 - Using Tableau to do descriptive statistics chart 

Having basic information from each feature and finding that there is no strong correlation between any feature and target.

## Step4 - Applying Machine Learning to predict target value of test data

We tried to use some methods such as multi logistic regression, K-NN, Random Forest and Deep Learning Model. In the end, we chose to use deep learning model because its performance is better than others methods.

