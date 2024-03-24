# Global News Engagement on Social Media

Taken from [Kaggle](https://www.kaggle.com/datasets/kanchana1990/global-news-engagement-on-social-media).

## Objective

Find out if the topics of articles have anything to do with social media engagement by first performing clustering, and then fitting classifier models.

## Define engagement ranges

Here we establish metrics for how we classify articles. How do we know that an article is viral? Conversely, how do we know that an article is underperfoming in terms of engagement? We will look to the histograms of metrics to establish ranges.

Based on the histograms below, it seems that majority of the articles fall in certain ranges, save for highly viral articles that are outliers, as you will see in the `max_value`.

Hence, we will establish the following rules:

1. An **underperforming** article's metrics fall below the 25th percentile of any of the metrics.
2. An **average** article's metrics fall in the 25th-90th percentile of metrics.
3. A **viral** article should have all their metrics beyond the 90th percentile.
4. If an article does not fall squarely in any of the above categories, they will be tagged as **mixed**

## Check the composition of article performance

* There are 1863 average performance articles
* There are 1060 mixed performance articles
* There are 687 underperforming articles
* There are 124 viral articles

# Does article content dictate social media engagement?

Based on the above clustering, we only get 2 general topics. This means that potentially, the topic of an article does not affect its social media engagement, but rather some external factor like ad spend, copywriting, etc. does.

However, to conduct a thorough investigation, we will attempt to create a machine learning model that takes article features and predicts its social media engagement level (mixed, underperforming, average, viral).

Hence, this is a **classification** problem.

# Conclusion

Based on the test scores, it seems like none of the classifier models are able to detect a meaningful relationship between article content and social media engagement.

Based on the clustering results, we see that the articles revolve around two main topics as well and when compared to the labelled graph, it seems like there is no clear divide between article content and social media engagement.