# How Fintech Has Affected the Public Discourse About Banking: Evidence from Twitter
This is a repository that contains all the code used for applying twitter analytics in our MSc. Thesis.

This readme provides a quick summary.

Please note that if Github is unable to load the notebooks, use https://nbviewer.jupyter.org/ instead! There is no need to install it. Direct link: https://nbviewer.jupyter.org/github/AlanRebane/TwitterAnalytics/tree/main/

#### Acknowledgements
1. I would like to thank our supervisor Mark Alexander Conley (github @mac2393) for putting us on the right track and giving us clear instructions on how to approach the research with an academic mindset. Overall, his contribution was invaluable.
2. A big thank you to Alice Zhao (@adashofdata) for her natural language processing tutorial on youtube and scripts on github. The informative video is: "Natural Language Processing in Python" by PyOhio.
3. I am greatful for C.J. Hutto (@cjhutto) for their sentiment analysis tool VADER. After going through at least a thousand tweets, I found that VADER was very accurate in assigning sentiment for a given text.

## 1. Abstract
The purpose of this paper is to understand how fintech has affected the public discourse about banking. The focus area of scholars has mostly been on technical and practical aspects of fintech and largely the public discourse around it has been overlooked. However, many prominent economists have argued that markets are social constructions and the dynamics of the social discourse is reflected in real business activity. By analysing over four million tweets on the Twitter social media platform we try to explain what dominating discourse the fintech movement brings about and how it has changed the public discourse. First, we conclude that since 2016 the number one topic in banking-related discussions on Twitter has been fintech; second, fintech tweets are generally associated with a significantly higher positive sentiment; and third, the positive sentiment of fintech has increased over the years. We add that the public discourse about banking is now mostly controlled by users that are promoting and advancing fintech. We argue that the immense popularity and positive sentiment of fintech enables new financial technology firms to gain power over the incumbents due to the shifting power relations in the market. This in turn could lead to structural changes in the banking market. However, we caution that even though the social stance is supportive towards fintech, the regulation regarding the new technology is largely in development and once enforced, it may favour incumbent banks to maintain control.

We pose the following RQ:

**How has the emergence of fintech affected the public discourse about banking among Twitter users?**

And following the theoretical framework we formulate two hypotheses:

*H1: Compared to other banking-related tweets, fintech tweets are higher in positive sentiment.*

*H2: Among banking tweets, the sentiment of fintech has become more positive over the years.*

## 2. Method
We are interested in comparing two sets of tweets: banking tweets without the word fintech and banking tweets that contain the word fintech. The Venn diagram below highlights the two areas that we are interested in (coloured in grey). To arrive at a statistically significant and robust conclusion regarding the sentiment of tweets and provide evidence for the hypotheses, we employ regression analysis. We used the generalized estimating equation (GEE) approach.

