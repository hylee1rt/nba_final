# NBA Draft Analysis (2010-2021) 
Once per year, prior to every NBA (National Basketball Association) season, NBA teams select
new players both from college and international leagues in a draft. Ultimately, 60 players are selected in order from pick 1 through 60. The purpose of our analysis/study is to examine the relationship between which pick a player was selected and that player’s 1st year performance. We looked at the last 11 drafts (2010-2021). Additionally, we examined the relationship between where a player played college basketball and first year performance, as well as the relationship between the team that drafts the player and first year performance. To accomplish these goals, we compiled a dataset containing the draft pick a player was selected, the team that selected the player, that player’s descriptive statistics (ex. age, college attended, state of college attended, etc.), and that player’s rookie year statistics (ex. assists, blocks, points per game, etc.).


Our dataset originally had 32 columns, and 660 rows. Due to having a high number of features, it was important to focus in and pinpoint the specific features that relate to when a player is picked. We made it a priority to exclude irrelevant or potentially redundant data within our dataset. 

We wanted to observe the per-game statistics for each player, so we dropped variables that were redundant (repetitive columns with different names) or not quantitative (such as name and college). Players with NULL values in their statistics did not play their first year, so we dropped those players. We ended up with 529 rows and 15 columns. 

After preprocessing, our dataset looks like:

<img width="1500" alt="Untitled" src="https://user-images.githubusercontent.com/66886936/118314414-1b52d300-b4c2-11eb-82f3-f424fe447c69.png">


The first visualization we created was a correlation matrix with each of the potential variables of interest. Specifically, we examined the pick (pk) variable and its relationship with the other variables. We noticed strong correlations between the order in the draft that the player was selected and that player’s first year statistics. In the case of our data, a negative correlation with pick (pk) means that the players drafted earlier outperformed the players that were picked later in the draft. We honed in on the negative correlations for points per game (PPG), total rebounds (RPG), and total assists (APG), and examined these variables through a variety of other visualizations.


<img width="600" alt="nbaheatmap (2)" src="https://user-images.githubusercontent.com/66886936/118314179-c4e59480-b4c1-11eb-9656-8fe469a36180.png">



In order to examine the average performance of each draft pick over the last eleven years, we created a line graph of important per-game statistics. The draft pick number is shown on the x-axis and the y-axis displays the average per-game value for each statistic. We chose to take a deeper look into points-per-game (PPG), rebounds-per-game (RPG), and assists-per-game (APG), as these stats are often regarded as the most important. Additionally, our correlation matrix showed that these variables have relatively strong negative correlations with the ‘pick’ variable. We can see that earlier picks generally outperform later picks, and in every case, the first round picks display significantly higher statistics.

<img width="800" alt="Dashboard 3 (4)" src="https://user-images.githubusercontent.com/66886936/118309382-2eae7000-b4bb-11eb-918c-9d1df4d53e14.png">


Since each NBA draft is broken into round one (picks 1-30) and round two (picks 31-60), we wanted to see if there was a significant difference in performance by round and expand on some of the insights from the line chart. We decided to perform TSNE on the NBA first-year performance by round to examine this idea. From the visualization we can see that while there is some overlap, rounds one and two are clustered. This suggests that players selected in round one generally perform like other players selected in round one with a similar relationship evident between round two players. Further this suggests that occasionally, a player selected in round one performs more like a player selected in round two and vice versa. 

Similar to the TSNE analysis, we decided to perform PCA to examine first-year performance by round. Our results show more overlap than in the TSNE plot, however, there is still evident clustering for each round, which further supports our hypothesis from our TSNE analysis that players selected in round one can be generally differentiated from players selected in round two by looking at the player’s per-game statistics. 



|     TSNE                        |   PCA   | 
|:--------------------------------:|:--------------------:|
|<img width="400" alt="nba_tsne (1)" src="https://user-images.githubusercontent.com/66886936/118314258-e5155380-b4c1-11eb-9896-597db46a0ef7.png"> | <img width="400" alt="nba_pca (1)" src="https://user-images.githubusercontent.com/66886936/118314236-daf35500-b4c1-11eb-9cf2-3bc478a7a5e5.png"> |




