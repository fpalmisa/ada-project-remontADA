
# <center>Bee(x)peRt</center>
Immersed in the sea of floating liters of beer within our minds, let's plunge into the intoxicating analysis of experts and their comparison with the "everyday" beer enthusiasts. But how to defines an expert among the customers ? Why should we truly trust what we label as expertise?

Picture a novice local brewery dreaming of its grand opening. Should it place its faith in the masses, in the opinions of the general populace, or should it exclusively lean towards the ratings of the acclaimed experts? In the cacophony of choices, should it navigate the path of a crowd-pleaser or trust the experts to turn its brew into the blockbuster highlight of a Saturday night among friends?

In this flavorful journey, we dissect the essence of expertise, question the reliability of expert ratings, ponder whether a brewery's destiny lies in the hands of the crowd or the discerning palates of insiders, and if it is worthy to pay for some experts advices. Join us in this spirited exploration, where the frothy symphony of data unfolds the secrets of brewing success.

## <center>About the Dataset</center>

This dataset consists beer reviews collected over period of 17 years (2001 to 2017) from two beer rating websites: BeerAdvocate (https://www.beeradvocate.com/) and RateBeer (https://www.ratebeer.com/). The dataset contain both textual and numerical data.

Following some analysis, the decision was made to merge the datasets from both platforms. This merging process aimed to obtain more robust and meaningful results in terms of expert and non-expert ratings. It was observed that combining both datasets reduces more the bias than considering each dataset in isolation. To mitigate potential biases introduced by the merger, a standardization procedure was implemented for the different rating systems used by the two websites.

To increase comparability, users on one website were linked with their counterparts on the other website, and a similar linkage process was applied to beers. This approach ensures a more equitable evaluation of ratings across the merged dataset, providing a foundation for reliable and unbiased analyses.


## <center>Who is an expert ?</center>
In this section we introduce our definition of experts, the ones that could be able to help making our beer successful.
### <center>Distribution of the number of ratings per user</center>
Let's dive into the satistics:


<div align="center">
  <img src="https://raw.githubusercontent.com/fpalmisa/ada-project-remontADA/81108e0145e72ff7a1ad0f8c87f5c60276f38499/assets/img/CCDF.png" alt="Plot Title">
</div>


The distribution has a heavy tail, indicating that there are numerous users who have posted only a few ratings, and conversely, a small number of users who are prolific raters. This observation motivates us to delve deeper into understanding the distinctions between these prolific raters and the rest of the user population. We'll pick up our experts from these figures.
### <center>Define who is a massive rater</center>

In order to separate people in two group, a definition of a massive rater, called from now an "expert" has to be found. The choice was made here to consider the number of ratings per year and aggregate scores from the past 3 years with the formula:

$S_{Y_j} = 2 \cdot R_{Y_{j}} + 0.5 \cdot R_{Y_{j-1}} + 0.25 \cdot R_{Y_{j-2}} + 0.1 \cdot R_{Y_{j-3}}$

, where $R_{Y_j}$ denotes the number of ratings for the year j and $S_{Y_j}$ is the score of the user for the year j.
The experts are then people from the 0.995 quantile of the score calculate previously (among those who have a non-zero score i.e active users).
These users only represent 0.5 % of active users and yet their influence on the ratings are huge since they account for huge part the final mean rating that will be displayed on the websites.

### <center>What an impact !</center>


<div align="center">
  <img src="https://github.com/fpalmisa/ada-project-remontADA/blob/a72c07490fb8da00ab6ad8939e5b2e1a9b3964d3/assets/img/paleale.png" alt="Plot Title">
</div>

First of all, even if experts account only for 0.5% of the active they represent a big part in the ratings of the beers. There are even some years and styles for which they overtake non experts part. Thus, their voice really matter since they can make a huge difference for the final average rating displayed on websites.

Plus we found that experts tend to rate beers that are less famous than those that are rated by casual users. Threfore, the fast and early sucess might depend a lot on experts tastes.

<div align="center">
  <img src="https://github.com/fpalmisa/ada-project-remontADA/blob/1c4b4ab5cb9b68dec1e6dd1118cc98136ba803f7/assets/img/expert_proportion_since_begining.png" alt="Plot Title">
</div>


So it might be interesting to know if their ratings differentiate.

<div align="center">
  <img src="https://github.com/fpalmisa/ada-project-remontADA/blob/1c4b4ab5cb9b68dec1e6dd1118cc98136ba803f7/assets/img/mean_ratings_experts_casuals.png" alt="Plot Title">
</div>

It has been observed that experts tend to assess beers more critically than non-experts. However, despite these discernible distinctions, a common trend in ratings emerges, indicating that specific qualities are universally appreciated or disliked across both groups. 



## ----------------------------------------------------------

- Différence entre experts et casual⇒ plus sévère, notent pas les mêmes bières etc. (Grades, Text Analysis)

- Mais quand même ils sont pareils, mêmes tendances etc.

- Analyse plus complexes/précises

- 2 types de raters (experts et non), check la distribution des ratings , définition des experts 

- Qui sont nos experts ? On y répond plus bas ?
  
- Montrer l'impact sur le début des binchs

- Text Analysis, sentiment analysis (plus négatifs les experts)

- Fin Datastory, différents car ils font bcp de ratings mais en même temps très similaires (tendances très similaires), avis beaucoup plus complexes plus détaillés 

Fil conducteur:
- titre, question intro
- Il existe 2 types de users, donc légitime de se poser la question des différences (parce que high volume raters ⇒ impact)
- Définition de nos experts
- Différence entre experts et casual⇒ plus sévère, notent pas les mêmes bières etc.
- Mais quand même ils sont pareils, mêmes tendances etc.
- Leurs analyses sont plus complexes/précises etc
- 


### Contributions 
Fabio : 
Yannis : 
Vincent R. :
Vincent Roh : 
Alexi : 

### <center>Ethics !</center>

<div align="center">
  <img src="https://raw.githubusercontent.com/fpalmisa/ada-project-remontADA/81108e0145e72ff7a1ad0f8c87f5c60276f38499/assets/img/ethic.jpeg" alt="Plot Title">
</div>

In contemporary machine learning and applied data analysis projects like Beer Reviews Analysis, the evaluation of ethical risks is gaining importance. The master course at EPFL provided a brief introduction on how to navigate these risks using a helpful canvas. As designers of this kind of project, it is the responsibility to assess potential impacts and address them responsibly.

Focusing specifically on the Beer Analysis, one identifiable ethical risk involves influencing consumer choices. There are both indirect stakeholders, who are impacted by the system but do not directly interact with it (including the Public, Government, Environment, and Friends), and direct stakeholders, such as admins, end-users, or contractors, who have direct interactions with the system.

Taking the example of influencing consumer choices, considering only direct stakeholders, which are the customers. If the dataset is used to manipulate consumer choices by promoting certain beers over others through fake reviews or biased recommendations, it can be deceptive and unethical.

In this project, the aim is to use both datasets, incorporating the maximum number of reviews possible to minimize bias in consumer reviews and recommendations. Relying on only one dataset could introduce more bias into consumer choices. Hence, incorporating both datasets serves as an additional measure to mitigate bias and provide more robust and unbiased consumer advice.

### Credits : 
This project is done by Laaroussi Yannis, Palmisano Fabio, Roduit Vincent, Roh Vincent, Semiz Alexi for the course of Applied Data Analysis from EPFL (CS-401)
