# Beyond Words - predicting user decision with text data
<p align="center">
   <img src="https://github.com/er1czz/beyondwords/blob/main/word_cloud_1.png"  width="500"/> 
</p>  

## Executive Summary
  * Software as a service (SaaS) is a major sector of cloud computing business. To thrive in this competitive market, growing user base is a crucial drive of business. Predicting and understanding customer decision is imperative to help a company quickly adapt its product to meet users’ needs.  
  * Performing sentiment and text analysis on user communication data can be an effective approach to reflect user experience or satisfaction level. An algorithmic approach based on the sentiment and text analysis was carried out to predict when a user is about to subscribe or unsubscribe. The client of this consulting project is a startup company specializing on a fitness app designed for runners. The data are generated from user communication in-app.  
  * Several features were extracted from the text data by machine learning, including sentiment, number of characters, number of words, etc. A classification algorithm was used to process the text data, which predicted nearly 100% user conversions within the free-trial period. This algorithmic approach can facilitate the client to develop effective marketing strategy to target users. Consequently, the growth rate of premium user base is expected to be improved by increasing the user conversion rate. Similar approach can be used to improve user retention by predicting user unsubscription events.

**The key steps of this data science project are listed as follows:**   
1. Preprocessing text data for machine to read
 - Converting emoji and emoticon by [*emoji*](https://github.com/carpedm20/emoji/) and [*emot*](https://github.com/NeelShah18/emot) packages, respectively.
 - Note: although [*emot*](https://github.com/NeelShah18/emot) can also process emoji, its emoji database is incomplete.
 
2. Choosing the right natural language processing (NLP)models
 - Unsupervised NLP: TextBlob and VADER
 - Supervised NLP: [Pretrained BERT (off-the-self)](https://huggingface.co/transformers/main_classes/pipelines.html#transformers.pipeline)
 
3. Tuning the model with proper labels
 - Customized two label classes: Tone (netural/positive) and Fact (none/partial/rich)
 - Fine-tune BERT through [ktrain](https://arxiv.org/abs/2004.10703)
 
4. Predicting user conversion within free-trial period
 - Sentiment, likes, words, characters
 - A stacking classifier (Random Forest, XGBoost, and Ridge combined by Logistic Regression)
 - User engagement is the key (top predictive features: characters, words, and their averages)

<p align="center"><img src="https://github.com/er1czz/beyondwords/blob/main/emo_convert.PNG"  width="700"/></p>
<p align="center"><b>Converting emojis and emoticons</b> </p>
<p align="center"><img src="https://github.com/er1czz/beyondwords/blob/main/NLP_benchmark.PNG"  width="700"/></p>
<p align="center"><b>NLP Models Performance Comparision</b>, OTS: off-the-shelf </p>


**To Be Continued**
