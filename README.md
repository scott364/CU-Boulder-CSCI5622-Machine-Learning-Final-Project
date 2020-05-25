Movie Profit Trend Visualization and Predictor


Authors : Abikamet Anbunathan, Hyerin Seok, Scott Scheraga

CSCI 5622 - Spring 2020, Professor Quigley


Problem Space

The film industry involves costly and risky investments and movie studios want to maximize profit and reduce risk especially for large-budget productions. We believe that this risk can be reduced through the use of unsupervised machine learning techniques to cluster together movie genres of movies made in the last 20 years, note the profit the movies of that genre over time, through the use of genre and descriptive terms, forecast the profit of a future movies 
This could potentially reduce the need for production studio’s resources to be allocated to research tasks.Manually labeling broad film categories would be time consuming for studios, and unsupervised clustering methods may be able to determine categories that a human categorizer would not notice.
Lastly, the sub-problem of automatically clustering movies together based on characteristics could be useful for digital distribution companies such as Hulu or Netflix, in order to display similar movies together in their interface, easing the browsing of their content.
Our solution is novel because of our use of a two-stage k-means classifier, optimized with elbow analysis in order to better analyze films through subcategorization. 

Approach

Our approach involved processing movie genre and overview text columns in the TMDB dataset (discussed below) using NLTK. To process this data, we ran each text column through filtering steps that made the text lowercase, removed punctuation and most stop-words, lemmatized, stemmed and then tokenized the words. We then used Tf-idf (term frequency-inverse document frequency) vectorization in order to find the frequency of words used in each text block. We then performed Kmeans clustering on the movie genres, with distance being set as 1-cosine_similarity distance between the films. We utilized elbow analysis to find that 7 clusters was the optimal k  for genre clusters. 
Next, we performed the same TF-idf process on movie overviews, and performed 7 separate k-means clustering operations. The top 3 (lowest) TF-idf word scores for each genre, and top 5 word score for each overview are displayed in this poster’s main chart. 
Once we were able to label each film with a genre cluster and overview cluster, we were able to compare similar films with linear regression. While we had initially set out to predict only a single year’s film profits (revenue-cost) for a given overview cluster, we decided to train our regression models on the years of 2000 to 2015, and predict profits from 2015 to 2019, in order to get a better sense of the accuracy of our model.We also recorded the accuracy of our model with Mean Absolute error, Mean squared error and Root mean squared error.


![1](https://github.com/scott364/CU-Boulder-CSCI5622-Machine-Learning-Final-Project/blob/master/pic1.png)
![2](https://github.com/scott364/CU-Boulder-CSCI5622-Machine-Learning-Final-Project/blob/master/pic2.png)
![3](https://github.com/scott364/CU-Boulder-CSCI5622-Machine-Learning-Final-Project/blob/master/pic3.png)
![4](https://github.com/scott364/CU-Boulder-CSCI5622-Machine-Learning-Final-Project/blob/master/pic4.png)
![5](https://github.com/scott364/CU-Boulder-CSCI5622-Machine-Learning-Final-Project/blob/master/pic5.png)
