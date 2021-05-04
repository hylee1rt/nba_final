# NBA Draft Analysis (2010-2021) 
Once per year, prior to every NBA (National Basketball Association) season, NBA teams select  
new players out of college and international leagues in a draft. Ultimately, 60 players are selected in  order from pick 1 through 60. The purpose of our analysis/study is to examine the relationship between  which pick a player was selected with and that player’s 1st year performance and will be looking at the  last 11 drafts (2010-2021). Additionally, we also examined the relationship between where a player played college basketball and first year performance, as well as the relationship between the team that drafts the player and first year performance. To accomplish these, we compiled a dataset containing the draft pick a player was selected with, the team that selected the player, that player’s descriptive statistics (ex. age, college attended, state of college attended, etc.), and that player’s rookie year statistics (ex. assists, blocks, points per game, etc.).



Our dataset has 32 columns, and 660 rows. Due to having a high number of features, it is important that we focus in and pinpoint the specific features we are trying to examine in relationship to when a player is picked. It is important that we do not get lost in potentially redundant data or irrelevant data within our dataset. The correlation matrix we have currently only contains 14 out of the 32 features, so our next steps would be to hone in on the variables that we want to further examine (whether that be by adding more features or take away features from the correlation matrix).


<img width="1800" alt="data" src="https://user-images.githubusercontent.com/66886936/116904257-77d50900-ac0b-11eb-98a3-820409fd772d.png">

After preprocessing and choosing our variables, we cleaned up our data:

<img width="800" alt="Untitled1" src="https://user-images.githubusercontent.com/66886936/116956067-57846900-ac62-11eb-866c-7c676eb3f81f.png">


* The first visualization we created was a correlation matrix with each of the potential variables of interest. Specifically, we examined the “pick” variable and its relationship with the other variables and in particular, noticed strong correlations between the order in the draft that the player was selected and that player's first year per-game statistics. In the case of our data, a negative correlation with pick means that the players drafted earlier outperformed the players that were picked later in the draft. We honed in on the negative correlations for points per game, rebounds per game, and assists per game, and examined these variables through a variety of other visualizations. 

<img width="600" alt="download (1)" src="https://user-images.githubusercontent.com/66886936/116953555-9531c380-ac5b-11eb-91dc-02173b6067e2.png">

* In order to examine the average performance of each draft pick over the last eleven years, we created a line graph of important per-game statistics. The draft pick number is shown on the x-axis and the y-axis displays the average per-game value for each statistic. We chose to take a deeper look into points-per-game, rebounds-per-game, and assists-per-game, as these stats are often regarded as the most important and because from our correlation matrix, we have pinpointed these variables to have relatively strong negative correlations with the ‘pick’ variable. We can see that earlier picks generally outperform later picks, and in every case, the first round picks display significantly higher statistics. 

<img width="800" alt="Dashboard 3 (2)" src="https://user-images.githubusercontent.com/66886936/116959022-5b1bee00-ac6a-11eb-98e6-e77d1a70ab4b.png">


* Since each NBA draft is broken into round one (picks 1-30) and round two (picks 31-60), we wanted to see if there was a significant difference in performance by round and expand on some of the insights from the line chart. We decided to perform TSNE on the NBA first-year performance by round to examine this idea. From the visualization we can see that while there is some overlap, rounds one and two are clustered. This suggests that players selected in round one generally perform like other players selected in round one with a similar relationship evident between round two players. Further this suggests that occasionally, a player selected in round one performs more like a player selected in round two and vice versa. 

* Similar to the TSNE analysis, we decided to perform PCA to examine first-year performance by round. Our results show more overlap than in the TSNE plot, however, there is still evident clustering for each round, which further supports our hypothesis from our TSNE analysis that players selected in round one can be generally differentiated from players selected in round two by looking at the player’s per-game statistics. 




