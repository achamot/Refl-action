![image](output/popcorn.jpg)

<div align="right">In the 17th century, Molière, the French playwright, actor and poet, was a revolutionary force in his day, using his artistic expression as a reflection of the tumultuous societal issues and deep-rooted questions of the time. Through his plays and poetry, Molière provided a glimpse into the customs and norms of his time, and today, the analysis of his work continues to deliver an electrifying insight into the issues and concerns of the era. In a similar manner, the 7th art has proven to be a powerful tool through which we can gain a startling understanding of the thoughts and beliefs of society.</div>

Here, we are about to unlock the society's deepest mysteries by analyzing the content of movie plot summaries from the [CMU Movie Summary Corpus](http://www.cs.cmu.edu/~ark/personas/). Thanks to groundbreaking natural language processing methods, we will delve into the lexical fields and word occurrences, as well as the words polarity and general sentiments to uncover the main concerns that society faces today – climate catastrophe, war, technological disaster, family disunity – and evaluate the emotions associated with them. By tracing the evolution of these concerns over time, we will be closer to fully understanding the dire reality of the situation[^1].

[^1]: All the statements made here are supported with satistically significant results. 

## Which scope of information can we get from CMU?

Our study focuses on the movies provided by the CMU Movie Summary Corpus and, more specifically, on the release date and the plot summaries of these movies. Thanks to this database, we have access to more than 42000 movies with English plot texts, of which 93.8% are provided with a release year. Our dataset represents a wide period of time ranging from 1893 to 2014 with a higher representation for more recent movies. It also gathers a wide range of countries with the top-5 most representative countries being the United States of America, India, United Kingdom, Japan and France.

## Which topics are the most common?

Our first goal is to extract the main topics from plot summaries in order to classify them. To achieve this, we use the BERTopic modeling technique, which is able to analyze all words and sentences contained in the plots summaries, in order to find relevant topics addressed in them. Our BERT model run on all plot summaries resulted in a set of 50 topics, each characterized by a name composed of a number determined by the model, followed by the three most frequent words inside each topic. In the following plot, the 19 most frequent topics are represented with their associated words and proportion among each topic. To better see the less represented topics, you can click on each bubble to make them bigger. From this plot, we observe that the first most frequent topic is 2_town_men_horse, representing cowboy/western movies, and the second topic is 1_police_murder_detective, which can be associated with crime or more violent movies. Overall, among the most represented topics, we find some topics related to conflicts (e.g. 14_hitler_nazi_berlin), relationships (e.g. 3_mother_father_family), technology (e.g. 4_earth_planet_space) or health (e.g. 18_dr_patient_hospital), reflecting major societal issues.  In the following, we are going to delve deeper into these topics and understand what they represent from a societal perspective.

{% include Bert_topics_bubble.html %}

## How do these topics evolve over time?

Now that we have obtained our topics, we can observe their evolution throughout the years. The figure below displays the proportion of each topic for each five years, and reveals that the repartition has changed a lot in the last century. We indeed see a recent expansion of the topic 4_earth_planet_space, reflecting the importance of technology in modern society. Foreign countries related topics have also increased, such as 7_tokyo_conan_japan or 6_wong_kong_master. In addition, topics related to relationships and more precisely family are well represented in recent years, as reflected by topics 0_father_police_family, which is constantly increasing over time, and by topic 3_mother_father_family, which also increases but undergoes a small decline at the very end of the period.  On the contrary, we see a drastic reduction of the second most frequent topic 2_town_men_horse, which is underrepresented in the last 30 years. We also observe a strong increase of the topic 14_hitler_nazi_berlin in 1940, in accordance with the historical facts at that time. Interestingly, topic 11_sharpe_soldiers_japanese and 24_soviet_agent_nuclear, both related to conflicts, evolve in a similmar manner, with an increase through the 20th century followed by a decline in the 21st. This could reflect the conflict context presents in the 20th century, which has calmed down after this period in the occidental society.

{% include bert_topics_time.html %}

## How specific societal concerns are reflected from these movies?

Our second goal is to see to what extent specific societal concerns are reflected in plot summaries. We start by creating these specific concern categories by targeting leading words to characterize each plot summaries by attributing a score for each concern. Each concern associated with its 10 most frequent words found in the plot summaries are represented in the following figure. Overall, the most represented concerns are relationships, conflict is in second position, the third one gathers space and health concerns, then 4th position is for mental concern, and finally ecological, technological, gender inequality and homophobia are equally represented.

{% include Concerns_Words.html %}

In the following plot we can explore the association between concerns and each BERT topic previously found. To isolate one particular concern in the plot, you can double click on it in the legend. We can see relations of common sense such as space, technological or ecological concern with the topic 4_earth_planet_space, or the conflict concern with 24_soviet_agent_nuclear, 14_hitler_nazi_berlin and 11_sharpe_soldiers_japanese, as well as the relationship concern with 3_mother_father_family. More interestingly, gender inequality is related to topic 1_police_murder_detective and 27_priest_church_nuns, the latter being also related to homophobia. We encourage you to explore this plot, which presents very interesting and societal related results!

{% include Concerns_vs_BERT.html %}

## Do these concerns evolve over time?

Categories over time period of five years:

{% include concern_score_time.html %}

## Which sentiments are mirrored by the cinema?

## What is the evolution of society's feelings?

Sentiments over time: 

{% include sentiment_scores_time.html %}

BERT vs Sentiment over time: 

{% include bert_topics_time_sentiment.html max-width="50" %}

BERT topics vs sentiment: 

{% include radar_chart_trisentiment_BERT.html %}

BERT topics vs negative/positive:

{% include radar_chart_bisentiment_BERT.html %}

BERT topics vs multi sentiment:

{% include radar_chart_multisentiment_BERT.html %}

##  How is society feeling about societal issues?

Sentiments vs concerns: 

{% include heatmap_sentiments_concerns.html %}

## Conclusion
After all this analysis, we come up with the conclusion that relationships and health are the most important concern found in this study. (relate to wishes new year)
