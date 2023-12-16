# Bee(x)peRt
Immersed in the sea of floating liters of beer within our minds, let's plunge into the intoxicating analysis of experts and their comparison with the "everyday" beer enthusiasts. But how to defines an expert among the customers ? Why should we truly trust what we label as expertise?

Picture a novice local brewery dreaming of its grand opening. Should it place its faith in the masses, in the opinions of the general populace, or should it exclusively lean towards the ratings of the acclaimed experts? In the cacophony of choices, should it navigate the path of a crowd-pleaser or trust the experts to turn its brew into the blockbuster highlight of a Saturday night among friends?

In this flavorful journey, we dissect the essence of expertise, question the reliability of expert ratings, ponder whether a brewery's destiny lies in the hands of the crowd or the discerning palates of insiders, and if it is worthy to pay for some experts advices. Join us in this spirited exploration, where the frothy symphony of data unfolds the secrets of brewing success.

 
## About the Dataset

## Who is an expert ?
In this section we introduce our definition of experts, the ones that could be able to help making our beer successful.
### Distribution of the number of ratings per user
Let's dive into the satistics:


![Plot Title](https://github.com/fpalmisa/ada-project-remontADA/blob/81108e0145e72ff7a1ad0f8c87f5c60276f38499/assets/img/CCDF.png)

Cumulative histogram of the number of ratings per user (all websites)

The distribution has a heavy tail, indicating that there are numerous users who have posted only a few ratings, and conversely, a small number of users who are prolific raters. This observation motivates us to delve deeper into understanding the distinctions between these prolific raters and the rest of the user population. We'll pick up our experts from these figures.

### Define who is a massive rater
In order to separate people in two group, a definition of a massive rater, called from now an "expert" has to be found. The choice was made here to consider the number of ratings per year and aggregate scores from the past 3 years with the formula:
$$
S_{Y_j} = 2 * R_{Y_{j}} + 0.5 * R_{Y_{j-1}} + 0.25 * R_{Y_{j-2}} + 0.1 * R_{Y_{j-3}}
$$
, where $R_{Y_j}$ denotes the number of ratings for the year j and $S_{Y_j}$ is the score of the user for the year j.
The experts are then people from the 0.995 quantile of the score calculate previously (among those who have a non-zero score i.e active users).
These users only represent 0.5 % of active users and yet their influence on the ratings are huge since they account for huge part the final mean rating that will be displayed on the websites.
### What an impact !

PLOOOOOOOOOOOOT avec Rating proportion of experts and non experts for top 16 styles (maybe only one style)(TO DO)

First of all, even if experts account only for 0.5% of the active they represent a big part in the ratings of the beers. There are even some years and styles for which they overtake non experts part. Thus, their voice really matter since hey can make a huge difference for the final average rating displayed on websites.
Plus we found that experts tend to rate beers that are less famous than those that are rated by casual users. Threfore, the fast and early sucess might depend a lot on experts tastes.
PLOOOOOOOOOT avec expert rating proportion as a function of time evolution (cumulative or proportion by year ?)(from the launch of a beer to now, but mean over all the beers (for which there is enough ratings))TO DOOOOOOOOOOOOO




So it might be interesting to know if their ratings differentiate.

- 2 types de raters (experts et non), check la distribution des ratings , définition des experts 

- Qui sont nos experts ? On y répond plus bas ?
  


- Montrer l'impact sur le début des binchs
  
  
- Text Analysis, sentiment analysis (plus négatifs les experts)

- Fin Datastory, différents car ils font bcp de ratings mais en même temps très similaires (tendances très similaires), avis beaucoup plus complexes plus détaillés 

vhjhv bn;,:

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

### Ethics : 
(Done by Fabio)
### Credits : 
This project is done by Laaroussi Yannis, Palmisano Fabio, Roduit Vincent, Roh Vincent, Semiz Alexi for the course of Applied Data Analysis from EPFL (CS-401)
