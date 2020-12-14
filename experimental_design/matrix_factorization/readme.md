Content:

- We will look from a high level at how you might go about validating your recommendations.

- We will look at matrix factorization as a method to use machine learning to make recommendations.

- We will look at combining recommendation techniques to make predictions to existing and new users and for existing and new items.

Validating Your Recommendations

- Online Testing

For online methods of testing a recommender's performance, many of the methods you saw in the previous lesson work very well - you can deploy your recommendations and just watch your metrics carefully. It is common in practice to set up online recommendations to have an "old" version of recommended items, which is compared to a new page that uses a new recommendation strategy.

All ideas associated with A/B testing that you learned in the earlier lessons are critical to watching your metrics in online learning, and ultimately, choosing a recommendation strategy that works best for your products and customers.

- Offline Testing

In many cases, a company might not let you simply deploy your recommendations out into the real world any time you feel like it. Testing out your recommendations in a training-testing environment prior to deploying them is called offline testing.

The recommendation methods you built in the previous lesson actually don't work very well for offline testing. In offline testing, it is ideal to not just obtain a list of recommendations for each individual, because we ultimately don't know if a user doesn't use an item because they don't like it, or because they just haven't used it yet (but would like it). Rather, it would be great if we have an idea of how much each user would like each item using a predicted rating. Then we can compare this predicted rating to the actual rating any individual gives to an item in the future.

In the previous video, you saw an example of a user to whom we gave a list of movies that they still hadn't seen. Therefore, we couldn't tell how well we were doing with our recommendations. Techniques related to matrix factorization lend themselves nicely to solving this problem.

- User Groups

The final (possible) method of validating your recommendations is by having user groups give feedback on items you would recommend for them. Obtaining good user groups that are representative of your customers can be a challenge on its own. This is especially true when you have a lot of products and a very large consumer base.

Metric & Method

Accurracy => Classification
MSE => Regression
Precision = Classification
Recall => Classification
R-Squared => Regression

Singular Value Decomposition Takeaways

Three main takeaways from the previous notebook:

The latent factors retrieved from SVD aren't actually labeled.
We can get an idea of how many latent factors we might want to keep by using the Sigma matrix.
SVD in NumPy will not work when our matrix has missing values. This makes this technique less than useful for our current user-movie matrix.
