# NBA Draft Analysis (2010-2021)
Once per year, prior to every NBA (National Basketball Association) season, NBA teams select  
new players out of college and international leagues in a draft. Ultimately, 60 players are selected in  order from pick 1 through 60. The purpose of our analysis/study is to examine the relationship between  which pick a player was selected with and that player’s 1st year performance and will be looking at the  last 11 drafts (2010-2021). Additionally, we also examined the relationship between where a player played college basketball and first year performance, as well as the relationship between the team that drafts the player and first year performance. To accomplish these, we compiled a dataset containing the draft pick a player was selected with, the team that selected the player, that player’s descriptive statistics (ex. age, college attended, state of college attended, etc.), and that player’s rookie year statistics (ex. assists, blocks, points per game, etc.).



Our dataset has 32 columns, and 660 rows. Due to having a high number of features, it is important that we focus in and pinpoint the specific features we are trying to examine in relationship to when a player is picked. It is important that we do not get lost in potentially redundant data or irrelevant data within our dataset. The correlation matrix we have currently only contains 14 out of the 32 features, so our next steps would be to hone in on the variables that we want to further examine (whether that be by adding more features or take away features from the correlation matrix).


<img width="1800" alt="data" src="https://user-images.githubusercontent.com/66886936/116904257-77d50900-ac0b-11eb-98a3-820409fd772d.png">

After preprocessing and choosing our variables, we cleaned up our data:

<img width="800" alt="Untitled1" src="https://user-images.githubusercontent.com/66886936/116956067-57846900-ac62-11eb-866c-7c676eb3f81f.png">


The first visualization we created was a correlation matrix with each of the potential variables of interest. Specifically, we examined the “pick” variable and its relationship with the other variables and in particular, noticed strong correlations between the order in the draft that the player was selected and that player's first year per-game statistics. In the case of our data, a negative correlation with pick means that the players drafted earlier outperformed the players that were picked later in the draft. We honed in on the negative correlations for points per game, rebounds per game, and assists per game, and examined these variables through a variety of other visualizations. 

<img width="600" alt="download (1)" src="https://user-images.githubusercontent.com/66886936/116953555-9531c380-ac5b-11eb-91dc-02173b6067e2.png">

In order to examine the average performance of each draft pick over the last eleven years, we created a line graph of important per-game statistics. The draft pick number is shown on the x-axis and the y-axis displays the average per-game value for each statistic. We chose to take a deeper look into points-per-game, rebounds-per-game, and assists-per-game, as these stats are often regarded as the most important and because from our correlation matrix, we have pinpointed these variables to have relatively strong negative correlations with the ‘pick’ variable. We can see that earlier picks generally outperform later picks, and in every case, the first round picks display significantly higher statistics. 

<img width="800" alt="Dashboard 3" src="https://user-images.githubusercontent.com/66886936/116955535-d8dafc00-ac60-11eb-8735-22430c63f255.png">

Since each NBA draft is broken into round one (picks 1-30) and round two (picks 31-60), we wanted to see if there was a significant difference in performance by round and expand on some of the insights from the line chart. We decided to perform TSNE on the NBA first-year performance by round to examine this idea. From the visualization we can see that while there is some overlap, rounds one and two are clustered. This suggests that players selected in round one generally perform like other players selected in round one with a similar relationship evident between round two players. Further this suggests that occasionally, a player selected in round one performs more like a player selected in round two and vice versa.  

![nba_tsne](https://user-images.githubusercontent.com/66886936/116956986-a3d0a880-ac64-11eb-99cf-4da65f097720.png)


Similar to the TSNE analysis, we decided to perform PCA to examine first-year performance by round. Our results show more overlap than in the TSNE plot, however, there is still evident clustering for each round, which further supports our hypothesis from our TSNE analysis that players selected in round one can be generally differentiated from players selected in round two by looking at the player’s per-game statistics. 





<img width="1762" alt="Dashboard 2" src="https://user-images.githubusercontent.com/66886936/116956869-5ce2b300-ac64-11eb-9c03-1d57215855d8.png">
<img width="1762" alt="Dashboard 1" src="https://user-images.githubusercontent.com/66886936/116956877-5f450d00-ac64-11eb-8768-f5e283b72890.png">


