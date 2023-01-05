
# Mox User Spending Analysis



## Problem Statement
Using one month historical transactional data, can we partition the dataset into cluster of users such that each cluster have relative spending habits.

## Question 2- Data Visualization Chart Explanation: 

[Tableau Public Link](https://public.tableau.com/app/profile/jacky1833/viz/Mox4/Dashboard1?publish=yes)

The dashboard is split into three different regions. 
![](https://github.com/Jleung1996/Mox/blob/main/picture/box.png)
The top portion(1) of the dashboard provides quick statistics regading our userbase.
Average percent salary used is derived from the total spending of this month over the salary. Note, some users have over 100% (i.e. they are using their savings/credits to fund their spending), and
users with 0 salary are excluded from the calculation. The middle portion(2) of the dashboard gives a more granular of our user statistics.
The graph shows us that majority of our users are in the age of 20-40 with an even distribution of gender. The bottom portion (3) gives statistics
regarding the different transactions. The high transactions amount days laid between Tuesday - Thursday. Majority of the spending are related travels.
Combing all three sections of the dashboard, it gives a good overview who our userbase are and their spending habits.

Our two main objectives of the dashboard are : to see which users are already-engaged and their spending patterns and to see which users
are not spending engaged and their spending habits. On the left hand side of the dashboard, there are two filters: spending engaged and encourage spending.
The spending engaged filter targets users that are in the top 75 percentile of spending. The metric for this are based on the percent salary used (0.89 or more)
. This yields us around 4565 users to target. Encourage Spending are the bottom 25% in term of spending. The metric is also based on
percent salary used (0.682 or lower) yielding us around 4398 users. The reason why we picked top 75% and bottom 25%, because its able to
reduce the population size by more than half, allowing a more focus marketing strategy.  
## Question 3 - Machine Learning
Our main objective is the find similar group of users. 

To begin, we combined the two datasets that were given into one. Since, we are not trying to analysis individual transactions, but rather
the overall user behavior, we grouped the transaction dataset by customerId & transaction categories, resulting the dataset below.

Since our dataset is not well labeled(i.e. there is no clear y values), we used an unsupervised learning model. The model we pick was K-Mean Clustering because it is 
generally used when you have a set of features that you want to find groups that share similar charateristics. In addition, its relative simple implement.
To begin, we had to find out appropriate N-Cluster. To do this, we deployed the elbow method (Sum of Squared Distance), which resulted in n=3. 
There isn't an solid evaluation metric for most clustering analysis. However, we did plot a scatterplot regarding salary and transational total to see if
the data was correctly partition(See Below)





## Verdict
Combing the Data Visualization results with the K-Mean clustering can allow the growth/marketing team to target specific subgroup of our users.
First, spending engaged users. Depending on which K-Mean categories they belong to, we can produce targeted promotion to continue to spend. For the encourage spending group, 95% of the usres are in K-Mean Cat Group 0. This means that according to our K-Mean Cluster, this group is quiet homogenous. If done correctly, the our targeted promotion should resonnate with majority of the users here.

From the dashboard, we can see that majority of our spending belongs to travel agencies with Trip.Com, CTrip.Com, and HK Wing ON Travel Service
as the stores that clears the most transaction amount for us. We should have some collorbation with some travel agencies to promote spending.

