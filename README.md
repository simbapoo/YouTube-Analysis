# YouTube-Analysis
# Data-science
The main idea of this project to  help bloggers to create popular video by analyzing our dataset.
How to write title,which category to choose,when to publish,which tags to use in a video to have more views.
 Project is based on Youtube trending videos. Lets say we  want to know how to create popular videos. 
We worked on Youtube trending videos from the first half of 2018 not only from the USA, but from 9 countries:
- USA
- Russia
- India
- Japan
- Germany
- South Korea
- Mexica
- Canada
- France
 
 Data Preparation
From the start in the dataset we have only category_id, but we can’t understand anything with just a number.
We took the data from the json file with information about Youtube’s categories. 
​In this section we'll convert the raw messages (sequence of characters) into vectors (sequences of numbers). 
Splitted a message into its individual words and return a list.
By using NLP libraries we also removed very common words and punctuation marks ('the', 'a',etc..). Data p​reparation steps by using NLP:

● Count how many times does a word occur in each message (Known as term frequency).

● Weigh the counts, so that frequent tokens get lower weight (inverse document frequency) by TF-IDF algorithm.

● Normalize the vectors to unit length, to abstract from the original text length (L2 norm)

Modeling
At first, we predicted on all the data that we considered necessary(category_id,title_length) and realized that many features do not have weight for predicting views. 
In the initial model, we used Linear Regression and we got 3% , after that we switched to NLP-preprocessing and deduced the following.
By using several algorithms, the R2 score of each algorithm is shown as following:
 
 Linear Regression NLP-‘Title’ based algorithm: 78%
KNeighborsRegressor NLP-’Title’ based algorithm: 80%, best parameter is K=2.
 Evaluation
There are not many possible metrics in our case for evaluating model performance. Which one is most important depends on the challenge and the
business implications of the model-driven decisions. We used the R2 to calculate the score. We also used Mean Absolute Error (MAE) , 
Mean Squared Error (MSE) and Root Mean Squared Error (RMSE).
 
 Data understanding
We have 40000 rows for each country. We started analysys from USA trending videos. First of all we checked the correlation between columns of the dataset, 
but it does not represent any important information for us. We checked differences between the countries.
 
    
  As we can see, the US part of Youtube is the most developed. Here we have much more views, likes, dislikes, and comments than in other countries. 
  We are going to use the US segment of Youtube for analysing videos.
 Entertainment is the most popular category in all countries except Russia.
 
 In the USA people and blogs are on the 5th place. Entertainment is on the first place with a huge gap between the music category.
  People in the USA love funny videos.
 
 Most videos in the trending list are uploaded at 4 PM.
Conclusion
This project explores how to use machine learning algorithms to predict the video performance for YouTuber. After using several algorithms, model improvements,
and backward search on features, extreme gradient boosting with features category, description performs the best with a linear regression R2 score of 0.78 
and KNR(k-neighbor regression) -score of 0.82 tool. The features {category, description} briefly represent the content of video, 
and the audience may have a tendency to look for a certain category or content of video. We can say that for video the title is the most important feature, 
because viewers can’t see the description before opening the video. 
The video has more chances to be popular if it’s category is Entertainment and using tags like funny and comedy.
