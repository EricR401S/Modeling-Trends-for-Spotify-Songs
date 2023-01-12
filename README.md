# Modeling-Trends-for-Spotify-Songs
This is a project in which we will investigate Spotify song data (scraped by Yamac Eren Ay and hosted on Kaggle) to answer two questions of interest. One is what musical attributes boosted the popularity of songs in the 2010s, and the second is to what extent can the musicality of a song predict whether a song is explicit or non-explicit. 

Dataset Link : https://www.kaggle.com/datasets/yamaerenay/spotify-dataset-19212020-600k-tracks

# Research Questions Overview with Variables of interest

Research Questions:
<ul>
<li> What are the musical attributes that gauged the popularity of songs in the 2010s? 

*Dependent Variable (continuous) = popularity Independent Variables = acousticness, danceability, energy, instrumentation, tempo, loudness, and speechiness.* </li>

<li> To what extent can the musicality of a song predict whether a song will be explicit or non-explicit? 

*Dependent Variable (categorical) = Explicitness Independent Variables = danceability, energy, speechiness, and tempo.* </li>
</ul>

Popularity's EDA:

![image](https://user-images.githubusercontent.com/70504872/212140511-7b78341e-8a22-43a9-8cb2-49b535c8daab.png)

Explicitness's EDA:

![image](https://user-images.githubusercontent.com/70504872/212141076-1ce7a62d-de13-4990-8a51-1821b0dce28e.png)


# Methods used to model

We used multiple linear regression for the first question and logistic regression for the second question. 

# Key Results 

In the analysis of the first research question, which dealt with inferring the significant predictors impacting the popularity of the song, we have a finding that 
instrumentalness is the most important attribute influencing the popularity of the song in 2010s decade. A track with high levels of instrumentalness is likely to be 
least appealing to the audience. Also, other important predictors impacting the popularity are acousticness, danceability, energy, loudness and speechiness. For the 
popularity of the track to be high, instrumentalness and energy, the most significant musical attributes should have low values. A track that has high levels of 
acousticness, danceability, loudness and speechiness is likely to have a higher popularity score. Furthermore, loudness was the predictor with the highest coefficient, 
which is not surprising. During music mastering, adjusting loudness commands high prioritization due to how sensitive the human ear perceives changes in it
(Sage Audio). Based on the second research result, we can conclude that the four chosen predictors, danceability, energy, speechiness and tempo, are indeed related to 
explicitness and can predict explicitness to some extent. Overall, the model at the 0.5 threshold is a good fit with an acceptable, prediction accuracy score of 81%, 
with a 14% success rate of identifying explicit songs. The AUC value was 79%, a determinant of how well the model can classify positives and negatives, and this score is 
relatively high. On the contrary, when adjusting the cutoff to a best threshold of 0.087, the overall accuracy drops to 72%, but the ability to predict explicit songs 
rises to 73.2% while the capacity to classify non-explicit songs drops from 97.9% to a 71.8%. The gains and losses from this trade-off are evident, and we conclude that 
we need better and more robust predictors to have better accuracy. Yet, we still remain with a pressing question. Why do we prioritize correctly classifying explicit 
songs? If a song’s capacity to play in a setting depended on this categorizing, then this model would have to be more accurate. An ill classified explicit song should 
not play in a setting for children. Conversely, a misidentified, non-explicit song should not be penalized and lose potential profits by not being allowed to
play in a general, public setting. However, these arguments would mostly apply if our statistical model was a mission critical one, but it is not; Spotify most likely 
employs methods from the realm of natural language processing to flag the explicitness of songs, not statistical methods. This implies that they would ignore most of the 
musical aspects when employing their codification processes.
