![image](output/popcorn.jpg)
In the 17th century, Molière, the French playwright, actor and poet, was a revolutionary force in his day, using his artistic expression as a reflection of the tumultuous societal issues and deep-rooted questions of the time. Through his plays and poetry, Molière provided a glimpse into the customs and norms of his time, and today, the analysis of his work continues to deliver an electrifying insight into the issues and concerns of the era. In a similar manner, the 7th art has proven to be a powerful tool through which we can gain a startling understanding of the thoughts and beliefs of society.

In this study, we are about to unlock the society's deepest mysteries by analyzing the content of movies plot summaries from the [CMU Movie Summary Corpus](http://www.cs.cmu.edu/~ark/personas/). Thanks to groundbreaking natural language processing methods, we will delve into the lexical fields and word occurrences, as well as the words polarity and general sentiments to uncover the main concerns that society faces today – climate catastrophe, war, technological disaster, family disunity – and evaluate the emotions associated with them. By tracing the evolution of these concerns over time, we will come closer to fully understand the dire reality of the situation[^1]. 

[^1]: All the statements made here are supported with satistically significant results. 

## Which scope of information can we get from CMU?

Our study focuses on the movies provided by the CMU Movie Summary Corpus and, more specifically, on the release dates and the plot summaries of these movies. Thanks to this database, we have access to more than 42000 movies with English plot texts, of which 93.8% are provided with a release year. Our dataset represents a wide period of time ranging from 1893 to 2014 with a higher representation for more recent movies. It also gathers a wide range of countries with the top-5 most representative countries being the United States of America, India, United Kingdom, Japan and France.

## Which topics are the most common?

Our first goal is to extract the main topics from plot summaries in order to classify them. To achieve this, we use the BERTopic modeling technique, which is able to analyze all words and sentences contained in the plots summaries, in order to find relevant topics addressed in them. Our BERT model run on all plot summaries and resulted in a set of 50 topics, each characterized by a name composed of a number determined by the model, followed by the three most frequent words inside each topic. In the following plot, the 19 most frequent topics are represented with their associated words and proportion among each topic. To zoom into the less represented topics, you can click on each bubble to make them bigger. From this plot, we observe that the first most frequent topic is 2_town_men_horse, representing cowboy/western movies, and the second topic is 1_police_murder_detective, which can be associated with crime or more violent movies. Overall, among the most represented topics, we find some topics related to conflicts (e.g. 14_hitler_nazi_berlin), relationships (e.g. 3_mother_father_family), technology (e.g. 4_earth_planet_space) or health (e.g. 18_dr_patient_hospital), reflecting major societal issues.  In the stages of our analysis, we are going to delve deeper into these topics and understand what they represent from a societal perspective.

{% include Bert_topics_bubble.html %}

## How do these topics evolve over time?

Now that we have obtained our topics, we can observe their evolution throughout the years. The figure below displays the proportion of each topic for each five years (e.g. 1960 includes years from 1960 to 1964), and reveals that the repartition has changed a lot in the last century. We indeed see a recent expansion of the topic 4_earth_planet_space, reflecting the importance of technology in modern society. Foreign countries related topics have also increased, such as 7_tokyo_conan_japan or 6_wong_kong_master. In addition, topics related to relationships and more precisely family are well represented in recent years, as reflected by topics 0_father_police_family, which is constantly increasing over time, and by topic 3_mother_father_family, which also increases but undergoes a small decline at the very end of the investigated period.  On the contrary, we see a drastic reduction of the second most frequent topic 2_town_men_horse, which is underrepresented in the last 30 years. We also observe a strong increase of the topic 14_hitler_nazi_berlin in 1940, in accordance with the historical facts at that time. Interestingly, topic 11_sharpe_soldiers_japanese and 24_soviet_agent_nuclear, both related to conflicts, evolve in a similar manner, with an increase through the 20th century followed by a decline in the 21st. This could reflect the conflict context presents in the 20th century, which has calmed down after this period in the occidental society. 

{% include bert_topics_time.html %}

## How specific societal concerns are reflected from these movies?

