# Beyond Words - predicting user decision with text data
<p align="center">
   <img src="word_cloud_1.png"  width="500"/> 
</p>  

## Executive Summary
  * Software as a service (SaaS) is a major sector of cloud computing business. To thrive in this competitive market, growing user base is a crucial drive of business. Predicting and understanding customer decision are imperative to help a company timely adapt its service to meet users’ needs.  
  * Performing sentiment and text analysis on user communication data can be an effective approach to reflect user experience or satisfaction level. An algorithmic approach based on the user text data was carried out to predict when a user is about to subscribe or unsubscribe. The client of this consulting project is a startup company specializing in developing platforms designed for content creators to create their mobile apps. The data are generated from user communication in-app.  
  * Several features were extracted from the text data, including sentiment, number of characters, number of words, etc. A model was trained based on these features to predict user decision. Specifically, this model examined user conversion events within the free-trial period, which successfully predicted nearly all the events. Therefore, this algorithmic approach can facilitate the development of marketing strategies for client to grow the premium user base by more trial promotions. Similar approach can be used to improve user retention by predicting user unsubscription events (customer churn).

## Key Procedures
1. **Preprocessing text data for machine to read**
    - Converte emoji and emoticon by [*emoji*](https://github.com/carpedm20/emoji/) and [*emot*](https://github.com/NeelShah18/emot) packages, respectively.
    - Note: although [*emot*](https://github.com/NeelShah18/emot) can also process emoji, its emoji database is not as comprehensive as [*emoji*](https://github.com/carpedm20/emoji/).

2. **Choosing the right natural language processing (NLP)models**
    - Test unsupervised NLP: [TextBlob](https://textblob.readthedocs.io) and [VADER](https://www.nltk.org/_modules/nltk/sentiment/vader.html)
    - Test supervised NLP: [Pretrained BERT (state-of-the-art and off-the-shelf)](https://huggingface.co/transformers/main_classes/pipelines.html#transformers.pipeline)
    - Highly skewed data: user text contents were overwhelmingly positive and supportive, unsuitable for existing unsupervised models or off-the-shelf supervised models.
 
3. **Tuning BERT model with proper labelling**
    - Create two type of labels for each text: Tone (netural/positive) and Fact (none/partial/rich)
    - Fine-tune two BERT models through [ktrain](https://arxiv.org/abs/2004.10703) for each label class separately
    - Achieved accuracy score 0.85 and 0.78 for Tone and Fact, respectively
    - Note: another approach is to merge two label classes into one (2x3) to train one model (less costly but weakned prediction: accuracy score 0.67 due to data imbalance)
 
4. **Predicting user subscription within free-trial period**
    - Only use text data generated within the time period of free-trial
    - Extract sentiment features, number of likes, words, characters, as well as their average by comment number for each user
    - Apply a stacking classifier (Random Forest, XGBoost, and Ridge combined by Logistic Regression)
    - Predicted almost all conversion events (recall 0.99, precision 0.60)

5. **Takeaways** 
   - Top predictive features: characters, words, and their averages
   - User engagement level is a key indicator of conversion within the free-trial

## Examples
 <details>
   <summary>Click to show to an example of <b>Emoji and Emoticon Conversion</b></summary>
 <p align="center"><img src="emo_convert.png" /></p>
</details>

 <details>
   <summary>Click to show the <b>Sanity Check</b> of sentiment analysis by different NLP models</summary>
<p align="center"><img src="NLP_benchmark.PNG" /></p>
<p align="center"><b>NLP Models Performance Comparision</b>, OTS: off-the-shelf </p>
</details> 

## Updated 2020/10/11   
[**Current Page**](https://er1czz.github.io/beyondwords)    
[**Return to My GitHub**](https://github.com/er1czz)  



<div align="center"> 
   >>>>>> <b>CC BY 4.0</b> <<<<<<    
</div>


