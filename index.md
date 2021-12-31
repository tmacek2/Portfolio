#  Tyler Macek's Portfolio
This is a compliation of some of my personal data analsts projects, including some code, images, and files.  

Included projects:
- Bellabeat Wearable Data Case Analysis
- IBM Employee Attrition



## Project: Bellabeat Case Analysis (Google Data Analyst Certicate Project)
The goal of this project was to analyze data in the public [Kagle dataset](https://www.kaggle.com/arashnic/fitbit) and provide insights to the head of markeing for Bellabeat. 

### Data - Cleaning and Analysis
The data in this project was in different csv files, to begin cleaning and organzing the data was necessary. All of the cleaning was done in excel, combining all 18 files into a single master file.  

The analysis was done in R Studio using tidyverse, ggplot2, and other libraries.  During the analysis, it was discoverd that most of the users did not record any of their sleep data, while the majority used the activity/sleep tracking functionality.  

```R
#sleep
  ggplot(data = daily_activity_clean) + 
    geom_point(mapping = aes(x= ActivityDate, y = Total_minutes_asleep)) +
    facet_wrap(~Id)  + 
    theme(axis.text.x = element_text(angle = 90, vjust = 0.5, hjust=1))
```
<img src="https://www.kaggleusercontent.com/kf/64858339/eyJhbGciOiJkaXIiLCJlbmMiOiJBMTI4Q0JDLUhTMjU2In0..XgmtJ77flJrwgOPzQ2WaZg.EmTfGiN36K1eiQ-6j5WT1TE8FUDpVR4YRdRsNRqCE9zW1NZar0nMf1DhNldjQuU8vlS0SjF_9L88aIyfgSthpqEj6oHgqe52hd0I0AGtqkZyGeHrg3pzk-8fL1HVVFXM5Z_pu8n2fNoYI3sQYhSn4FzPmVtJl09FjqqIWpcDrvMvjlRr1bFUATbwZMn7YClo9FG0zbvcvHoTYcyJ32PdUPSjhJsVcDGgeqM6zHxC9g8ULqpQnbQtQdy0VtCDAsXldb-DVwEmltafl47IUiMbct1FKKQe_aSURDyf3Irtq7rRl2FLkKHuFXReBANOa9E7ZQuRsqfMVlOgvY8Bq-wujvw9RxNut_lzHqKj0gU8MRXx1-dXz8mU_j5iZjW48uLw3LfAPPhNepSo3F2uYUgU-NFLOfhV0l5Rsaoq6wlp79ZLymEoSpaXSYBUGtFSHiSgxUpLyleCVhN_hHmTk_yq8pma_DlxI6y53ymmgNw9MGYmck99u5xQTwRisu7YEmi9i_T6e7VkpYK0DQED7Y6bLncsX2LJk0brJMTighYHMvz2iBCu3OGlDXct-43oRwyvSLH3UDIAtPK2qQPOX2-J63TatJd2dDSQVzZKlwXC6qedL8uOa2Fb8Uy1JYbXygPSGlPTQanQLeueIxD2nTHLkFXGMfiR7SHg-xywKsKUffM.HK_lOa03Xg8dX1lHYJgmTg/__results___files/__results___7_0.png" width="400" height="200">

```R
#sleep and steps
  ggplot(data = daily_activity_clean) + 
    geom_point(mapping = aes(x= ActivityDate, y = Total_minutes_asleep), color= "Blue") +
    geom_point(mapping = aes(x = ActivityDate, y = TotalSteps), color = "red") +
    facet_wrap(~Id)  + 
    theme(axis.text.x = element_text(angle = 90, vjust = 0.5, hjust=1))
 ```

<img src ="https://www.kaggleusercontent.com/kf/64858339/eyJhbGciOiJkaXIiLCJlbmMiOiJBMTI4Q0JDLUhTMjU2In0..XgmtJ77flJrwgOPzQ2WaZg.EmTfGiN36K1eiQ-6j5WT1TE8FUDpVR4YRdRsNRqCE9zW1NZar0nMf1DhNldjQuU8vlS0SjF_9L88aIyfgSthpqEj6oHgqe52hd0I0AGtqkZyGeHrg3pzk-8fL1HVVFXM5Z_pu8n2fNoYI3sQYhSn4FzPmVtJl09FjqqIWpcDrvMvjlRr1bFUATbwZMn7YClo9FG0zbvcvHoTYcyJ32PdUPSjhJsVcDGgeqM6zHxC9g8ULqpQnbQtQdy0VtCDAsXldb-DVwEmltafl47IUiMbct1FKKQe_aSURDyf3Irtq7rRl2FLkKHuFXReBANOa9E7ZQuRsqfMVlOgvY8Bq-wujvw9RxNut_lzHqKj0gU8MRXx1-dXz8mU_j5iZjW48uLw3LfAPPhNepSo3F2uYUgU-NFLOfhV0l5Rsaoq6wlp79ZLymEoSpaXSYBUGtFSHiSgxUpLyleCVhN_hHmTk_yq8pma_DlxI6y53ymmgNw9MGYmck99u5xQTwRisu7YEmi9i_T6e7VkpYK0DQED7Y6bLncsX2LJk0brJMTighYHMvz2iBCu3OGlDXct-43oRwyvSLH3UDIAtPK2qQPOX2-J63TatJd2dDSQVzZKlwXC6qedL8uOa2Fb8Uy1JYbXygPSGlPTQanQLeueIxD2nTHLkFXGMfiR7SHg-xywKsKUffM.HK_lOa03Xg8dX1lHYJgmTg/__results___files/__results___8_0.png" width="400" height ="200">

### Conclusion and Recomendations
A [Presentation](https://github.com/tmacek2/Portfolio/blob/gh-pages/Bellabeat%20Case%20Study.pptx) was created to show to the head of marketing of Bellabeat.  The conclusion on the presentation (presenter notes are present) is that there was not enough data in order to complete the analysis.  My recommendation was to create a survey for Leaf users to determine which features they use the most and which are least utilized.  From there with that data, a better marketing strategy recommendation could be made.  


## Project: Employee Attrition
The goal of this project was to analyze employee data and figure out which factors influenced employee attrition.  This [Dataset](https://www.kaggle.com/pavansubhasht/ibm-hr-analytics-attrition-dataset) comes from Kaggle, supplied by IBM as a ficticious dataset.

### Data - Cleaning and Analysis
The data was contained in a single csv file, which needed minimal cleaning.  The first pass of analysis was done in Excel using pivot tables, checking different factors against attrition.  This provided some ideas on what effected attrition, however this was not enough to draw any concrete resolutions.  Once the data was added into [Tableau](https://public.tableau.com/app/profile/tyler5859/viz/EmployeeAttritionbasedonYearsofServiceandDepartment/EmployeeAttrition), the visualization started to show some clear trends.  

<img src = "https://github.com/tmacek2/Portfolio/blob/gh-pages/Excel%20Pivot%20Table%20-%20Attrition.png?raw=true" width="400">
<img src = "https://github.com/tmacek2/Portfolio/blob/gh-pages/Tableau%20Dashboard%20-%20Attrition.png?raw=true" width = "400">
                                                                                                                             
### Conclusion and recommendations
Based on the tableau dashboard visualization, employees in R&D who are recently promoted are more likely to leave the company.  This occurs after a year with the company, when the employee is promoted.  The reason for this could be promoting the wrong fit, the employee was not fully aware of the role's responsibilities/duties, or burning out. The second most likely department for this is sales.  

With this knowledge, one possible solution would be to rework the promotion process, ensuring employees know the process and make sure they understand the role they are applying for.  Another solution is to work on the interviewing process, making sure to teach managers how to more effectively tell if someone is a good fit for the role.  
