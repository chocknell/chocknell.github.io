---
layout: post
title: Movie Recommendation System
---

Sentiment Analysis of Movie Reviews and Multiple Recommender Systems.

#### Sentiment Analysis
For the first part of this project, I utilised NLP analysis and a number of machine learning algorithms to predict the sentiment of a given movie review. **Logistic Regression** resulted in the highest accuracy of over 80%, and this was then used within a pipeline to generate a .pkl file to be used on a user-input movie review.

**Sentiment Example**
![sentiment]({{ site.baseurl }}/images/sentiment.png)

#### Recommender Systems

The second part of this project was to create three different forms of recommender system:
1. Content based
2. User based
3. Collaborative

These were each created to allow for recommendations to be given to a new user of a site, therefore avoiding the 'Cold Start' problem. An example of a Content-Based recommendation is given in the image below.

**Content Based Recommendation**
![movies]({{ site.baseurl }}/images/movies.png)

#### Try It Yourself!
Feel free to look into both the Sentiment Analysis and Recommendation Systems via my [Streamlit App](https://moviereviews-chocknell.streamlit.app/), and please reach out if you have any questions!