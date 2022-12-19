![image](output/popcorn.jpg)

In the 17th century, Molière, the French playwright, actor and poet depicted the customs and morals of his day. The analysis of his work allows us today to have an idea of the societal issues and the questionings of that time. Artistic expression and, more precisely, the 7th art can provide a lot of information about society’s thoughts.  
Here, our goal is to analyze the content of plot summaries from the [CMU Movie Summary Corpus](http://www.cs.cmu.edu/~ark/personas/) and characterized them by looking at the lexical fields, word occurrences, as well as the words polarity and general sentiments. This would allow to identify the main concerns of society (e.g., climate catastrophe, war, technological disaster, family disunity) and evaluate the feelings associated with these topics. We will also look at the evolution of these concerns over time to obtain a more complete characterization of the situation. 

## Topics

{% include Bert_topics_bubble.html %}


{% include bert_topics.html %}

BERT over time: 

{% include bert_topics_time.html %}

## Concerns

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