Our second goal is to see to what extent specific societal concerns are reflected in plot summaries. Using the Empath tool, we created lexicon categories for specific concerns based on lead words. Afterwards, this allowed us to caracterize each plot summaries by attributing a score for each concern. Each concern associated with its 10 most frequent words found in the plot summaries are represented in the following figure. Overall, the most represented concerns are relationships, conflict is in second position, the third one gathers space and health concerns, then 4th position is for mental concern, and finally ecological, technological, gender inequality and homophobia are equally represented.

{% include Concerns_Words.html %}

In the following plot we can explore the association between concerns and each BERT topic previously found. To isolate one particular concern in the plot, you can double click on it in the legend. We can see relations of common sense such as space, technological or ecological concern with the topic 4_earth_planet_space, or the conflict concern with 24_soviet_agent_nuclear, 14_hitler_nazi_berlin and 11_sharpe_soldiers_japanese, as well as the relationship concern with 3_mother_father_family. More interestingly, gender inequality is related to topic 1_police_murder_detective and 27_priest_church_nuns, the latter being also related to homophobia. We encourage you to explore this plot on your own, which presents very intriguing societal related results!

{% include Concerns_vs_BERT.html %}

## Do these concerns evolve over time?

The most striking score increase is the one about human interactions and relationships. This concern is constantly increasing and becomes the biggest concern from the 1910s with an exception in the 1940’s where the conflict concern is also very high. In general, ecology, health, technology, homophobia and mental concerns also increase across the study period. 
By inspecting more closely the evolution of specific concerns we can spot interesting links  between concerns evolution and historical timeline. Considering the conflict concern, we can notice two early peaks and a later one. The first one is located between 1915 and 1920, the other one in the 1940s and the third one in the 1965s potentially reflecting the contexts of the First World War, Second World War and Vietnam War among the most famous ones. About space, we can observe a global increase around the 1960s which may be related to some iconic space events: in 1957, U.S.R.R. launched Sputnik; in 1958, the U.S. launched the first satellite; in 1969, the first man landed on the moon. 
Overall, what cannot be disputed is that society is concerned about human relationships and warfare. 

{% include concern_score_time.html %}

## Which sentiments are mirrored by the cinema?

Our third goal is to extract and analyze feelings conveyed by plot summaries. We start with a simple analysis using the VADER model, which is sensitive to the polarity (positive/negative) of emotion, and then continue further by extracting more complex sentiments based on the basic emotions defined by [Plutchik](https://doi.org/10.1016/B978-0-12-558701-3.50007-7)(such as fear, anger, trust, sadness or joy). After that, a score for each sentiment is attributed to every movie. Our analysis reveals that trust, negative, fear, anticipation and positive feelings have the highest mean score overall. Looking at the correlations across sentiments, we can notice that what is recognized as “good feelings” tend to be positively linearly correlated together (same goes for “bad feelings”), while the linear correlation between “good feelings” and “bad feelings” tends to be negative. We can also note that anticipation is associated with good sentiments underlying the meaning of anticipation here is closer to enthusiasm than anxiety. 


## What is the evolution of society's feelings?

At first glance, we should be worried about the societal situation: negative sentiment scores outgrow the positive ones in the 1930s and stay higher until 2014, the end of the study period. However, when analyzing the global evolution of sentiments through the course of time, we can be reassured by the decrease of “bad feelings” such as negative, fear, anger and disgust, and by the increase of “good feelings” with an augmentation in trust, joy and anticipation. There is an exception, however, for sadness which is also increasing. 
Here, cinema reflects an overall societal state which is more negative since the 1930s, but which is getting more positive and less negative across time. 

{% include sentiment_scores_time.html %}
 

##  How is society feeling about societal issues?
<div align="justify">... </div> 


BERT topics vs negative/positive:

{% include radar_chart_bisentiment_BERT.html %}

BERT topics vs multi sentiment:

{% include radar_chart_multisentiment_BERT.html %}

Sentiments vs concerns: 

{% include heatmap_sentiments_concerns.html %}


## Conclusion
<div align="justify">After all this analysis, we come up with the conclusion that relationships and health are the most important concern found in this study. (relate to wishes new year)</div>
