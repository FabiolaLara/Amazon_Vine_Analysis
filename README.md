# Amazon_Vine_Analysis
Bid Data, using colab, pandas, RDS, AWS

1.  Overview of the analysis: Explain the purpose of this analysis.
  
  The purpose for the deliverable 2 is to retrieve information througth the use of PySpark, or Pandas or PgAdmin. 
In the case of PySpark que had to make a conncetion to AWS to extract our data base, so all the work made was online. Secondly, while using Pandas in jupyter notebook we import the data base from AWS to our computer so the data base can be loaded in jupyter. And thirdth using PgAdmin a daba base can be created but it wasn´t related to aws, I mean, we create the data base locally so we have to create the tables using some queries and then populate the data base importing our local data base.
  
While using each tool to manage the data base, this challenge asked to retrieve some data frames, or tables in order to know some information where we can see statisticall information, for example, we can determine the number of five stars give by the clients when they made a purchase and the number of five stars given when they did´t buy the product finally, so we can have a best landscape in the behaviour of our clients versus the products, I mean, we can realized or make some hypotesis how clients are accepting the product.


2.  Results: Using bulleted lists and images of DataFrames as support, address the following questions:

+ How many Vine reviews and non-Vine reviews were there?

To get these values, the challege asked to make two filters before, the first one was:  to get the votes where total_votes column is equal to or greater than 20, this was made in this way in order to pick reviews that are more likely to be helpful and to avoid having division by zero errors later on. The second filter was: once made the previous request, we had to retrieve all the rows where the number of helpful_votes divided by total_votes is equal to or greater than 50%, this way was made in order to focus in those products where their votes represent those who have more impact for our analysis.

Having these two filters first, we were filterin in a table where the total of rows was reduced considerably, so we just have 61,948 rows. When we make the filter to get the vine reviews where vine column is 'Y' (yes), we get: 334 raws. On the other hand when filtering to get the values wher vine = 'N', we get te total amount of raws equal to 61,614. 

The analysis for the vine_table_df retrieved a total of 4,850,360 reviews, to get this value, we count the values for the review_id column.

+ How many Vine reviews were 5 stars? and how many non-Vine reviews were 5 stars?

The total of reviews with 5 stars were those where vine column was equal to 'Y' (yes), and there were also 5 stars for the star_rating column, getting the amount of: 2,637,198. In comparision with these raws where total of reviews had 5 stars reviews but 


+ What percentage of Vine reviews were 5 stars? What percentage of non-Vine reviews were 5 stars?

3.  Summary: In your summary, state if there is any positivity bias for reviews in the Vine program. Use the results of your analysis to support your statement. Then, provide one additional analysis that you could do with the dataset to support your statement.
