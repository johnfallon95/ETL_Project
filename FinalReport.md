# ETL_Project
Project for Rice Data Analytics

# Data Sources
1. Historical MLB data in SQL form from http://www.seanlahman.com/baseball-archive/statistics.
2. Draft data of #1 overall picks in CSV form from https://www.baseball-reference.com/draft/.

The data I chose for transformation was very comprehensive. The Lahman dataset had basically every useful metric for analysis of player performance over the game's entire history. Because I had all the data I could possibly want, I did not need to combine many different data sources, it was already in a clear dataset.

# Extraction
All of the data was publicly available and somewhat easy to extract. The list of first overall draft picks was available in excel format which was easily converted into CSV form. The Lahman baseball archive data was in a SQL database and ready to run after downloading.

# Transformation
The first transformation I had to do was eliminate all of the data before 1980, the start date for some of the data was in 1880 from the start of baseball statistics recording. This cut out all of the data that was usesless for analysis of first overall draft picks since 1980 and made the future queries in SQL run much faster. Next, I observed that the column 'playerID' was shared amongst data sets, thus could be used as a common ID for analysis. Because player ID was not the players exact name (due to multiple players having the same name), I had to search for each ID for all of the first overall draft picks to be able to analyze their statistics on other tables. I also had to eliminate the first overall picks who did not have statistics in the database. Some of the players never made it to the Major Leagues and thus did not have statistics while others had not yet made it to the MLB by 2016 and were still in the minor leagues or college/ high school yet to be drafted. Having narrowed down the tables to just data for the first overall picks, I could then query for individual statistics on that player easily and effectivly using the 'playerID'

# Loading
To load the data, I exported certain SELECT queries that were applicable into SQL INSERT statements into a folder for easy retrevial. This folder has all relevant baseball statistics of every fist overall draft pick from 1980 to 2016 with major league service. This includes on field performance stats, awards and accolades, and salaries.

# Hypothetical Uses
This could be used to analyze the impact of first overall draft picks in the MLB. First overall picks are expected to be future all stars and are payed a large sum to sign with the team, however this is not always the case. Some players do not live up to the hype while others get injured. There is alot of potential for analysis with this data set. Further examination could look at the impact of fisrt overall draft picks compared to the impact of second overall draft pics. Or, the first overall draft picks performance in the MLB could be compare to the first overall draft picks performance in the NFL. There are alot of possibilities with this data.
