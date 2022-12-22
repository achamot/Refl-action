![image](output/popcorn.jpg)

In the 17th century, Molière, the French playwright, actor and poet, was a revolutionary force in his day, using his artistic expression as a reflection of the tumultuous societal issues and deep-rooted questions of the time. Through his plays and poetry, Molière provided a glimpse into the customs and norms of his time, and today, the analysis of his work continues to deliver an electrifying insight into the issues and concerns of the era. In a similar manner, the 7th art has proven to be a powerful tool through which we can gain a startling understanding of the thoughts and beliefs of society.

Here, we are about to unlock the society's deepest mysteries by analyzing the content of movie plot summaries from the CMU Movie Summary Corpus. Thanks to groundbreaking natural language processing methods, we will delve into the lexical fields and word occurrences, as well as the words polarity and general sentiments to uncover the main concerns that society faces today – climate catastrophe, war, technological disaster, family disunity – and evaluate the emotions associated with them. By tracing the evolution of these concerns over time, we will be closer to fully understanding the dire reality of the situation.

## Which scope of information can we get from CMU?

Our study focuses on the movies provided by the CMU Movie Summary Corpus and, more specifically, on the release date and the plot summaries of these movies. Thanks to this database, we have access to more than 42000 movies with English plot texts, of which 93.8% are provided with a release year. Our dataset represents a wide period of time ranging from 1893 to 2014 with a higher representation for more recent movies. It also gathers a wide range of countries with the top-5 most representative countries being United States of America, India, United Kingdom, Japan and France.

## Which topics are the most common?

Our first goal is to extract the main topics from plot summaries in order to classify them. To achieve this, we use the BERTopic modeling technique, which is able to analyze all words and sentences contained in the plots summaries, in order to find relevant topics addressed in them. Our BERT model run on all plot summaries resulted in a set of 50 topics, each characterized by a name composed of a number determined by the model, followed by the three most frequent words inside each topic. In the following plot, the 19 most frequent topics are represented with their associated words and proportion among each topic. To better see the less represented topics, you can click on each bubble to make them bigger. From this plot, we observe that the first most frequent topic is the 1_police_murder_detective topic, which can be associated with crime or more violent movies, and the second topic is  2_town_men_horse, representing cowboy movies. In the following, we are going to delve deeper into these topics and understand what they represent from a societal perspective.

{% include Bert_topics_bubble.html %}

## How do these topics evolve over time?



{% include bert_topics_time.html %}

## Concerns

The 10 most present words in movies plot summaries for each concern:

{% include Concerns_Words.html %}

Categories over time period of five years:

{% include concern_score_time.html %}

## Sentiments

Sentiments over time: 

{% include sentiment_scores_time.html %}

BERT vs Sentiment over time t: 

{% include bert_topics_time_sentiment.html max-width="50" %}

BERT topics vs sentiment: 

{% include radar_chart_trisentiment_BERT.html %}

BERT topics vs negative/positive:

{% include radar_chart_bisentiment_BERT.html %}

BERT topics vs multi sentiment:

{% include radar_chart_multisentiment_BERT.html %}

Sentiments vs concerns: 

{% include heatmap_sentiments_concerns.html %}
