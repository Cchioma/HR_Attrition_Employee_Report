# HR_Attrition_Employee_Report
![](attrtion_image.jpg)
## Background
Employee attrition, often referred to as staff attrition or employee turnover, is the rate at which employees leave an organization over a specific period of time. A critical human resources (HR) metric quantifies the number or percentage of employees who voluntarily or involuntarily depart from their jobs and are replaced by new employees. 
There are two main types of employee attrition:
1.  Voluntary Attrition: This occurs when employees choose to leave their jobs voluntarily. Reasons for voluntary attrition can vary widely and may include career advancement opportunities, dissatisfaction with the work environment, seeking better compensation or benefits, personal reasons, or pursuing other career options.
2.  Involuntary Attrition: Involuntary attrition happens when the employer separates employees from their jobs. This can include layoffs, termination due to performance issues or policy violations, or other circumstances where the employer initiates the departure.
This project seeks to assess the rate of attrition in an organization, discover some major factors contributing to attrition, and suggest ways to mitigate them

## About the Data
The dataset is a CSV file that contains one table, consisting of 1470 rows and 32 columns of the Employees hiring records and performance. The dataset can be found here.

## Business Problem
The following are some business questions the project seeks to assess:
1.  What is the overall attrition rate in the company?
2.	What is the average age of an Employee?
3.	How does attrition vary by age group?
4.	What is the overall attrition rate in the company?
5.	Is there a significant difference in attrition rates between different business travel categories (e.g., Travel Frequently, Rarely, Non-Travel)?
6.	Does gender play a role in attrition rates?
7.	Are there any noticeable patterns in attrition among employees of different education fields?
8.	Does marital status affect attrition rates?
9.	How does attrition vary across departments and job roles?
10.	Is there a correlation between years of service at the company and attrition?
11.	How does job satisfaction affect attrition?
12.	Are employees with a better work-life balance less likely to leave the company?
13.	Is there a relationship between monthly income and attrition

## Skills/ Concepts applied
The following skills and concepts wer applied throughout the course of this project:
1.	Defining KPIs
2.	Cleaning/Validation in Power Query
3.	Power BI DAX Concepts: Calculated Measures
4.	Data Visualization in Power BI
5.	Power BI Dashboard building
6.	Filters and Slicers
7.	Insights & Actions

## Data Transformation / Cleaning
The dataset was imported into Power BI’s Power Query for data validation and cleaning.  ‘Column quality’ and ‘Column distribution’ checkboxes were selected to get summary information about each column for effective cleaning/Preprocessing. The processes are outlined below:
1.	Changed EmployeeNumber column to EmployeeId
2.	Deleted redundant columns ( 'EmployeeCount', 'StandardHours', 'Over18').
3.	Created an 'AgeGroup' column using the following DAX code:
  AgeGroup = 
  SWITCH(
    		TRUE(),
    		'HR-Employee-Attrition'[Age] >= 18 && 'HR-Employee-Attrition'[Age] <= 24, "18-24",
   		'HR-Employee-Attrition'[Age] >= 25 && 'HR-Employee-Attrition'[Age] <= 34, "25-34",
    		'HR-Employee-Attrition'[Age] >= 35 && 'HR-Employee-Attrition'[Age] <= 44, "35-44",
   		 'HR-Employee-Attrition'[Age] >= 45 && 'HR-Employee-Attrition'[Age] <= 54, "45-54",
   		 'HR-Employee-Attrition'[Age] >= 55, "55+",
)

)
4.	Created the following DAX Measures to help in defining KPI’s:
    a.	Attrition Rate = ([Attrition] /'_Measures'[Total Employees]) 
    b.	Attrition = CALCULATE('_Measures'[Total Employees], 'HR-Employee-            Attrition'[Attrition] = "Yes")
    c.	Active Employees = CALCULATE('_Measures'[Total Employees], 'HR-              Employee-Attrition'[Attrition] = "No")
    d.	Total Employees = COUNT('HR-Employee-Attrition'[EmployeeId])

## Data Visualization

## Insights
1.	Employees in the age group 25-34 had the highest attrition at 112, which was significantly higher (918.18%) than employees aged 55 and above (11 attritions)
2.	Singles had the highest Attrition at 120, followed by the Married at 84 and divorced at 33.  
3.	Male employees had a higher attrition rate (150) compared to female employees (87).
4.	The job role "Laboratory Technician" had the highest attrition at 62, which was 416.67% higher than the job role "Human Resources" with the lowest attrition (12).
5.	Job satisfaction ranged from 46 to 73 across four levels.
6.	In the "Life Sciences" education field, attrition was the highest at 89, significantly surpassing "Human Resources" with the lowest attrition at 7.
7.	Employees with 1 year at the company had the highest attrition rate at 98, significantly higher than those with 8 years (the lowest at 6).
8.	Employees who have worked at 1 company had the highest attrition rate at 59, followed by those with 2 and 5 companies worked.

## Recommendations
1.	Consider conducting surveys or assessments to understand the reasons for higher attrition in the 25-34 age group and implement targeted retention strategies
2.	Investigate the factors contributing to higher attrition among male employees and tailor retention efforts accordingly.
3.	Explore the work environment and job satisfaction specific to Laboratory Technicians to address attrition concerns.
4.	Focus on understanding the drivers of job satisfaction and consider initiatives to improve overall job satisfaction levels.
5.	Investigate whether there are specific challenges or opportunities related to the Life Sciences field and tailor retention strategies accordingly.
6.	Explore why employees with just one year of tenure are leaving and consider onboarding and engagement strategies.
7.	Investigate whether there are patterns related to employees who have worked at multiple companies and develop strategies to retain them.
8.	Conduct surveys, exit interviews, and deeper analyses to uncover the root causes of attrition.











