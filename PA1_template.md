# Reproducible Research: Peer Assessment 1


## Loading and preprocessing the data

```r
mydata <- read.csv(unzip("activity.zip"))
```


## What is mean total number of steps taken per day?

```r
mygraph.data <- aggregate(steps ~ date, mydata, sum)
hist(mygraph.data$steps)
```

![](PA1_template_files/figure-html/unnamed-chunk-2-1.png)

```r
#calculate mean
mean(mygraph.data$steps)
```

```
## [1] 10766.19
```

```r
#calculate median
median(mygraph.data$steps)
```

```
## [1] 10765
```



## What is the average daily activity pattern?

```r
mygraph.data <- aggregate(steps ~ interval, mydata, mean)
plot(mygraph.data$interval, mygraph.data$steps, type = "l")
```

![](PA1_template_files/figure-html/unnamed-chunk-3-1.png)

```r
#pick interval with most steps
mygraph.data[which.max(mygraph.data$steps),]
```

```
##     interval    steps
## 104      835 206.1698
```



## Imputing missing values



## Are there differences in activity patterns between weekdays and weekends?
