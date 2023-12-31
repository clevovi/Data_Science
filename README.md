# Project : Data Science writing a blog

## Business Understanding

### Project Motivation : A Deeper Dive into the StackOverflow dataset
After reviewing the dataset on the Udacity course there were additional questions to consider when looking at the data

### Questions addressed 
1. Does the average salary change based on gender?
2. Which countries have the highest Job satisfaction?
3. Does company size corralate to job satisfsction? 

## Data Understanding

### Libarires Used
1. pandas
2. sklearn
3. collections

### File Description
data_science_project.ipynb is the jupyter notebook where all the analysis for all 3 questions can be found

## Prepare Data
1. NAN were removed in some analyses
2. categorical data were converted to numerical data

## Modeling
1. linear regression
2. logistic regression

## Analysis
### Question 1 - Q1
Setup - the Gender and Salary column needed to be analyzed. The NAN were filled in with a place holder as the information was important to retain. Individuals who didnt answer the gender question are still a datapoints so we retained these individuals as a seperate group. There were many smaller categories included in the gender column. Instead of removing them, we combined these groups, with low counts, and created a group called "other". However, individuals with unreported salaries were removed.
Results 
1.There were almost 10X the number of "males" then "females" in the analysis
2.The group made up of indiciduals who did not reveal their gender was the second highests gender category, half the number of "males" and 6X the number of "females". Clearly many people did not want to reveal their gender.
3.On average, the saleries are comprable. Males average salery at ~21k, Female average salery ~19k, and Other average category ~20k. Intereestingly, individuals who did not report their gender had much lower average salergy at ~4k
4. Both male and Females had a left skewed distribution. staking their distributions with differnt colors demonstrates how many more males individuals there are despoite a similar distribution curve. 

#### Question 2 - Q2
Setup - The Country and JobSarifaction columns needed to be analyzed. Here, the indivuduals withoout jobStatisfaction scores were droped as it was not needed for the analysis. Since this question is answered using descriptive statistics we used a pivot table to summerize the data. 
Results
1.  The mean job satisfaction across all countries is 7, with the standard deviasion of 2.1 and 75% at 8 and 25% at 6 
2. The Virgin Islands and Iraq had the highest job satisfaction scores
3. North Korea and Fiji has the lowest job satisfaction scores.
4. the top 5 countries are in differnce continents.
5. climate or geographical location doesnt seem to influence job satisfaction (island countries are highest and lowest)

#### Question 3 - Q3
Setup - The CompanySize and JbSatisfaction columns needed to be analyzed. We dont need the data with NAN so they were droped. Since we would like to find the corrolation between Salary and company size we needed to make sure the companysize was converted to numerical values so we used get_dummies pandas function to get categorical data into indicator dummies in 0/1 form. We then used the sklearn linearregression and logisticregression models to fit the data and find the coefficient values. we calculated the r2 to see if there is a correlation. 
Results
1. the linear regression show almost no correlation with r2 vallue very close to zero
2. the logistic regression showed a very low correlation with an r2 value of .23
3. Company size is likely not correlated to job satisfaction however other models can be used to test this. 

## Evaluation
Average salary did not vary across large gender groups.
Jobsatisfaction varied accross country fo work but the mean across countries was reletivly high
Company size does not seem to correlate with job satisfaction

## Acknowledgements
### Data used
StackOverflow 2017 dataset - information on this dataset can be found at this website https://www.kaggle.com/datasets/stackoverflow/so-survey-2017
