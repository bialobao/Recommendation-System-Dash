Recommendation system, market basket analyses and Dashboard

ABSTRACT
This machine learning and data visualization project has the objective of analysing a profiles of book buyers to recommend other books. Also analyse the basket supermarket to associate products.
The project follows the CRISP-DM methodology as this is an open standard process that describes the approaches used in data analysis. CRISP-DM is widely used across many industries and, although it is an idealised sequence of events, there is flexibility, as tasks can be performed in different order.
Keywords: Recommendation system, market basket analyses, Amazon books, Dashboard.

DATA PREPARATION, MODELLING AND EVALUATION
The dataset is about book sales by amazon. The dataset was treated in order to reduce the number of rows by removing those that did not make sense, such as people over 100 years old, year of publication 0 or before 1500 or after 2021. Fix errors in city, state and country names.
In addition to filtering books that have received at least 100 reviews, to ensure that the rating is not based on the opinion of a few people, and users who have reviewed 200 times, to avoid fraudulent reviews.
The dataset after data preparation has 41932 observations and 17 columns.
Highlighting the userID, ISBN, bookRating, bookTitle, bookAuthor, yearOfPublication, publisher, Location, Age, City, State, Country, query, location_lat, location_long.

RECOMMENDATION SYSTEM
The recommendation system is an app or website that, based on your past purchases, predicts what the user would be interested in buying, reading or watching. That would save time that would otherwise be spent searching for books of interest on various sites.
Initially, the following methods for building the recommendation system were tested.

BaselineOnly
Algorithm predicts the baseline estimate for given user and item.

kNNBaseline
The method of using the mean rating for a book when evaluating a user’s rating.

kNNwithMeans
K-means algorithm in data mining starts with a first group of randomly selected centroids, which are used as the beginning points for every cluster, and then performs iterative (repetitive) calculations to optimize the positions of the centroids.

SVIs a collaborative filtering algorithm based on Non-negative Matrix Factorization. It is very similar with SVD.Is a collaborative filtering algorithm based on Non-negative Matrix Factorization. It is very similar with SVD.D
Singular value decomposition is a very popular linear algebra technique to break down a matrix into the product of a few smaller matrices. SVD to discover relationship between items.

kNN basic
KNN works by finding the distances between a query and all the examples in the data, selecting the specified number examples (K) closest to the query, then votes for the most frequent label (in the case of classification) or averages the labels (in the case of regression).

SVDpp
The algorithm is an extension of SVD that takes into account implicit ratings.

NMF
Is a collaborative filtering algorithm based on Non-negative Matrix Factorization. It is very similar with SVD.

NormalPredictor
The algorithm predicts a random rating based on the distribution of the training set, which is assumed to be normal.
The results of the methods are in the table below. The methods were guided by the RMSE.