From our PCA loadings, we can see that there are a few variables with high proportion of variance, which indicates that those are the most influential variables. We can eliminate the other variables if we wanted to narrow down even more for further analysis.

<img width="231" alt="loadings" src="https://user-images.githubusercontent.com/66886936/116959370-72a7a680-ac6b-11eb-875a-490e688f360f.png">


We wanted to further examine what differentiated round one picks and round two picks, so we looked at the age distributions of each round. The box plots reveal that the median age of players selected in round one is much lower than in round two. The median age for round one is twenty, while the median age for round two is twenty-two. Further the average age of players selected in round one are also substantially lower when compared to players selected in round two. This shows us that younger players are more likely to be picked earlier in the draft. Additionally the distribution of age of round one picks is right skewed, showing that while the majority of players were young, with many as young as nineteen, there were a few very old players making the distribution positively skewed. The distribution of age of round two picks appears normal, with a single outlier, but should be noted that the distribution is slightly left skewed as the mean is less than the mean. Additionally, we looked at the average points per game distributions by round. The box plot for round one shows that several players picked in the first round performed exceptionally well. These outliers reveal that round one picks have significantly higher ceilings than those picked in round two. Furthermore, the mean and median for the average points per game for round one picks are also noticeably higher than the mean and medians for the average points per game for round two picks. This further suggests that on average, players in round one score more points per game on average than players selected in round two. It should also be noted that both the distribution for round one and round two picks are slightly right skewed. 

|Age                        | Points   | 
|:--------------------------------:|:--------------------:|
|<img width="500" alt="nba_box_age (2)" src="https://user-images.githubusercontent.com/66886936/118311759-4fc49000-b4be-11eb-8767-702c21b05d29.png"> | <img width="500" alt="nba_box_pts (2)" src="https://user-images.githubusercontent.com/66886936/118311757-4e936300-b4be-11eb-8a3b-afbf17d1897b.png"> |



Further, we looked to examine the relationship between the state that players played college basketball in and their average first year performances, so we created a heatmap of the average points per game of drafted players by the state that they played college basketball in. The visualization shows that players who were drafted from the state of Alabama performed substantially better than the players in the other states with an average 11.4 points per game in their first year. It also revealed that some states have had no draft picks in the past eleven years. From this heatmap we can see that players who play in certain states for college before being drafted into the NBA perform better than players from other states. In order to do that, we added a couple of new columns to our data:

<img width="828" alt="Capture (2)" src="https://user-images.githubusercontent.com/66886936/118310165-3b7f9380-b4bc-11eb-92f2-6b36cd89e928.PNG">


The figure below shows that players who were drafted from the state of Alabama performed substantially better than the players in the other states with an average 11.4 points per game in their first year. It also revealed that some states have had no draft picks in the past eleven years. From this heatmap we can see that players who play in certain states for college before being drafted into the NBA perform better than players from other states.


<img width="1762" alt="Dashboard 1 (2)" src="https://user-images.githubusercontent.com/66886936/118308527-0bcf8c00-b4ba-11eb-90a2-6b2d6517fd78.png">



Lastly, we also wanted to analyze the performance of NBA teams themselves, specifically how well they draft. This map shows each NBA team's location and the average first year points per game of their draft picks. The map reveals that a few teams, particularly the Charlotte Hornets, the Washington Wizards, the Cleveland Cavaliers, and the New York Knicks, generally pick players that average higher points per game in their first year than the rest of the NBA teams.

<img width="1762" alt="Dashboard 2 (2)" src="https://user-images.githubusercontent.com/66886936/118308547-14c05d80-b4ba-11eb-97b3-dc4e83e952f4.png">



All data was obtained from https://www.basketball-reference.com/.
