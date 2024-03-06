# PWC Power BI Virtual work - Call Center Trends

![main](https://github.com/Anabil12/PWC-Power-BI-Virtual-Work-Experience/assets/118571332/51a9bbc1-1185-487d-b418-4f932c2ef0d5)
 
## Table of Contents :

- Problem Statement
- Data Preparation
- Data Modelling
- Data Analysis (DAX)
- Data Visualization Dashboard
- Insights

## Problem Statement :
In this project Create a dashboard in Power BI for the call center manager that reflects all relevant Key Performance Indicators (KPIs) and metrics in the dataset.

- Overall customer satisfaction
- Overall calls answered/abandoned
- Calls by time
- Average speed of answer
- Agent’s performance quadrant -> average handle time (talk duration) vs calls answered

## Datasource :

The dataset used for this task was presented by [Pwc](https://www.pwc.ch/en/careers-with-pwc/students/virtual-case-experience.html) and call centre trends dataset:

Dataset: [Call Centre Trends](https://github.com/Anabil12/PWC-Power-BI-Virtual-Work-Experience/blob/main/01%20Call-Center-Dataset.xlsx)

## Data Preparation:

Completed the Data transformation in Power Query and the dataset was loaded into Microsoft Power BI Desktop for modeling.

Call Center Trends dataset is give table named:

- " Call Center trends dataset" which has `10 columns and 5000 rows` of observation

Data Cleaning for the dataset was done in the power query editor as follows:

- Removed Unnecessary columns
- Removed Unnecessary rows
- Each of the columns in the table were validated to have the correct data type

## Data Modeling:

And then dataset was cleaned and transformed, it was ready to the data modeled.

- The `measure table` and `call centre trends` tables as show below:

-![Screenshot (37)](https://user-images.githubusercontent.com/118357991/227766088-7fe8f2b3-b4b3-4cfd-a925-0895874ea956.png)

## Data Analysis (DAX):

Measures used in  all visualization are:

- Average of seed of answered = `AVERAGE('call centre trends'[Speed of answer in seconds])`

- Average of satisfaction = `AVERAGE('call centre trends'[Satisfaction rating])`

- Count satisfaction rating = `COUNT('call centre trends'[Satisfaction rating])`

- Overall Customer Satisfaction = `DIVIDE([Possitive satisfaction rating],[Count satisfaction rating],0)`

- Positive satisfaction rating = `CALCULATE(COUNT('call centre trends'[Satisfaction rating]),FILTER('call centre trends','call centre trends'[Satisfaction rating] IN {4,5}))`

- resolved calls = `COUNTX(FILTER('call centre trends','call centre trends'[Resolved] = "Yes"), 'call centre trends'[Resolved])`

- Unresolved calls = `COUNTX(FILTER('call centre trends','call centre trends'[Resolved] = "No"), 'call centre trends'[Resolved])`

- total calls =  `CALCULATE('Table'[total calls answered] + 'Table'[total calls unanswred])`

- total calls answered = `COUNTX(FILTER('call centre trends','call centre trends'[Answered (Y/N)] = "Yes"),'call centre trends'[Answered (Y/N)])`

- total calls unanswered =`COUNTX(FILTER('call centre trends','call centre trends'[Answered (Y/N)] = "No"), 'call centre trends'[Answered (Y/N)])`

## Data Visualization (Dashboard) :

Data visualization for the data analysis (DAX) was done in Microsoft Power BI Desktop:

Dashboard: [View Dashboard]()

Shows visualizations from Call Center Trends :

| Call Center Trends (Overview) |
| ----------- |
| ![overview](https://github.com/Anabil12/PWC-Power-BI-Virtual-Work-Experience/assets/118571332/5025926e-14ef-4b90-afb1-b461d8aa4f83) |


| Call Center Trends (Agent's Performance) |
| ----------- |
| ![performance](https://github.com/Anabil12/PWC-Power-BI-Virtual-Work-Experience/assets/118571332/24cdc504-2be6-44ce-8516-3b9d75ef17ee) |

| Call Center Trends (Insights) |
| ----------- |
| ![insights](https://github.com/Anabil12/PWC-Power-BI-Virtual-Work-Experience/assets/118571332/293b8b32-95a1-46f5-9d0e-3b0f7274f9b4) |




