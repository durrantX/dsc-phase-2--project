## Final Project Submission

* Student name:  Deon Durrant
* Student pace: self paced 
* Scheduled project review date/time: 
* Instructor name: Mark Bardour
* Blog post URL:



# Project Overview

This project investigates movie data sourced from Box Office Mojo (BOM) and the Internet Movie Database (IMDB) for the years 2010 to 2018. The aim is to offer insights to GAT INC, assisting in their decision-making process regarding potential expansion into the movie production industry.

The analysis encompasses fundamental market metrics and extends to additional metrics beyond the project's scope, providing a comprehensive view of the industry landscape.

# Business Challenge

GAT INC aims to diversify its portfolio as a movie studio by aligning movie audience preferences with different market segments.

The focus lies in identifying movie genres, assessing movie durations, and understanding their roles as predictors of sales. Through market segmentation and the exploration of the relationships between these variables, the study aims to provide valuable insights. Trends and patterns related to movie genres, ratings, movie durations, domestic and foreign sales, and global sales are analyzed.

# Data Understanding 

Understanding the data involves consolidating information from two distinct movie databases covering the years 2010 to 2018. The dataset originates from two separate sources: a SQL database and a CSV file. Prior to merging, thorough preprocessing and cleaning procedures are applied. Additionally, feature engineering techniques are utilized to establish a new market segment. To support initial insights and enhance visualization capabilities, categorical variable is encoded.

# Exploratory Data Analysis
During the exploratory data analysis phase, I will investigate patterns, variations, and other characteristics relevant to the business inquiries. Simultaneously, I will scrutinize the data for irregularities and recognize any constraints it may have.

# Importing the databases
Begin by importing the data and converting it into a pandas dataframe.
Data from IMDB is located in a SQLite database will be imported first.To address the business problem tables movie_basic and movie_ratings will be used. The dataframe for analysis created by joining movie basics and moving ratings tables. Data from the Box Office Mojo is a csv file.
 
## Explore and Examine IMDB data
### Summary of the overall structure of  IMDB dataframe
The data summary confirms this is a pandas dataframe. The dataframe has 146143 entries within 6 columns. Indication of missing data in 3 of the columns. Decisions regarding handling of such is taken during data cleaning.
dtypes: float64(2), int64(1), object(3) memory usage: 6.7+ MB

### Explore and examine BOM  data
### Summary of the overall structure of  bom_movie dataframe
The data summary confirms this is a pandas dataframe. The dataframe has 3387 entries within 5 columns Indication of missing data in 3 of the columns. Decisions regarding handling of such is taken during data cleaning. dtypes: float64(1), int64(1), object(3). 
foreign_gross is an object data type and requres a change to float.
# Data Cleaning 
## Handling Inconsistent Data:
Address typos, variations in capitalization, and naming conventions
## Data Type Conversion
1.Change foreign_gross to float dtype
# Merge Databases  for Analysis
To conduct a thorough analysis, I will merge the IMDB and BOM databases. This integration will enable a comprehensive examination of the data.
# Explore and examine the Merged dataset movie_db
Examine the data structure.
#Overview of the numerical features of the dataset
# Summary of the overall structure of  movie_dataframe
The data summary confirms this is a pandas dataframe. The combined dataframe has 1767 entries within 10 columns. There is no indication of missing data. dtypes: float64(4), int64(2), object(4)
memory usage: 151.9+ KB
# To address the business inquiry and provide actionable insights:
1.  Analysis will entail movie genres as a predictor of  sales, average rating, and runtime.
2. Investigate the relationship between movie length (runtime), average rating, and sales across different market segments
3. Explore how movie length(runtime) correlates with  sales.
4. Assess geographical market segmentation, aligning with the company's areas of interest.
# Drop unnecessary columns
movie_db.drop(['start_year' ,'movieID', 'studio'], axis=1, inplace=True)
# Feature Engineering Global Sales
To address business inquiries, particularly regarding market segmentation,  I established a global sales column by aggregating both foreign and domestic sales.
# Descriptive Statistics
I will generate statistics that summarize the data concisely, and evaluate different ways to visualize data.
 ## Findings Central Tendencies 
