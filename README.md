# Amazon_Vine_Analysis
Bid Data, using colab, pandas, RDS, AWS

## 1.  Overview of the analysis: Explain the purpose of this analysis.
  
  The purpose for the deliverable 2 is to retrieve information througth the use of PySpark, or Pandas or PgAdmin. 
In the case of PySpark que had to make a conncetion to AWS to extract our data base, so all the work made was online. Secondly, while using Pandas in jupyter notebook we import the data base from AWS to our computer so the data base can be loaded in jupyter. And thirth using PgAdmin a daba base can be created but it wasn´t related to aws, I mean, we create the data base locally so we have to create the tables using some queries and then populate the data base importing our local data base.
  
While using each tool to manage the data base, this challenge asked to retrieve some data frames, or tables in order to know some information where we can see statisticall information, for example, we can determine the number of five stars give by the clients when they made a purchase and the number of five stars given when they did´t buy the product finally, so we can have a best landscape in the behaviour of our clients versus the products, I mean, we can realized or make some hypotesis how clients are accepting the product.


## 2.  Results

**+ 'How many Vine reviews and non-Vine reviews were there?'**

To get these values, the challege asked to make two filters before, the first one was:  to get the votes where total_votes column is equal to or greater than 20, this was made in this way in order to pick reviews that are more likely to be helpful and to avoid having division by zero errors later on. The second filter was: once made the previous request, we had to retrieve all the rows where the number of helpful_votes divided by total_votes is equal to or greater than 50%, this way was made in order to focus in those products where their votes represent those who have more impact for our analysis.

Having these two filters first, we were filterin in a table where the total of rows was reduced considerably, so we just have 61,948 rows. When we make the filter to get the vine reviews where vine column is 'Y' (yes), we get: 334 raws. On the other hand when filtering to get the values wher vine = 'N', we get te total amount of raws equal to 61,614. 

![VineProgram](/ResourcesPandas/vine_program_Y.png)
![VineProgram](/ResourcesPandas/vine_program_N.png)


**+ How many Vine reviews were 5 stars? and how many non-Vine reviews were 5 stars?**

The total of reviews with 5 stars requested by the challenge were taken fron the original vine_table_df, retrieving a total amount of: 2,961,223. From these same table, in order to get the number of raws where reviews had 5 stars and the column verified purchase = 'Y', we got a number of: 2,637,198 raws, in the same way but just changing the verified_purchase = 'N', we got 324,025 reviews. 

![vine_reviews_5_stars](/ResourcesPandas/vine_reviews_5_stars.png)


**+ What percentage of Vine reviews were 5 stars? What percentage of non-Vine reviews were 5 stars?**

The percentage of the total revies, where the star_rating colum = 5, is: 61.05%, meaning that roughly more than 50% of the reviews have 5 stars values.

To determine the percentage of these reviews where they had been evaluated with 5 star and the verified_purchase = 'Y', is: 89.06%. while for those reviews where the verified_purchase values = 'N' we got a 10.94%. 

![vine_reviews_percentage](/ResourcesPandas/vine_reviews_percentages.png)


## 3.  Summary

Lets point out that the analysis where we applied two filters first, we had that where the vine program = 'Y', the percentage that it represents is less than 1 %, meaning that the members of this program are few. In comparission where members are not part of the vine program, they form part of more than 99 percent, so it is difficult to deduct with just these number of values if there is a bias with these Vine Program. 

On the other hand when we use the origianl vine_table_df, the results change considerably. Firstable we have that, taking all the data where the star_rating = 5, the data represents a little bit more than 60 % approximately of our entire data set, then, to get the numbers of raws where a 5 star was given and the verified_purchase is equal to 'Y', the percentae obtained was 89.06% meanwhile for those values where the verified_purchase was equal 'N' we got a 10.94% of the values. 

With the mention before  we could say that the Vine program shows a kind of bias when the data set was reduced by making the two filters explained previously, however these filters are reasonably important. On the other hand when we filter data jut takig in count values where rating_stars are 5 stars, we can deduct that the percentages are very clear for our analysis, however we could have a greater bias due we have a higth percentage of products with 5 stars and where the purchase was made, but we dont know what kind of products represent the ones with a highest demand, so we should take in count some other filters if we want appreciate the kind of products that represent the most important in our data set, due this products are sold constantly and have the rate of 5 stars.

The next images show both analysis and where values were taken to provide the previous summary.
The first two images represent the data analysis when applying the two filters.

![reviews_two_filters](/ResourcesPandas/reviews_two_filters_1.png)
![reviews_two_filters](/ResourcesPandas/reviews_two_filters_2.png)

The third image shows the results when taking the data set complete, but just filtering values with 5 stars rating and verified purchase was 'Y' firstable and then when it was 'N'.

![reviews_complete_dataset](/ResourcesPandas/reviews_complete_dataset.png)









