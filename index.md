---
title       : Content Trend Explorer and Forecaster
subtitle    : Developing Data Products Coursera Course
author      : Sami Kallinen
job         : Student
framework   : impressjs        # {io2012, html5slides, shower, dzslides, ...}
highlighter : highlight.js  # {highlight.js, prettify, highlight}
hitheme     : tomorrow      # 
widgets     : []            # {mathjax, quiz, bootstrap}
mode        : selfcontained # {standalone, draft}
knit        : slidify::knit2slides

--- x:-1000 y:0 scale:5


# Exploring Tactical Content Trends and Forecasts  
## Developing Data Products Assignment*  
## Coursera Course by Johns Hopkin University    

*presentation by sami kallinen*
</br>
</br>
</br>



<span class="footnote">* The Assignment:
"OK, you've made your shiny app, now it's time to make your pitch. You get 5 slides (inclusive of the title slide)  to pitch your app. You're going to create a web page using Slidify or Rstudio Presenter with an html5 slide deck."
</span>


---  x:0 y:2500 scale:4
## 1. Why?  
        
In a world of increasing **complexity and fragmentation**, with a plethora of **content** being published every second, we need new tools to help us to **sift through this abundance** and make sense of the world. For any such tools, data is going to be central. This simple app is an experiment to figure out how such tools might work.

Possible use cases:  
- Media professionals can analyse the data and make tactical minute by minute **editorial decisions** based on their findings.
- Media producers can track their own content, **benchmark** against competitors or programmatically use the data to **optimize** their own publishing.
- The app could be developed into a **content search** or recommendation engine.



--- x:1500 y:4500 scale:3

## 2. What?
        
The [**Tactical Content Trend Explorer and Forecaster**](http://sakal.li/shinyapp) let's you explore data about how different content items are shared on social media. You can **apply different filters** to explore different aspects of a trending item. Filters include the following:

1. Defining minimum and maximum values for item **share count**.
1. Defining **share velocity**, ie. how many times the url has been shared per hour.
1. Defining **time period** by setting how many hours will be displayed.
1. Selecting **sources**. Narrowing down the sources to certain predefined types of tweeters.
1. You can also pick one item and isolate its trend plus **forecast** how it will be shared in the future.

--- x:2000 y:6200 rot:0 scale:2

## 3. How?
        
Your task in the app is to **isolate interesting items**. The upper plot contains items shared less than 5000 times with a velocity of at least 10 shares/h. Not much help, is it? By toying with the "levers" you'll find the interesting items. The plot below has max set to 1000 shares and velocity to 28.





```r
s <- data.frame(sCmax=c(5000,1000), sCmin=50, velocity=c(10,28))
p1 <- trendplot(pr, s[1,]); p2 <- trendplot(pr, s[2,]); multiplot(p1, p2)
```

![plot of chunk unnamed-chunk-2](assets/fig/unnamed-chunk-2-1.png) 


--- x:8000 y:-1200 rot:160 scale:1

## 4. Forecasting
        
The app also lets you pick **indvidual items**, explore them separately and **forecast** how they will be shared in the future. The method used is **exponential smoothing**. Not only the forecast but also the 95% respective 80% confidence intervals are plotted.

![plot of chunk unnamed-chunk-3](assets/fig/unnamed-chunk-3-1.png) 


[Please try the app here!](http://sakal.li/shinyapp)

