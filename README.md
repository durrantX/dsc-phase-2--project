## Final Project Submission
![image](https://github.com/durrantX/dsc-phase-2--project/assets/148919288/7738b394-07a4-44f9-92dd-ee61c8729bf5)

* Author: Deon Durrant

# Project Overview

This project investigates movie data sourced from Box Office Mojo (BOM) and the Internet Movie Database (IMDB) for the years 2010 to 2018. The aim is to offer insights to GAT INC, assisting in their decision-making process regarding potential expansion into the movie production industry.

The analysis encompasses fundamental market metrics and extends to additional metrics beyond the project's scope, providing a comprehensive view of the industry landscape.

# Business Challenge

GAT INC aims to diversify its portfolio as a movie studio by aligning movie audience preferences with different market segments.

The focus lies in identifying movie genres, assessing movie durations, and understanding their roles as predictors of sales. Through market segmentation and the exploration of the relationships between these variables, the study aims to provide valuable insights. Trends and patterns related to movie genres, ratings, movie durations, domestic and foreign sales, and global sales are analyzed.

# Data Understanding 

Understanding the data involves consolidating information from two distinct movie databases covering the years 2010 to 2018. The dataset originates from two separate sources: a SQL database and a CSV file. Prior to merging, thorough preprocessing and cleaning procedures are applied. Additionally, feature engineering techniques are utilized to establish a new market segment. To support initial insights and enhance visualization capabilities, categorical variable is encoded.

# Exploratory Data Analysis
Investigate patterns, variations, and relevant characteristics during exploratory data analysis. Scrutinize data for irregularities and constraints.
- Import databases:
    Create dataframe from SQLite database IMDB by joining movie basics and movie ratings tables.
  
    Import Box Office Mojo data from a CSV file.
  
-    Summary of IMDB dataframe structure:
-    
     146143 entries, 6 columns.
   
     Missing data in 3 columns
  
    dtypes: float64(2), int64(1), object(3)
  
-    Summary of bom_movie dataframe structure:
  
    3387 entries, 5 columns.
    
    Missing data in 3 columns.
   
   dtypes: float64(1), int64(1), object(3).
   
   Convert foreign_gross to float dtype.
   
- Data Cleaning:
   Address typos, capitalization variations, and naming conventions.
  
   Convert foreign_gross to float.
  
- Merge Databases for Analysis: Merge IMDB and BOM databases.
  
   Explore merged dataset movie_db:Examine data structure and numerical features.
   
    1767 entries, 10 columns.
    
    No missing data.
    
   dtypes: float64(4), int64(2), object(4).
   
   Drop unnecessary columns
## Feature Engineering Global Sales
To address business inquiries, particularly regarding market segmentation,  I established a global sales column by aggregating both foreign and domestic sales.

## To address the business inquiry and provide actionable insights:
1.  Analysis will entail movie genres as a predictor of  sales, average rating, and runtime.
2. Investigate the relationship between movie length (runtime), average rating, and sales across different market segments
3. Explore how movie length(runtime) correlates with  sales.
4. Assess geographical market segmentation, aligning with the company's areas of interest.


# Descriptive Statistics
I will generate statistics that summarize the data concisely, and evaluate different ways to visualize data.
 ## Findings: Central Tendencies 
 ### runtime_minutes-
 Mean: 107.90 minutes
 Median (50th Percentile): 106 minutes
 Minimum: 3 minutes
 Maximum: 272 minutes
### averagerating-
Mean: 6.46, 
Median (50th Percentile): 6.5, 
Minimum: 1.6,  
Maximum: 9.2
### domestic_gross-
Mean: $50,081,030, 
Median (50th Percentile): $21,100,000, 
Minimum: $400, 
Maximum: $700,100,000
### foreign_gross-
Mean: $79,595,820, 
Median (50th Percentile): $21,500,000, 
Minimum: $600, Maximum: $946,400,000
### global_sales-
Mean: $129,676,800, 
Median (50th Percentile): $48,400,000, 
Minimum: $10,800, Maximum: $1,405,400,000
# Analyzing the Data and Building Visualizations
 ## Market performance through the years: Groupby year
Group the movies by year, organizing them based on global sales categories.
![image](https://github.com/durrantX/dsc-phase-2--project/assets/148919288/29e7490c-6d1e-4e72-9b17-674d3981a623)
### Findings: 
The findings reveal that between 2010 and 2018, there was a decline in the quantity of movies produced.
Simultaneously, both foreign and global sales experienced significant upward trends, whereas domestic sales showed a moderate increase. This suggests an inverse relationship between the variables during the specified period. 

## Analysis of Genres
Genre analysis involves grouping genres to examine their relationships with other variables in the dataset, such as average rating, movie length, and sales. By categorizing genres based on these factors, I obtained gainful insights into their interrelationships and their impact on various aspects of the dataset.
There are 260 different genres in the dataset.To  identify the genre that appears most frequently the mode of the 'genres' column in the movie_db dataset is determined  to be "Drama"

### Top Rating Genres 

![image](https://github.com/durrantX/dsc-phase-2--project/assets/148919288/eaf6a16a-5983-4e3a-bfb1-b00a2f9db9bd)
    
 ### Findings
The analysis revealed the average ratings for each genre group. Notably, genres such as "Adventure", "Action, Sport", and "Drama, Western" emerged as the top-ranking genres with the highest average ratings.

### Market performance categorized by genres 
  
![image](https://github.com/durrantX/dsc-phase-2--project/assets/148919288/46f1241b-4877-4d73-b790-ba786401ce1c)

### Findings
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

### The duration of movies categorized by genres.

![image](https://github.com/durrantX/dsc-phase-2--project/assets/148919288/cf016ca2-47ed-4b53-bf6e-9949db440766)
### Findings
Determining the mean runtime duration for each category of genres, indicated that the top three genres with the lengthiest average runtimes are "Drama, Western," "Adventure, Drama, Sci-Fi," and "Drama, History, Sports."
Conversely, genres exhibiting the shortest average durations include "Action, Sport", "Adventure, Comedy, Horror," and "Documentary, News".

## Examination of Movie Duration (runtime_minutes)
The runtime_minutes variable will be scrutinized to explore the correlation between movie duration and average rating, as well as the relationship between movie duration and sales across various markets.
### Movie length market performanace 

![image](https://github.com/durrantX/dsc-phase-2--project/assets/148919288/be12682f-baac-4221-b6b1-27c45e8d69c3)

### Findings 
Among the various movie lengths observed, movies with a runtime of 59 minutes generated the highest  global gross sales $8.5B dollars. Analysis of movie runtimes across different markets reveals that a runtime of 59 minutes emerged as the top performer, leading both the domestic market with 3.5B dollars  and the foreign market with 5B dollars. Following closely in the domestic market were runtimes of 152 and 149 minutes, while in the foreign markets, they were 147 and 143 minutes.

### Visualize the relationship between the movie length and the global sales using scatter plots
    
![image](https://github.com/durrantX/dsc-phase-2--project/assets/148919288/7ea4276a-4752-4b5b-b3a6-e0577909790f)
     
### Top movie runtimes and the movie average rating
![image](https://github.com/durrantX/dsc-phase-2--project/assets/148919288/abcdca37-28c7-4873-a33f-1a45d76bdf10)
    
### Findings
Analysis of the average movie length and average ratings showed that movie length of 192 enjoyed the highest rating folllowed by 45 and 47 minutes. 
   
### Visualize the relationship between the movie average rating and the movie sales

![image](https://github.com/durrantX/dsc-phase-2--project/assets/148919288/084f80bc-f654-4daa-a8db-9293836f1127)
    
# Correlation Analysis
    
![image](https://github.com/durrantX/dsc-phase-2--project/assets/148919288/59e8dd96-9524-435b-97ce-8ac7f44d0af7)
### Findings
 The correlation coefficient between runtime_minutes’ and ‘averagerating’ is 0.25, between  ‘runtime_minutes’ and ‘global_sales’ is 0.19 and between ‘averagerating’ and ‘global_sales’ is 0.17.
All correlations observed are positive, suggesting that as one variable increases, the other tends to increase as well. These correlations can guide decision-making in areas of movie production and marketing.  
# Additional analysis
Linear regression statistcal modeling will be used to provide better insights by uncovering patterns and relationships to better inform  business  decisions. 
### Linear regression with runtime as the predictor of global sales 
### Findings 
 The ordinary least square  regression was used to test if  movie length(runtime_minutes) significantly predicted gross sales.
Coefficients of the model
The intercept(const ): -8.354e+07 runtime_minutes  1.976e+06
The fitted regression model was: Global Sales=-8.354e+07+1.976e+06*runtime_minutes
Suggesting that for every additional minute in movie length, global sales are expected to increase by 1.976e+06 units($1,976,000).

R-squared: 0.036, 
Adj. R-squared:0.037 
Approximately 3.6 percent of the variability in global sales can be explained by the length of the movie.
 F-statistic is 65.31,  low p-value,  (Prob (F-statistic):  1.18e-15) suggesting that the regression model is statistically significant. 

Overall, the regression model suggests that there is a statistically significant positive relationship between the runtime of movies and their global sales.  The low R-squared value indicates that the model explains only a small portion of the variance in gross sales, suggesting that other factors not included in the model may also influence  global sales.

 ### Run a Simple Linear Regression with runtime  as the Predictor and domestic sales as dependent variable 

As previous  analysis above indicates, the length of the movie has a relationship with sales.  Analysis delves further quantifying the strength of the relationship in the domestic and foreign market.     
### Findings 
 The OLS  regression was used to test if  movie length(runtime_minutes) significantly predicted doemestic sales.
Coefficients:
The intercept (const) is  -18,440,000.
runtime_minutes  6.351e+05 
The fitted regression model was:Domestic gross= -18,440,000+6.351e+05*runtime_minutes
The coefficient for the predictor variable runtime_minutes is approximately 635,100. This means that for each additional minute of runtime, the domestic gross is estimated to increase by approximately $635,100.

R-squared:  0.025
Adjusted R-squared: 0.024.
R-squared is 0.025, indicating that approximately 2.5 percent of the variance in domestic gross is explained by runtime_minutes.

F-statistic: 44.97 and  low probability (p < 0.001)indicating that the overall model is statistically significant.
The model suggests that there is a statistically significant positive relationship between the runtime of movies and their domestic gross. The R-squared value indicates that the model explains only a small proportion of the variance in domestic gross, other factors not included in the model maybe  influencing domestic gross.
 
# OLS with movie ratings(averagerating) as the predictor and global sales as dependent variable
OLS regression was used to test if  movie ratings(averagerating) significantly predicted global sales

Coefficients:
The intercept (const) is  --1.037e+08 
averagerating   3.613e+07
The fitted regression model was:Global sales = -1.037e+08 +3.613e+07*averagerating.
The coefficient for averagerating is approximately 36 million dollars. This means that for each additional  unit of average rating  the global sales is estimated to increase by approximately 36M dollars.

R-squared:  0.029
Adjusted R-squared: 0.028.
R-squared is 0.029, indicating that approximately 2.9 percent of the variance in global sales is explained by  averagerating.

F-statistic: 52.69 and  low probability (p < 0.001)indicating that the overall model is statistically significant.

 The regression model suggests that there is a statistically significant positive relationship between the  averageratings of movies and their global sales. The R-squared value indicates that the model explains only a small proportion of the variance in global sales, suggesting that other factors not included in the model maybe influencing global sales.
# Runtime as the predictor of average rating
### Findings 
The R-squared value, is 0.061. This suggests that approximately 6.1% of the variance in movie ratings can be explained by the independent variable (runtime_minutes).

Coefficients:
The coefficient for the runtime_minutes variable is 0.0122. 
This indicates that, on average, for each additional minute in the runtime of a movie, the average rating is expected to increase by approximately 0.0122 units.

The F-statistic is 115.1 with a very low p-value (4.64e-26), indicating that the overall regression model is statistically significant.
 The regression results indicate that there is a statistically significant relationship between movie runtime and average rating. The model explains only a small proportion of the variance in movie ratings, suggesting that other factors beyond runtime also influence the average rating of movies.

# OLS genre and global sales 
Convert categorical genres to numeric for regression analysis

![image](https://github.com/durrantX/dsc-phase-2--project/assets/148919288/8dca702d-bf16-4821-a48d-d05d7d447a02)

## Findings
This OLS regression analysis provides insights into the relationship between global sales, and the independent  numeric_genres. 
The R-squared value of 0.122 indicates that approximately 12.2% of the variation in global sales can be explained by the variation in numeric_genres.

The F-statistic of 245.5 with a very low p-value (6.61e-52) suggests that the regression model as a whole is statistically significant. 

 The regression model suggests that there is a statistically significant relationship between the number of genres and global sales.The model explains only a small portion of the variation in global sales, and there may be other factors not included in the analysis that influence movie sales
# Conclusion 

 Based on these findings, here are three actionable recommendations
1. Genre-based Content Strategy:
- The top-ranking genres with the highest average ratings, such as "Adventure", "Action, Sport", and "Drama, Western", prioritize content creation and marketing efforts towards these genres.
- Allocate resources towards developing compelling narratives and high-quality productions within these genres to attract and retain audiences.
 
2.  Market-specific Distribution Approach: The Global Strategy
- Tailor distribution strategies based on market preferences 
- Foreign markets  focus on promoting genres like "Adventure, Animation, Comedy" and "Action, Adventure, Sci-Fi" 
- Domestic markets emphasize genres like "Action, Adventure, Fantasy

3. Optimize Movie Runtimes for Global Appeal:
- Optimize movie lengths to align with audience preferences across different markets. 
- Shorter runtimes like 59 minutes show strong performance globally.
- Longer durations like 152 and 149 minutes resonate better domestically. 
- Tailor content duration based on regional preferences to maximize audience engagement and revenue generation.

See the full analysis in the Jupyter Notebook or review this presentation.

## Data structure
──.gitignore 

── Presentation.pdf

── README.md

── bom.movie_gross.csv

── movie_db_analysis.ipynb

── output.csv
