# Reproducible Research: Peer Assessment 1


## Loading and preprocessing the data


```r
if (!file.exists("activity.csv")) {
  download <- "https://d396qusza40orc.cloudfront.net/repdata%2Fdata%2Factivity.zip"
  tempfile <- "temp.zip"
  download.file(download, tempfile, method = "curl")
  unzip(tempfile)
}  

activity <- read.csv("activity.csv")
```


## What is mean total number of steps taken per day?

```r
applied <- aggregate(steps ~ date, data = activity, FUN="sum", na.rm=TRUE)
hist(applied$steps)
```

![](PA1_template_files/figure-html/unnamed-chunk-2-1.png)<!-- -->

### Calculate Mean and Median

```r
datamedian <- median(applied$steps)
datamean <- mean(applied$steps)
```

The mean is 1.0766189\times 10^{4} and median is 10765

## What is the average daily activity pattern?



## Imputing missing values



## Are there differences in activity patterns between weekdays and weekends?
