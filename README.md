
![header](./images/slides_header.jpg)
# Overview

The goal of this project is to perform a sentiment analysis of Apple customers, and uncover actionable insight that could be used to optimize a marketing strategy going forward. To achieve this, we built a predictive model using Natural Language Processing (NLP),  that could rate the sentiment of a tweet based on its content. At the end of our analysis, we present the findings of our model and provide concrete recommendations as to how Apple could improve its marketing strategy going forward and ultimately increase customer satisfaction. 

# Business Understanding 

Developing an excellent marketing strategy is crucial for an organization to consistently achieve positive results. To perform effective marketing, companies need to gain a deep understanding of their customers and uncover what matters to them most. The challenge is figuring out how to gain this insight in an efficient manner, and how to consistently implement meaningful change. Fortunately, machine learning provides us with unique and effective tools to perform customer sentiment analysis and guide long-term decision making. 

# Data Understanding
For our analysis we utilized the Brands & Product Emotions Dataset, which originally consisted of 9,093 entries. The attributes of this dataset included customer tweets, Apple and Google product types, and customer sentiment. For exploration purposes, we narrowed the dataset to all Apple and Google tweets that had a sentiment attached, which was 3,291 entries.

![Company Tweets](./images/tweets_by_company.png)

# Exploratory Data Analysis
Since our stakeholder for this analysis is Apple, we began exploring overall customer sentiment specifically towards them. As you can see in the chart below, the majority of tweets were positive.

![Apple Sentiment](./images/apple_sentiment.png)

The next step was to explore product specific sentiment. To do this, we created a new dataframe that only contained tweets related to the iPad and iPhone. As you can see in the plot below, the iPhone had a higher percentage of negative tweets compared to the iPad. This led us to believe that the iPhone could represent an opportunity for marketing improvement and should be explored further.

![Product Sentiment](./images/product_sentiment.png)

We then sought to identify specific words that may be related to positive or negative sentiment tweets. We discovered that ???SXSW??? was the most common word found in positive tweets. Upon a deeper dive into the tweets themselves, we were able to confirm that Apple had launched a new iPad at the SXSW event in Austin, which generated a lot of positive buzz on Twitter. As for negative sentiment, we discovered that ???battery??? was the most common word found in negative tweets about the iPhone. As you can see in the plot below, ???blackberry??? was also a common word found in negative tweets. A deeper dive into the tweets themselves told us that users were complaining about the iPhone battery and reminiscing about stronger battery life found in the Blackberry. 

![Positive Words](./images/positive_words.png)
![Negative Words](./images/negative_words.png)

# Modeling
To better understand the customer, we used NLP and a RandomForest Classifier model to predict customer sentiment based on tweets. The first step is preprocessing the tweets using NLTK, which includes tokenizing the tweets using a regular expression tokenizer, removing stop words, and stemming the words. This preprocessing step is performed on the 'tweet' column of the data and the result is stored in a new column 'preprocessed_tweet'.
The next step is to create a vector representation of the preprocessed tweets using CountVectorizer. This vector is then split into training and test sets. The model then uses a RandomForestClassifier to fit the training data and predict the sentiment of the test data. The baseline model accuracy came out to be 86.49%. In the next section, we discuss the results of our final model after tuning. 

# Final Evaluation
In order to train our model to predict Apple customer sentiment based on future tweets, we needed to narrow our dataset so that it only contained Apple related customer tweets that had a sentiment attached to them. As a result, our final model was built from a dataset that contained 2,751 data entries.  We then preprocessed and vectorized in the same way as our original model, and performed a Grid Search to tune the hyperparameters of the Random Forest Classifier. The Grid Search used a 5-fold-cross-validation and tested various combinations of parameters such as number of estimators, criterion, class weight, etc. After the Grid Search returned the best set of hyperparameters, we ran the final model and achieved an accuracy score of 87.21%. 

# Recommendations
Based on our analysis, we have two concrete recommendations for the Apple marketing team to implement going forward. First- look for more opportunities to do product launches at events. Twitter data indicated that the SXSW event in Austin went very well and generated a lot of positive online buzz. Second- as the iPhone sees improvements in battery life, make sure to strongly highlight these improvements in your advertising. Data indicated that there is a negative perception of the iPhone battery life, and therefore efforts to reduce this perception should bode well.

# Next Steps
In the future we???d like to add additional sources of customer sentiment into the analysis, such as data from Facebook and Instagram. The more examples of customer sentiment we have, the better we can predict outcomes and make recommendations. Finally, since customer preferences and attitudes are always evolving, we???d like to update the model and our analysis regularly so that your team can stay on top of trends and perceptions in real-time. Ultimately, we believe these efforts will lead to increased customer satisfaction.

## For More Information   

See the full analysis in the [Jupyter Notebook](./index.ipynb) or review this [presentation](./presentation.pdf).

**For additional info, contact:**
- Nate Kist: natekist@outlook.com
- Zach Cherna: zacharycherna@gmail.com
- Jose Castillo: 114josecastillo@gmail.com 

## Repository Structure

```
????????? images
???   ????????? slides_header.jpg
???   ????????? negative_words.png
???   ????????? positive_words.png
???   ????????? product_sentiment.png
???   ????????? tweets_by_company.png
????????? data
???   ????????? judge-1377884607_tweet_product_company.csv
????????? eda_notebooks
???   ????????? index_Nate - v3.ipynb.csv
???   ????????? index_just_eda_zach.ipynb
????????? notebook.ipynb
????????? presentation.pdf
????????? README.md
```




