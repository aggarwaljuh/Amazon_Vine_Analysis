# Amazon_Vine_Analysis

## Purpose
The purpose of this study is to determine what if the Vine programs poses any bias to video games reviews. We want to tell SellBy the results so that they can make any changes they wish to.

## Results
### How many Vine reviews and non-Vine reviews were there?
After filtering by total votes over 20, helpful votes over 50%, 98 reviews were made by people who paid for Vine.
```
paid_vine_df=helpfulvine.filter(helpfulvine["vine"]=='Y')
paid_vine_df.count()
```
```
98
```
After filtering by total votes over 20, helpful votes over 50%, 43466 reviews were made by people who did not pay for Vine.
```
unpaid_vine_df=helpfulvine.filter(helpfulvine["vine"]=='N')
unpaid_vine_df.count()
```
```
43466
```
### How many Vine reviews were 5 stars? What percentage of Vine reviews were 5 stars?  
49 Vine reviews were 5 stars which is 50% of reviews.

```
paid_vine_5star_df=paid_vine_df.filter(paid_vine_df["star_rating"]==5)
paid_vine_5star_df.count()
```
```
49
```
```
fivestarpaid=paid_vine_5star_df.count()/paid_vine_df.count()
fivestarpaid
```
```
.5
```

### How many non-Vine reviews were 5 stars?  What percentage of non-Vine reviews were 5 stars?
16731 Vine reviews were 5 stars which is 38% of reviews.


```
unpaid_vine_5star_df=unpaid_vine_df.filter(unpaid_vine_df["star_rating"]==5)
unpaid_vine_5star_df.count()
```
```
16731
```
```
fivestarunpaid=unpaid_vine_5star_df.count()/unpaid_vine_df.count()
```
```
0.3849215478765012
```

## Summary
There is postivity vias for reviews from the Vine program as those part of the Vine program had 12% more 5 star reviews. However due to small sample sizes this may not be completly comparable or significant. 
We can do a t-test to determine if the two groups are significantly different.