![Figure 5 Venn](https://user-images.githubusercontent.com/63585199/118402752-96a3b880-b66b-11eb-8835-da15381f009d.png)

The regression models are the following:

To answer the first hypotheses:

<a href="https://www.codecogs.com/eqnedit.php?latex=\dpi{200}&space;\tiny&space;SENTIMENT_{t,i}=\alpha&space;&plus;&space;\beta(FINTECH&space;DUMMY)_{t,i}&space;&plus;\gamma&space;CONTROL_{t,i}&plus;\varepsilon&space;_(t,i)" target="_blank"><img src="https://latex.codecogs.com/gif.latex?\dpi{200}&space;\tiny&space;SENTIMENT_{t,i}=\alpha&space;&plus;&space;\beta(FINTECH&space;DUMMY)_{t,i}&space;&plus;\gamma&space;CONTROL_{t,i}&plus;\varepsilon&space;_(t,i)" title="\tiny SENTIMENT_{t,i}=\alpha + \beta(FINTECH DUMMY)_{t,i} +\gamma CONTROL_{t,i}+\varepsilon _(t,i)" /></a>

Where the dependent variable SENTIMENT is a continuous number from –1 to 1 representing the normalized sentiment score from VADER. The FINTECH DUMMY is a dummy variable corresponding to 1 if the tweet contains the word fintech (or #fintech) and 0 if it does not contain the word fintech. CONTROL is a vector of four control variables that include: the number of replies, likes, retweets, and quotes (quotes are retweets with a comment). The subscript t corresponds to a tweet, and subscript i corresponds to a user. 

To answer the second hypothesis:

<a href="https://www.codecogs.com/eqnedit.php?latex=\dpi{200}&space;\tiny&space;SENTIMENT_{t,i}=\alpha&space;&plus;&space;\beta(FINTECH&space;DUMMY)*(YEAR)_{t,i}&space;&plus;\gamma&space;CONTROL_{t,i}&plus;\varepsilon&space;_(t,i)" target="_blank"><img src="https://latex.codecogs.com/gif.latex?\dpi{200}&space;\tiny&space;SENTIMENT_{t,i}=\alpha&space;&plus;&space;\beta(FINTECH&space;DUMMY)*(YEAR)_{t,i}&space;&plus;\gamma&space;CONTROL_{t,i}&plus;\varepsilon&space;_(t,i)" title="\tiny SENTIMENT_{t,i}=\alpha + \beta(FINTECH DUMMY)*(YEAR)_{t,i} +\gamma CONTROL_{t,i}+\varepsilon _(t,i)" /></a>

Here we have an interaction term (FINTECH DUMMY) * (YEAR DUMMY) which represents the vector of interactions between the fintech dummy and years. The years span from 2015 to 2021 and the YEAR DUMMY is equal to one for each specific year. Now the coefficients of interest are βs that represent the effect that fintech tweets have on the sentiment of a tweet in a given year. 

## 3. Key Results
The figure below shows how the portion of fintech tweets in banking has changed over time. Tweeting about fintech became popular in 2015, and starting from 2017, tweets about fintech account for around a fourth of all the banking tweets with a high of 30% in 2020.
![Bankng vs Fintech](https://user-images.githubusercontent.com/63585199/118403008-b9829c80-b66c-11eb-8b9f-3a38f9b16bf1.png)

The table below shows the five most frequent terms in a year for the banking related hashtags while disregarding banking, banks, and bank because naturally, all tweets contain at least one of them. The analysis shows that in the early years of the discussion, banking-related content was attuned towards job seekers as jobs and job were the most frequent words. However, in 2020, fintech-related content is by far the most relevant in the banking discussion. In fact, the top 5 most frequent terms in 2020 besides finance are fintech, digital, payments, and blockchain, which are all technological terms.

![frequent words](https://user-images.githubusercontent.com/63585199/118403042-e1720000-b66c-11eb-8448-6c946cc8c131.png)

The figure below shows that indeed the sentiment of fintech-related tweets has become more positive over the years. As the 99.5% confidence intervals show, we do not have sufficient evidence to reject H2. We conclude that the banking market is largely influenced by financial technology and since the public has a positive stance towards it, we can expect more banks to follow the invading fintech companies and adjust their services accordingly. Therefore, we argue that the power to decide how and which banking services are provided will be increasingly more decided by small fintech companies rather than incumbent banks.
![H4_visual](https://user-images.githubusercontent.com/63585199/118403176-78d75300-b66d-11eb-8d6d-fc4321968c80.png)

*Note that fintech sentiment represents the additional positive sentiment that fintech-related tweets have versus other banking-related tweets after controlling for user fixed effects, likes, retweets, replies and quotes.*

## 4. Conclusion and Limitations
To answer the research question: “How has the emergence of fintech affected the public discourse about banking among Twitter users?” we conclude that since 2016 the number one topic of interest in banking-related discussions has been financial technology, and fintech tweets are generally associated with a higher positive sentiment that has increased over the years. We add that the public discourse is now mostly controlled by users that are devoted to advancing fintech.

We consider the main limitations of this study to be the lack of information on state regulation regarding the new financial technology; evidence on real banking activity which would give us insights how banks are internally changing their strategy; and the limited sample of Twitter users, which may not necessarily be representative of the people who have a strong influence on the public discourse about banking.
