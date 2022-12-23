---
permalink: /
title: "The amazing website of el famoso Team José"
excerpt: "About me"
author_profile: true
redirect_from: 
  - /about/
  - /about.html
---

Vous pouvez modifier le contenu dans le fichier _pages/about.md


Pour ajouter une plot, mettez le fichier html dans _includes

J'ai mis un fichier d'exemple pour convertir une plot en html --> plotly_to_html.ipynb  
(c'est trivial)

## Touchez à rien d'autre sinon ça pète tout et je viens vous goûmer !!!

Exemple des plots interactives : 

{% include jv_interactif.html %}






# Début du vrai truc 


With the rise of Covid cases and government imposing lockdowns on the population, people were forced into isolation at home hence massively decreasing the mobility of the population. Indeed, by looking at the mobility on google maps of the population in a few countries (Switzerland, United States, France, Australia, Germany, Italy, and Spain) and comparing it to 2019 baseline (ie before the Covid Lockdown), we noticed a mass increase in the percentage of people that stayed at home. 

{% include residential.html %}

Indeed, by performing a bootstrapping on our data and looking at the mean increase in percentage of people that stayed at home compared to the baseline during specific periods of the lockdown.

{% include percentage_residential.html %}

We noticed a huge 475% increase in residential percentage between the period before the lockdown and the beginning of the lockdown (6th March 2020 to 26th March 2020) in the worst-case scenario (upper bound of the confidence interval on the period before lockdown and lower bound of the confidence interval on the period indicating the beginning of the lockdown).
Slowly but surely and with the relief of a lot of the imposed restriction, the people were finally allowed to go out freely and thus the residential percent decreased by 42.6% between the lower confidence bound of period marking the end of the lockdown and the upper confidence bound of the period after the lockdown.
Therefore, it would be very interesting to see if the social hobbies adopted by the population during the lockdown indeed stayed relevant with the ease of the restrictions and the ability of go out of the house once again.


To evaluate which topics became more popular during the lockdown, we decided to compare the Wikipedia pageviews of subjects of each topic before, during and after the lockdown. For each topic, a few relevant and popular subjects were chosen to represent the group.
We then compared the increase/decrease rate of popularity on Wikipedia of each of the topics for a certain period. Since the number of subjects per topic is relatively small (between 5 and 7), we decided to use a bootstrapping on each topic to have a better estimation of the mean and 95 Confidence Interval of views on Wikipedia.
We first evaluate over 1 year from February 2019 and February 2020 to fix a baseline, then right before the lockdown (November 2019 and February 2020), during the lockdown (March 2020 until June 2020), right after the lockdown (July 2020 until October 2020) and finally a long period after the lockdown to have a long-time trend on our study (July 2020 till July 2021). During each one of these periods, we compute the mean of Wikipedia pageviews for each subject of the topic, then do a bootstrapping of 1000 iterations on these means of subjects. For each iteration we look at the mean of the selected samples. We can thus have an average of pageviews of different topics on Wikipedia, as well as confidence intervals.


We first looked at the popularity of video games on Wikipedia (League of Legends, Fortnite, Call of Duty, Minecraft, Roblox, GTA and Dead by Daylight). We notice straight away a quite big increase in mean number of pageviews of these topics during the lockdown. 

{% include videogames.html %}

Indeed, there is a 52.95% increase in viewership during the lockdown compared to right before. Moreover, this trend seems to be a long-term trend (it stayed even after the covid lockdown), although there is a slight decrease of 6.6% in searches after the end of lockdown, there is still a 44.6% increase in searches the following year after the lockdown compared to our baseline of before the lockdown.

{% include percentage_videogames.html %}

We then investigated some board games popularity on Wikipedia (Monopoly, Catan, Scrabble and Chess). In this case, we notice a rise of interest during the lockdown, however it was not a long-term trend as the searches decreased back after the lockdown. 

{% include boardgames.html %}

Indeed, there was a 24.7% increase in interest for board games during the lockdown compared to right before, followed by a 21.9% decrease of interest right after the lockdown compared to during the lockdown. Overall, there is a 2.6% decrease in views right after the end of the lockdown compared to before. Although there might seem to be an increase in popularity of board games the following year after the lockdown, this could be explained by the rise of popularity of chess following the release of “The Queen's Gambit” on Netflix.

{% include percentage_boardgames.html %}

To evaluate the rise of popularity of books, we decided to look at the number of reviews on Amazon Best Sellers per year from 2014 to 2020, as it is a public dataset that is representative of the trend of reading books. 

{% include books.html %}

We can thus look at the percentage increase or decrease between two consecutive years. 

{% include percentage_books.html %}

From 2015 to 2019, we notice that the increase is quite low, and we even in some cases have a decrease. However, between 2019 and 2020, there was a huge and unusual increase of about 125%. This is much bigger than what we had before and could only be explained by a rise of popularity in books during the lockdown. Moreover, to evaluate the unusual rise, we decided to train a linear regression model on the percentage increase of number of reviews up until 2020 (excluded). We can clearly see that the predicted value of 2020 is far lower than the true one, in fact, it is about 7 times lower than the true value! 