|TSNE                        | PCA   | 
|--------------------------------|--------------------|
|<img width="400" alt="nba_tsne" src="https://user-images.githubusercontent.com/66886936/116956986-a3d0a880-ac64-11eb-99cf-4da65f097720.png"> | <img width="400" alt="nba_pca" src="https://user-images.githubusercontent.com/66886936/116957223-57399d00-ac65-11eb-8097-b2e5a56908bc.png"> |

From our PCA loadings, we can see that there are a few variables with high proportion of variance, which indicates that those are the most influential variables. We can eliminate the other variables if we wanted to narrow down even more for further analysis.

<img width="231" alt="loadings" src="https://user-images.githubusercontent.com/66886936/116959370-72a7a680-ac6b-11eb-875a-490e688f360f.png">


* We wanted to further examine what differentiated round one picks and round two picks, so we looked at the age distributions of each round. The box plots reveal that the median age of players selected in round one is much lower than in round two. The median age for round one is twenty, while the median age for round two is twenty-two. Further the average age of players selected in round one are also substantially lower when compared to players selected in round two. This shows us that younger players are more likely to be picked earlier in the draft. Additionally the distribution of age of round one picks is right skewed, showing that while the majority of players were young, with many as young as nineteen, there were a few very old players making the distribution positively skewed. The distribution of age of round two picks appears normal, with a single outlier, but should be noted that the distribution is slightly left skewed as the mean is less than the mean. Additionally, we looked at the average points per game distributions by round. The box plot for round one shows that several players picked in the first round performed exceptionally well. These outliers reveal that round one picks have significantly higher ceilings than those picked in round two. Furthermore, the mean and median for the average points per game for round one picks are also noticeably higher than the mean and medians for the average points per game for round two picks. This further suggests that on average, players in round one score more points per game on average than players selected in round two. It should also be noted that both the distribution for round one and round two picks are slightly right skewed. 

|Age                        | Points   | 
|--------------------------------|--------------------|
|<img width="400" alt="rhlee@email wm edu (1)" src="https://user-images.githubusercontent.com/66886936/116957262-72a4a800-ac65-11eb-9ce7-293827a87119.png"> | <img width="400" alt="rhlee@email wm edu (2)" src="https://user-images.githubusercontent.com/66886936/116957481-f199e080-ac65-11eb-9df8-5ac632778701.png"> |

* Further, we looked to examine the relationship between the state that players played college basketball in and their average first year performances, so we created a heatmap of the average points per game of drafted players by the state that they played college basketball in. The visualization shows that players who were drafted from the state of Alabama performed substantially better than the players in the other states with an average 11.4 points per game in their first year. It also revealed that some states have had no draft picks in the past eleven years. From this heatmap we can see that players who play in certain states for college before being drafted into the NBA perform better than players from other states. In order to do that, we added a couple of new columns to our data:

<img width="828" alt="Capture" src="https://user-images.githubusercontent.com/66886936/116958471-c5cc2a00-ac68-11eb-851c-319d5a1b22a7.PNG">


* The figure below shows that players who were drafted from the state of Alabama performed substantially better than the players in the other states with an average 11.4 points per game in their first year. It also revealed that some states have had no draft picks in the past eleven years. From this heatmap we can see that players who play in certain states for college before being drafted into the NBA perform better than players from other states.


<img width="1762" alt="Dashboard 1 (1)" src="https://user-images.githubusercontent.com/66886936/116958289-142cf900-ac68-11eb-89a9-67117ed5c4e5.png">

* Lastly, we also wanted to analyze the performance of NBA teams themselves, specifically how well they draft. This map shows each NBA team's location and the average first year points per game of their draft picks. The map reveals that a few teams, particularly the Charlotte Hornets, the Washington Wizards, the Cleveland Cavaliers, and the New York Knicks, generally pick players that average higher points per game in their first year than the rest of the NBA teams.

<img width="1762" alt="Dashboard 2 (1)" src="https://user-images.githubusercontent.com/66886936/116958298-20b15180-ac68-11eb-9873-0a8249722789.png">





All data was obtained from https://www.basketball-reference.com/.
