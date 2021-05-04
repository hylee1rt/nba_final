# NBA Draft Analysis (2010-2021)

Once per year, prior to every NBA (National Basketball Association) season, NBA teams select new players out of college and international leagues in a draft. Ultimately, 60 players are selected in  order from pick 1 through 60. The purpose of our analysis/study is to examine the relationship between  which pick a player was selected with and that player’s 1st year performance and will be looking at the  last 11 drafts (2010-2021). To do this, we compiled a dataset containing the draft pick a player was selected with, the team that selected the player, that player’s descriptive statistics (ex. age, college attended, state of college attended, etc.), and that player’s rookie year statistics (ex. assists, blocks, points per game, etc.).


Our dataset has 32 columns, and 660 rows. Due to having a high number of features, it is important that we focus in and pinpoint the specific features we are trying to examine in relationship to when a player is picked. It is important that we do not get lost in potentially redundant data or irrelevant data within our dataset. The correlation matrix we have currently only contains 14 out of the 32 features, so our next steps would be to hone in on the variables that we want to further examine (whether that be by adding more features or take away features from the correlation matrix).


<img width="1500" alt="data" src="https://user-images.githubusercontent.com/66886936/116904257-77d50900-ac0b-11eb-98a3-820409fd772d.png">

After preprocessing and choosing our variables, we cleaned up our data:

<img width="800" alt="Untitled1" src="https://user-images.githubusercontent.com/66886936/116956067-57846900-ac62-11eb-866c-7c676eb3f81f.png">


The first visualization we created was a correlation matrix with each of the potential variables of interest. Specifically, we examined the “pick” variable and its relationship with the other variables and in particular, noticed strong correlations between the order in the draft that the player was selected and that players first year per-game statistics. In the case of our data, a negative correlation with pick means that the players drafted earlier outperformed the players that were picked later in the draft. We honed in on the negative correlations for points per game, rebounds per game, and assists per game, and examined these variables through a variety of other visualizations. 

![download (1)](https://user-images.githubusercontent.com/66886936/116953555-9531c380-ac5b-11eb-91dc-02173b6067e2.png)
In order to examine the average performance of each draft pick over the last eleven years, we created a line graph of important per-game statistics. The draft pick number is shown on the x-axis and the y-axis displays the average per-game value for each statistic. We chose to take a deeper look into points-per-game, rebounds-per-game, and assists-per-game, as these stats are often regarded as the most important and because from our correlation matrix, we have pinpointed these variables to have relatively strong negative correlations with the ‘pick’ variable. We can see that earlier picks generally outperform later picks, and in every case, the first round picks display significantly higher statistics.

<img width="1000" alt="Dashboard 3" src="https://user-images.githubusercontent.com/66886936/116955535-d8dafc00-ac60-11eb-8735-22430c63f255.png">
