# Who is an expert ?
In this section we introduce our definition of experts, the ones that could be able to help making our beer sucessful.
## Distribution of the number of ratings per user
Let's dive into the satistics:
![Plot Title](https://github.com/fpalmisa/ada-project-remontADA/blob/81108e0145e72ff7a1ad0f8c87f5c60276f38499/assets/img/CCDF.png)
PLOT Cumulative histogram of the number of ratings per user (all websites)

The distribution has a heavy tail, indicating that there are numerous users who have posted only a few ratings, and conversely, a small number of users who are prolific raters. This observation motivates us to delve deeper into understanding the distinctions between these prolific raters and the rest of the user population. We'll pick up our experts from these figures.

## Define who is a massive rater
In order to separate people in two groups, a definition of a massive rater, called from now an "expert" has to be found. The choice was made here to consider the number of ratings per year and aggregate scores from the past 3 years with the formula:
$$
S_{Y_j} = 2 * R_{Y_{j}} + 0.5 * R_{Y_{j-1}} + 0.25 * R_{Y_{j-2}} + 0.1 * R_{Y_{j-3}}
$$
, where $R_{Y_j}$ denotes the number of ratings for the year j and $S_{Y_j}$ is the score of the user for the year j.
The experts are then people from the 0.995 quantile of the score calculate previously (among those who have a non-zero score i.e active users).
These users only represent 0.5 % of active users and yet their influence on the ratings are huge since they account for huge part the final mean rating that will be displayed on the websites.
## What an impact !

PLOOOOOOOOOOOOT avec Rating proportion of experts and non experts for top 16 styles (maybe only one style)(TO DO)

First of all, even if experts account only for 0.5% of the active they represent a big part in the ratings of the beers. There are even some years and styles for which they overtake non experts part. Thus, their voice really matter since hey can make a huge difference for the final average rating displayed on websites.
Plus we found that experts tend to rate beers that are less famous than those that are rated by casual users. Threfore, the fast and early sucess might depend a lot on experts tastes.
PLOOOOOOOOOT avec expert rating proportion as a function of time evolution (cumulative or proportion by year ?)(from the launch of a beer to now, but mean over all the beers (for which there is enough ratings))TO DOOOOOOOOOOOOO

So it might be interesting to know if their ratings differentiate.