## runtime_minutes:
Mean: 107.90 minutes, Median (50th Percentile): 106 minutes, Minimum: 3 minutes, Maximum: 272 minutes
## averagerating:
Mean: 6.46, Median (50th Percentile): 6.5, Minimum: 1.6,  Maximum: 9.2
## domestic_gross:
Mean: $50,081,030, Median (50th Percentile): $21,100,000, Minimum: $400, Maximum: $700,100,000
## foreign_gross:
Mean: $79,595,820, Median (50th Percentile): $21,500,000, Minimum: $600, Maximum: $946,400,000
## global_sales:
Mean: $129,676,800, Median (50th Percentile): $48,400,000, Minimum: $10,800, Maximum: $1,405,400,000
# Analyzing the Data and Building Visualizations
 ## Market Performance through the years:Group by year
Group the movies by year, organizing them based on global sales categories.

# Create visualization
![alt text](image-1.png)

Findings: 
The findings reveal that between 2010 and 2018, there was a decline in the quantity of movies produced.
Simultaneously, both foreign and global sales experienced significant upward trends, whereas domestic sales showed a moderate increase. This suggests an inverse relationship between the variables during the specified period. 

## Analysis of Genres
Genre analysis involves grouping genres to examine their relationships with other variables in the dataset, such as average rating, movie length, and sales. By categorizing genres based on these factors, I obtained gainful insights into their interrelationships and their impact on various aspects of the dataset.
There are 260 different genres in the dataset.To  identify the genre that appears most frequently the mode of the 'genres' column in the movie_db dataset is determined  to be "Drama"

# Top rating genre 

![png](output_57_0.png)
    

#Findings

The analysis revealed the average ratings for each genre group. Notably, genres such as "Adventure", "Action, Sport", and "Drama, Western" emerged as the top-ranking genres with the highest average ratings.

# Market performance categorized by genres 
  
![png](output_61_1.png)
    
# Findings

Findings reveal that the genres emerged as the top global grossing genres are: 

"Action, Adventure, Sci-Fi", 
"Adventure, Animation, Comedy",
"Action, Adventure, Fantasy" 

Analysis comparing domestic and foreign sales by genre indicates that the top domestic sales were: 
"Action, Adventure, Sci-Fi",
"Adventure, Animation, Comedy",
"Action, Adventure, Fantasy".

Conversely, for foreign sales, the leading genres were:
"Adventure, Animation, Comedy",
"Action, Adventure, Sci-Fi",
"Action, Adventure, Fantasy

# The duration of movies categorized by genres.

![png](output_64_0.png)
    

    
![png](output_65_0.png)
    


# Findings

Determining the mean runtime duration for each category of genres, indicated that the top three genres with the lengthiest average runtimes are "Drama, Western," "Adventure, Drama, Sci-Fi," and "Drama, History, Sports."
Conversely, genres exhibiting the shortest average durations include "Action, Sport", "Adventure, Comedy, Horror," and "Documentary, News".

# Examination of Movie Duration (runtime_minutes)
The runtime_minutes variable will be scrutinized to explore the correlation between movie duration and average rating, as well as the relationship between movie duration and sales across various markets.
# Movie length market performanace 

# Create visualization 
![png](output_70_1.png)

# Findings 
Among the various movie lengths observed, movies with a runtime of 59 minutes generated the highest  global gross sales $  n8.5B. Analysis of movie runtimes across different markets reveals that a runtime of 59 minutes emerged as the top performer, leading both the domestic market with 3.5B dollars  and the foreign market with 5B dollars. Following closely in the domestic market were runtimes of 152 and 149 minutes, while in the foreign markets, they were 147 and 143 minutes.

# Visualize the relationship between the movie length  and the  global sales  using scatter plots
    
![png](output_72_0.png)
     
# Top movie length average rating
![png](output_73_0.png)
    
# Findings
Analysis of the average movie length and average showed that movie length of 192 enjoyed the highest rating folllowed by 45 and 47 minutes. 

