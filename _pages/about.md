---
permalink: /
title: "A data story about entertainment"
excerpt: "About me"
author_profile: true
redirect_from: 
  - /about/
  - /about.html
---


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

Indeed, there is a 52.3% increase in viewership during the lockdown compared to right before. Moreover, this trend seems to be a long-term trend (it stayed even after the covid lockdown), although there is a slight decrease of 8.46% in searches after the end of lockdown, there is still a 50.4% increase in searches the following year after the lockdown compared to our baseline of before the lockdown.

{% include percentage_videogames.html %}

We then investigated some board games popularity on Wikipedia (Monopoly, Catan, Scrabble and Chess). In this case, we notice a rise of interest during the lockdown, however it was not a long-term trend as the searches decreased back after the lockdown. 

{% include boardgames.html %}

Indeed, there was a 32.1% increase in interest for board games during the lockdown compared to right before, followed by a 22.5% decrease of interest right after the lockdown compared to during the lockdown. Overall, there is a 2.4% decrease in views right after the end of the lockdown compared to before. Although there might seem to be an increase in popularity of board games the following year after the lockdown, this could be explained by the rise of popularity of chess following the release of “The Queen's Gambit” on Netflix.

{% include percentage_boardgames.html %}

To evaluate the rise of popularity of books, we decided to look at the number of reviews on Amazon Best Sellers per year from 2014 to 2020, as it is a public dataset that is representative of the trend of reading books. 

{% include books.html %}

We can thus look at the percentage increase or decrease between two consecutive years. 

{% include percentage_books.html %}

From 2015 to 2019, we notice that the increase is quite low, and we even in some cases have a decrease. However, between 2019 and 2020, there was a huge and unusual increase of about 125%. This is much bigger than what we had before and could only be explained by a rise of popularity in books during the lockdown. Moreover, to evaluate the unusual rise, we decided to train a linear regression model on the percentage increase of number of reviews up until 2020 (excluded). We can clearly see that the predicted value of 2020 is far lower than the true one, in fact, it is about 7 times lower than the true value! 

# Live streaming

Twitch is the biggest video games streaming platform where people can share their video games sessions with their viewers and interact with them using a chat.

Since the lockdown created a lack of social interactions, it would be interesting to see the evolution of Twitch to measure how such a platform was able to unite people together around a shared hobby both from streamers and viewers perspective.

{% include twitch_evol_hours_watched.html %}

There has been a noticable increase in watch time since the start of the lockdown. People had more free time and looked for social interactions with streamers and other viewers under the video game distraction.

{% include twitch_evol_number_users.html %}

We realise also that the number of viewers, streams and channels has greatly increased since the start of the lockdown and was able to maintain their numbers even after the lockdown has ended. Since people had more time to spend at home during the lockdown, already existing streamers had more time to stream their games and some new gamers have decided to share their gaming sessions with their friends.

{% include twitch_diff_global.html %}

The watch time, number of viewers and number of channels follow all a very similar shape with a great increase at the start of the lockdown and a slower increase after the end of the lockdown. The number of streams also follows the same evolution but at a smaller rate. This may be due to the material requirements of streaming that not everyone can comply to.

To dig deeper, we will see if some video games have obtained more attention during this period compared to others.

{% include twitch_evol_top_games.html %}

For the top 10 games at that time on the platform, there has been a general increase in both hours streamed and hours watched. Let's see the difference of those hours between the times before, during and after the lockdown.

{% include twitch_diff_top_games.html %}

From the streamers perspective, all games got their streaming time increased but we notice an interesting outlier. Fortnite obtained much more stream time during the lockdown but also got a severe decrease after the lockdown ended. This is due to Fortnite being the most popular game by far in 2020. Therefore people wanting to start streaming will choose to play their favorite game which ended up being Fortnite. However, when the lockdown ended, these new streamers did no longer have enough time to spend on streaming or perfered to do some outside activities which ends up decreasing Fortnite streaming hours.

From the viewers perspective, the first thing to notice is that all games received an increase in viewership at the start of the lockdown except World of Warcaft. World of Warcraft (WoW) is a MMO-RPG and thus a game heavily based on social interactions with other players. For new players or viewers, WoW is also not a game that provides a viewer-friendly experience due to the highly customisable interface and complexity of the game. Those two reasons imply that new viewers probably won't enjoy watching and WoW players would spend more time in game instead of watching it on Twitch.

Just Chatting is a category that dominated in viewers during this whole time period. Since Just Chatting is not a game but a category used by streamers that just want to talk and interact with their community without having to focus on playing a game, it shows that viewers are really looking for social interactions.

It is also interesting that even though Fortnite was the most popular game at the time and had the most streamed hours, in terms of watch time, it stays on par with other games. It shows that it is not a game suitable for interacting with the chat because it requires permanent attention of the player.


# Gaming

The fact that everyone had to work from home created a lot of changes in our work life. A lot of meetings had to take place via video conference, lecture in schools and universities were held entirely online, and every office job had to take place at home. Everyone had to adapt to the situation for the worse or the better. 

But it also means no more monitoring of one's computer activities. Let's take a look at the activities of the players on Steam, the leading gaming platform for computer games : 

{% include steam_histo.html %}


It is difficult to compare the single and multiplayer games due to the bigger popularity of the latter. We see a very big increase in the daily players in multiplayer games, but due to the huge baseline number, it is hard to say if people really prefered multiplayer games.

Before the lockdown, we can see that the number of player is changing slightly with seasonal variation, with some sudden spikes in daily players when a new game or a new extension in an existing game is made available. This has been a continuous tendency for the months before the lockdown. But a new dynamic arrives with the Covid-19 outbreak. During lockdown, a lot more people suddenly started playing computer games on a more regular basis.

But is that a simple tendency ? It is entirely possible that a few new videogames and extensions went out in the same interval of time. Is it only a coincidence that so many beople picked up gaming at the same time. 

To understand the situation a bit better, we can compare the year 2019, the lockdown period, and the end of 2020, when everything is back to normal and everyone is back to work. 

Let's take a closer look :

{% include steam_percentage.html %}

We see practically zero changes between the baseline in 2019 and the following of the lockdown. The number of players immediately went down both in multiplayer and single player games. This show the very particular tendency that happened during covid. The absence of socializing events and the increase of free time made people find other ways to distract themselves. 

This sudden interest for videogames is also visible on Google trends : 

{% include gtrends.html %}

The Google Trends score is computed on the relative value of each subject. so for a given subject, the score of 100 would be the time were this subject was at the top of it's popularity.

Videogames have not only seen a great increase on daily players, but were also at the top of their popularity on the web during lockdown. This shows that people not only used this as a way to entertain themselves during lockdown, but it created a complete shift in people's interests. A higher popularity score also means that paople made more searches on videogames, created more content on youtube and social media, watched more streams and invested more time into it.
