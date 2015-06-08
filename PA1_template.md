# Reproducible Research: Peer Assessment 1


## Loading and preprocessing the data
To start, let us set the working directory to the local cloned directory, unzip and load the data.

```r
setwd("~/Documents/Data_Science/Reproducible_Research/RepData_PeerAssessment1/")
unzip("activity.zip")
activity<-read.csv("activity.csv")
```
The dates are in "factor" format, we put them to date format with the `as.Date` function.


```r
date<-as.Date(as.character(activity$date))
activity$date<-date
```
## What is mean total number of steps taken per day?
In the following chunk of code, we compute the number of total steps per day, as well as the mean and the median of the number of steps per day.

```r
totalsteps<-aggregate(activity$steps, list(period=activity$date), sum, na.rm=TRUE)
totalsteps<-complete.cases(totalsteps)
meansteps<-aggregate(activity$steps, list(period=activity$date), mean, na.rm=TRUE)
meansteps<-complete.cases(meansteps)
mediansteps<-aggregate(activity$steps, list(period=activity$date), median, na.rm=TRUE)
mediansteps<-complete.cases(mediansteps)
```


## What is the average daily activity pattern?



## Imputing missing values



## Are there differences in activity patterns between weekdays and weekends?