# Visualize the relationship between the movie runtimes and the movie average rating
    
![png](output_75_0.png)
    
# Findings

# Movie length market performanace 

# Create visualization 

    
![png](output_78_1.png)
    
# Visualize the relationship between the movie average rating and the movie sales
# Plot a scatter plot
    
![png](output_79_0.png)
    
# Correlation Analysis
The correlation coefficient between runtime_minutes’ and ‘averagerating’ is 0.25, between  ‘runtime_minutes’ and ‘global_sales’ is 0.19 and between ‘averagerating’ and ‘global_sales’ is 0.17.
All correlations observed are positive, suggesting that as one variable increases, the other tends to increase as well.Market correlations are significant; however, their correlation with movie runtime and average rating is notably lower compared to other variables. These correlations can guide decision-making in areas of movie production and marketing.

# Visualize the correlation matrix using a heatmap    
![png](output_80_1.png)
    
# Additional analysis

Linear regression statistcal modeling will be used to provide better insights by uncovering patterns and relationships to better inform  business  decisions. 


#  Linear regression with runtime as the predictor of global sales 
    
# Findings 

 The ordinary least square  regression was used to test if  movie length(runtime_minutes) significantly predicted gross sales.
#Coefficients of the model
#The intercept(const ): -8.354e+07 runtime_minutes  1.976e+06
The fitted regression model was: Global Sales=-8.354e+07+1.976e+06*runtime_minutes
Suggesting that for every additional minute in movie length, global sales are expected to increase by 1.976e+06 units($1,976,000).
The overall regression was statistically significant
R-squared: 0.036, 
Adj. R-squared:0.037 
Approximately 3.6 percent of the variability in global sales can be explained by the length of the movie.
 F-statistic is 65.31,  low p-value,  (Prob (F-statistic):  1.18e-15) suggesting that the regression model is statistically 
 significant. 

Overall, the regression model suggests that there is a statistically significant positive relationship between the runtime of movies and their global sales. However, the low R-squared value indicates that the model explains only a small portion of the variance in gross sales, suggesting that other factors not included in the model may also influence  global sales.

 
 Run a Simple Linear Regression with runtime  as the Predictor and domestic sales as dependent variable 

As previous  analysis above indicates, the length of the movie has a realtionship with sales.  Analysis delves further   quantifying the strength of the relationship in the domestic and foreign market. 

# Runtime as the predictor of domestic sales
    

# Findings 

 The ordinary least square  regression was used to test if  movie length(runtime_minutes) significantly predicted doemestic sales.
 
Coefficients:
The intercept (const) is  -18,440,000.
runtime_minutes  6.351e+05 
The fitted regression model was:Domestic gross= -18,440,000+6.351e+05*runtime_minutes

The coefficient for the predictor variable runtime_minutes is approximately 635,100. This means that for each additional minute of runtime, the domestic gross is estimated to increase by approximately $635,100.

R-squared:  0.025
Adjusted R-squared: 0.024.
R-squared is 0.025, indicating that approximately 2.5 percent of the variance in domestic gross is explained by the predictor variable (runtime_minutes).

F-statistic: 44.97 and  low probability (p < 0.001)indicating that the overall model is statistically significant.


Overall the regression model suggests that there is a statistically significant positive relationship between the runtime of movies and their domestic gross. However, the R-squared value indicates that the model explains only a small proportion of the variance in domestic gross, suggesting that other factors not included in the model is  influencing domestic gross.




The ordinary least square  regression was used to test if  movie ratings(averagerating) significantly predicted global sales
 
Coefficients:
The intercept (const) is  --1.037e+08 
averagerating   3.613e+07
The fitted regression model was:Global sales = -1.037e+08 +3.613e+07*averagerating

The coefficient for the predictor variable averagerating is approximately 36 million dollars . This means that for each additional  unit of average rating  the global sales is estimated to increase by approximately 36M dollars.

R-squared:  0.029
Adjusted R-squared: 0.028.
R-squared is 0.029, indicating that approximately 2.9 percent of the variance in global sales is explained by the predictor variable (averagerating).