![image](https://github.com/bialobao/Recommendation-System-Dash/assets/102151892/ee45362d-147a-438a-b50c-5e0054458312)

Table 1: Results of the models for recommendation system.

The four methods that presented the best RMSE results were applied to GridSearchCV

![image](https://github.com/bialobao/Recommendation-System-Dash/assets/102151892/047e4810-2564-4c2c-b1aa-fefadcc9c576)

Figure 1: Results of the models for recommendation system by RMSE.

![image](https://github.com/bialobao/Recommendation-System-Dash/assets/102151892/eb8cd542-f405-4ebe-881c-70b178a67c10)

Figure 2: Results of the models for recommendation system by MAE.

Comparing recommendations of the Best Model by RSME and the Best Model by MAE.
Recommendations based on (SVD) x Recommendations based on (K Means)

![image](https://github.com/bialobao/Recommendation-System-Dash/assets/102151892/617492a7-5490-4ac7-bd27-31588a3d3e0b)

Table 2: List of recommendation by SVD

![image](https://github.com/bialobao/Recommendation-System-Dash/assets/102151892/01c101e0-2ed2-4923-91e7-87559cb70e08)

Table 3: List of recommendation by Kmeans

Visualizing the table above, we can see that the methods coincide in 8 book indications for the same user. These coincidences shows a good performance of the methods.

MARKET BASKET ANALYSIS

Retailers predominantly use market basket analysis to reveal relationships between items. It works by looking for combinations of items that are often put together, allowing retailers to identify relationships between items that people buy.
The Apriori and Fp Grown method make a association rule mining finds interesting associations and relationships among large sets of data items. This rule shows how frequently an item set occurs in a transaction. A market basket analysis is performed based on the rules created from the dataset.
Support is the relative frequency of the rule display. In many cases, you may want
to seek high support to make sure it’s a worthwhile relationship. However, there may be
cases where low support is useful if you are trying to find “hidden” relationships.
Confidence is a measure of the reliability of a rule. A 0.5 reliability in the preceding
example means that bread and milk were purchased 50% of the time. The purchase also
included butter and chips. For a product recommendation, 50% confidence may be
perfectly acceptable, but this level may not be high enough in a medical situation.
Lift is the ratio of observed support to expected support if the two rules were
independent. As a rule of thumb, a lift value close to 1 means that the rules were completely independent. Lift - values > 1 are more “interesting” and could indicate a
useful rule pattern.

DATA PREPARATION, MODELLING AND EVALUATION

Unlike the first dataset, this second only contains the composition of a supermarket cart. Each column and a person's cart. The nan values were replaced by 0.
In addition, the dataset was encoded, so that each product was a column and showed that if there is a product then = 1, if not then = 0.

Apriori

![image](https://github.com/bialobao/Recommendation-System-Dash/assets/102151892/6684329e-16fb-4677-87fb-71955850fdc6)

Table 4: Associated products by Apriori

Fp Grown

![image](https://github.com/bialobao/Recommendation-System-Dash/assets/102151892/35b85475-ba34-457e-beac-922749a607f6)

Table 5: Associated products by Fp Grown

The tables above were generated by confidence level. That is, according to the two methods presented, there is a 25.6 chance that people who buy sausage and yogurt will also buy milk. This means that the products are highly related, and for the supermarket, placing them next to each other would be a great way to sell more.
The methods present exactly the same result, but at different time of execution.

![image](https://github.com/bialobao/Recommendation-System-Dash/assets/102151892/f5bef9e5-4e86-4272-ba5a-dccbe3757bd1)

Figure 3: Comparing time of execution Apriori x Fp Grown.

As we can see, in our dataset the apriori method took less time to execute than Fp Grown. So, being defined as the best for the dataset, since it proves the same result in a much shorter time.

DATA VISUALIZATION
DASHBOARD
The target audience of this panel is seniors aged 65+. With that in mind, the fact that at this age most of them have impaired eyesight, the contrast was used as a tool for developing the panel. The most used colors were gray, red, purple, orange, green and blue was avoided. The black template was essential for contrast with the focus on the target audience. The font size of the titles, axis titles and legend were 40, 20 and 15 respectively, respecting proportionality as a design understanding that the main information will be passed on to the public. All titles are located on the left, where Westerners begin to read, namely by highlighting the title.
The first view is a map that shows the world map with cities where people buy books from. clicking on the city it is possible to see all the books that have already been delivered in that specific city. It is possible to choose a specific city, a specific book, or even see all the dataset information or the amount you want up to the total dataset observations. This visualization was made by the folium library.

![image](https://github.com/bialobao/Recommendation-System-Dash/assets/102151892/5b594f1f-c800-4e15-ab15-b1679a0b2a19)

Figure 4: World map with cities where people buy books.

The dashboard was developed with plotly and Dash. The first view of the dashboard is made with water green that contrasts with the black background. The age distribution is left skew. 
Having most buyers between 25 - 35 years old. The second graph is the average book review according to the year it was published. Books published in 1974 were better evaluated by readers. 
Graph 3 uses the white template to separate the section with contrast. The chosen colors avoid blue and separate old books with purple from newer ones with yellow.
In 2002, 5267 books were published, making it the year with the most books published. In graphic 4 we can see the contrast by the colors dark red, yellow and gray. 
The author who most published books was Nora Roberts. Viewing on the pie chart I chose 5 very different colors so that there was no confusion of countries. The country colors are described in the legend. 
Americans are the ones who buy the most books. Chart 6 has the same color principle as chart 5.
It shows that user 52584 is the customer who buys the most books on Amazon.

![image](https://github.com/bialobao/Recommendation-System-Dash/assets/102151892/e2105aad-d514-44f6-8f73-2070dc814d60)

Figure 5: Dashboard most important aspects of the data.

CONCLUSION
The biggest challenge of the project was to reach the recommendation lists of the best methods achieved by GridsearchCV. In addition, iterability within Dash was a huge challenge.
The best models for recommendation according to RSME were SVD 3.22 and according to MAE were KnnwithMeans 2.39. Both methods had 8 recommendations in common, showing that both are good.
The Apriori and Fp Grown results were the same, as expected. With 25.6 chance that people who buy sausage and yogurt will also buy whole milk. The apriori method took less time to execute than Fp Grown. So, being defined as the best for the dataset.
The visualization of the map promoted an identification of where in the world people buy more books in an iterative way. The dashboard was developed with plotly and Dash. The dashboard shows the most important aspects of the data.
Visualization along with machine learning analysis makes it easier to understand how to work with the public. Who are the most loyal customers, where you need to invest more in marketing to sell more.