F-statistic: 52.69 and  low probability (p < 0.001)indicating that the overall model is statistically significant.


Overall the regression model suggests that there is a statistically significant positive relationship between the  averageratings of movies and their global sales. However, the R-squared value indicates that the model explains only a small proportion of the variance in global sales, suggesting that other factors not included in the model is  influencing global sales.


# Runtime as the predictor of average rating
# Findings 
The R-squared value, is 0.061. This suggests that approximately 6.1% of the variance in movie ratings can be explained by the independent variable (runtime_minutes).

Coefficients:
The coefficient for the runtime_minutes variable is 0.0122. 
This indicates that, on average, for each additional minute in the runtime of a movie, the average rating is expected to increase by approximately 0.0122 units.

The F-statistic is 115.1 with a very low p-value (4.64e-26), indicating that the overall regression model is statistically significant.
 The regression results indicate that there is a statistically significant but modest positive relationship between movie runtime and average rating. The model explains only a small proportion of the variance in movie ratings, suggesting that other factors beyond runtime also influence the average rating of movies.


    

# Findings 

# Conclusion 

 1.	Between 2010 and 2018, the quantity of movies produced saw a decline. However, market performance over these years demonstrated significant upward trends in both foreign and global sales, while domestic sales showed a moderate increase. This indicates an inverse relationship between the variables during the specified period.
 2. The genre most frequently observed is "Drama."
 3. Analysis reveals that the top-ranking genres with the highest average ratings are "Adventure", "Action, Sport", and "Drama, Western".
 4. The top global grossing genres are identified as "Action, Adventure, Sci-Fi", "Adventure, Animation, Comedy", and "Action, Adventure, Fantasy".
 5.	A comparison of domestic and foreign sales by genre highlights that the top genres for domestic sales include "Action, Adventure, Sci-Fi", "Adventure, Animation, Comedy", and "Action, Adventure, Fantasy". Conversely, leading genres for foreign sales comprise "Adventure, Animation, Comedy", "Action, Adventure, Sci-Fi", and "Action, Adventure, Fantasy".
 6.	Determining the mean runtime duration for each genre category, it is observed that the top three genres with the lengthiest average runtimes are "Drama, Western", "Adventure, Drama, Sci-Fi", and "Drama, History, Sports". Conversely, genres with the shortest average durations include "Action, Sport", "Adventure, Comedy, Horror", and "Documentary, News".
 7.	Movies with a runtime of 59 minutes generated the highest global gross sales, amounting to 8.5B.
 8. Analysis of movie runtimes across different markets reveals that a runtime of 59 minutes emerged as the top performer, leading both the domestic market with 3.5B dollars and the foreign market with 5B dollars. Following closely in the domestic market were runtimes of 152 and 149 minutes, while in the foreign markets, they were 147 and 143 minutes, respectively.
 9.	Analysis of the average movie length and average rating showed that movies with lengths of 192 minutes enjoyed the highest ratings, followed by those with lengths of 45 and 47 minutes.
 10.	The Ordinary Least Squares (OLS) analysis yielded the following results:
 
 • For movie length and global sales, the R-squared value was 0.036, indicating that approximately 3.6% of the variability in global sales can be explained by movie length.
 
 •	Movie length and domestic sales had an R-squared value of 0.025, suggesting that approximately 2.5% of the variance in domestic gross is explained by movie length.
 
 •	Movie ratings and global sales yielded an R-squared value of 0.029, indicating that approximately 2.9% of the variance in global sales is explained by movie ratings.
 
 •	The R-squared value for movie length and movie ratings was 0.061, suggesting that approximately 6.1% of the variance in movie ratings can be explained by movie length.
 
 •	Genres and global sales had an R-squared value of 0.122, indicating that approximately 12.2% of the variability in global sales can be explained by genres.

All OLS analyses were statistically significant. However, the low R-squared values suggest that the model explains only a small proportion of the variances in the dependent variables, indicating the influence of other factors not included in the model.
