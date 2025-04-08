 # 📊 CSV Documentation


 ## 📂 Data Sources
- **Source:** hr_raw_data.csv
- **Format:** CSV 
- **Size:** 1678 rows × 41 columns
- **Key Variables:**

    - `Age` (object): Employee's age.
    - `Attrition` (object): Indicates whether the employee left the company (Yes/No).
    - `BusinessTravel` (object): Frequency of business trips (e.g., travel_rarely).
    - `DailyRate` (float64): Estimated daily rate for clients, calculated based on the salary.
    - `Department` (object): The department in which the employee works.
    - `DistanceFromHome` (int64): Distance in miles or kilometers from home to work.
    - `Education` (int64): Employee's education level on a numerical scale.
    - `EducationField` (object): Employee's academic field of study.
    - `employeecount` (int64): Constant value of "1", indicating a single employee per record.
    - `employeenumber` (int64): Employee identification number.
    - `EnvironmentSatisfaction` (int64): Level of satisfaction with the work environment.
    - `Gender` (int64): Employee's gender.
    - `HourlyRate` (float64): Calculated hourly rate.
    - `JobInvolvement` (int64): Employee's level of commitment to the job.
    - `JobLevel` (int64): Job hierarchy level of the employee's position.
    - `JobRole` (object): Specific role or function of the employee.
    - `JobSatisfaction` (int64): Overall satisfaction in the role.
    - `MaritalStatus` (object): Marital status (e.g., Single, Married).
    - `MonthlyIncome` (object): Estimated monthly income based on the annual salary.
    - `MonthlyRate` (object): Estimated monthly rate based on the daily rate.
    - `NUMCOMPANIESWORKED` (int64): Number of previous companies the employee has worked for.
    - `OverTime` (object): Indicates whether the employee works overtime (Yes/No).
    - `PercentSalaryHike` (int64): Percentage increase in salary.
    - `PerformanceRating` (object): Performance evaluation on a numerical scale.
    - `RelationshipSatisfaction` (int64): Satisfaction with interpersonal relationships at work.
    - `StandardHours` (object): Classification of work hours (Full Time/Part Time).
    - `StockOptionLevel` (int64): Level of stock options assigned.
    - `TOTALWORKINGYEARS` (object): Total years of work experience.
    - `TrainingTimesLastYear` (int64): Number of training sessions in the last year.
    - `WORKLIFEBALANCE` (object): Level of work-life balance.
    - `YearsAtCompany` (int64): Years at the current company.
    - `YearsInCurrentRole` (object): Years in the current role.
    - `YearsSinceLastPromotion` (int64): Years since the last promotion.
    - `YEARSWITHCURRMANAGER` (int64): Years working with the current manager.
    - `DateBirth` (int64): Employee's year of birth.
    - `Salary` (object): Calculated annual salary for the employee.
    - `RoleDepartament` (object): Combination of role and department.
    - `NUMBERCHILDREN` (float64): Number of children the employee has (if available).
    - `RemoteWork` (object): Indicates whether the employee works remotely (Yes/No).

------------------------------
- **Source:** hr_clean_data.csv
- **Format:** CSV 
- **Size:** 1614 rows × 35 columns
- **Key Variables:**
    - `Attrition` (object): Indicates whether the employee left the company (Yes/No).
    - `BusinessTravel` (object): Frequency of business trips (e.g., travel_rarely).
    - `DailyRate` (float64): Estimated daily rate for clients, calculated based on the salary.
    - `Department` (object): The department in which the employee works.
    - `DistanceFromHome` (int64): Distance in miles or kilometers from home to work.
    - `Education` (object): Employee's education level on a numerical scale.
    - `EducationField` (object): Employee's academic field of study.
    - `EmployeeNumber` (int64): Employee identification number.
    - `EnvironmentSatisfaction` (int64): Level of satisfaction with the work environment.
    - `Gender` (object): Employee's gender.
    - `HourlyRate` (float64): Calculated hourly rate.
    - `JobInvolvement` (int64): Employee's level of commitment to the job.
    - `JobLevel` (int64): Job hierarchy level of the employee's position.
    - `JobRole` (object): Specific role or function of the employee.
    - `JobSatisfaction` (int64): Overall satisfaction in the role.
    - `MaritalStatus` (object): Marital status (e.g., Single, Married).
    - `MonthlyRate` (float64): Estimated monthly rate based on the daily rate.
    - `NUMCOMPANIESWORKED` (int64): Number of previous companies the employee has worked for.
    - `OverTime` (object): Indicates whether the employee works overtime (Yes/No).
    - `PercentSalaryHike` (int64): Percentage increase in salary.
    - `PerformanceRating` (float64): Performance evaluation on a numerical scale.
    - `RelationshipSatisfaction` (int64): Satisfaction with interpersonal relationships at work.
    - `StandardHours` (object): Classification of work hours (Full Time/Part Time).
    - `StockOptionLevel` (int64): Level of stock options assigned.
    - `TOTALWORKINGYEARS` (float64): Total years of work experience.
    - `TrainingTimesLastYear` (int64): Number of training sessions in the last year.
    - `WORKLIFEBALANCE` (float64): Level of work-life balance.
    - `YearsAtCompany` (int64): Years at the current company.
    - `YearsInCurrentRole` (object): Years in the current role.
    - `YearsSinceLastPromotion` (int64): Years since the last promotion.
    - `YEARSWITHCURRMANAGER` (int64): Years working with the current manager.
    - `DateBirth` (int64): Employee's year of birth.
    - `RemoteWork` (object): Indicates whether the employee works remotely (Yes/No).
    - `Salary` (float64): Calculated annual salary for the employee.
    - `SalaryLevel` (category): Employee's salary level category.


##  **👨‍💻Methodology:**

1. **Data Cleaning**: 
    - **Nulls**
        - There are many columns with a condierable amount of nulls. 
            - The column `businesstravel` all the nulls of this column can be changed by `no-travel`
            - The column `department` has many nulls that can be easily filled by comparing the data with `jobrole`. The nulls that can't be guessed will be marked as "Unknown"
            - The column `educationfield` has many nulls, but at the moment these data doesn't show any relevance. It will be left as it is.
            - The column `hourlyrate`has many nulls, but can be related to `monthlyrate`
            - The column `maritalstatus`has many nulls, but it isn't critical data. It will be left as it is. 
            - The column `monthlyincome`can complement the `salary` column.
            - The column `over18`doesn't bring relevant data, it will be dropped.
            - The column `overtime` can be filled with No in the Nan gaps.
            - The column `performancerating` has many nulls, but it isn't critical data. It will be left as it is.
            - The column `standardhours` has many nulls, but it isn't critical data. It will be left as it is.
            - The column `totalworkingyears` can be compared to `yearsatcompany`
            - The column `worklifebalance` has many nulls, but it isn't critical data. It will be left as it is.
            - The column `yearsincurrentrole` can be compared to `yearssincelastpromotion`
            - The column `sameasmonthlyincome` will be dropped.            - 
            - The column `numberofchildren` has 100% nulls, this column will be dropped. 
            - The column `roledeparment` has merged/repeated data. This column will be processed and dropped
            - 

    - **Duplicates**
        - There are 64 rows duplicated. After analyzing it, the duplicated data will be dropped. 

    - **Change of dtype**: 
        - The columns `monthlyincome`, `monthlyrate`, `salary`, `worklifebalance`, `totalworkingyears` and `performancerating` have to be changed to numeric dtype
    
    - **Homogenize data**:
        - The column `gender` needs to change its values for "Male" and "Female"
        - The column `maritalstatus`needs to change its values to match "Married", "Divorced"
        - The column `businesstravel` needs to change its Nan for "non-travel"
        - The column `overtime` needs to change its Nan for "non-travel"
        - The columns `dailyrate`,  `hourlyrate` need to round to 2 decimals
        - The column `education`needs to change it values per 1: "High School or Below", 2: "Professional Certification", 3: "Bachelor", 4: "Masters", 5: "Doctor"
        - The column `distancefromhome` needs to convert all its values to absolute values to avoid potential negative distances.
        - The column `remotework` needs to standardize its values to "Yes" and "No" using a mapping dictionary to ensure consistency across different formats

2. **Exploration**: 

    - Personal profile of the employees: 

        - More presence of male workers (60%) than female, almost half of them around middle age (30-40y o), around 27% are married.
    
    - Educational profile:
        - The majority of the employees (around 40%) hold a Bachelor degree, with men consistently outnumbering women across all education levels shown.
        - Life Sciences and Medical exhibit the highest percentages of education fields, particularly for Bachelor's and Master's degrees.

    - Professional profile of the employee: 

        - Male pressence is higher in all departments
        - Doctors have the highest average salary
        - Research scientist, Sales executive and Laboratory tech. are the roles with the lowest pay.
        - Even though there’s parity in almost al job roles, in some high-profile jobs male professionals aearn more than their female counterparts

    - Departed vs currnt employee professional profiles

        - The company has a 16% of attrition
        - The gender difference seems consistent between those staying and those leaving.
        - The jobs with more rotation are Laboratory Technician, Sales representative and Research Scientist. Those with fewer are Research Director and Manager
        - The high profile jobs are the ones with more retention, and Sales representative, the job with the worst pay, the job with more rotation and less expectaton of staying.

    - Satisfaction parameters 
        - Average satisfaction is not very high (2/4)
        - When crossing different common parameters in job satisfaction such as salary, overtime, commuting, and job position we can conclude that there is no clear indicator that these parameters affect satisfaction.
        - The satisfaction average varies during the years
        - The lack of promotion generates attrition.
        - The overall performance is low the first years, then starts to vary and, in the case of the employees that leave the company, after 15+ years, drop at minimums. 
        - The work balance also varies significantly during the time of the employees, showing that it must be one of the main reasons to attrite.
        - Although job satisfaction is constant, performance is dropping for departing workers.

3. **Insights**: 
    - The profiles that remain with the company the longest are those in the highest ranks and earn the best salaries.
    - The profiles with the highest turnover and the highest probability of attrition are those with lower rank, lower educational level and lower salary.
    - Although the company is moving towards parity, there is still a gender pay gap in the same job positions. There is also a noticeably lower presence of women than men.
    - The usual parameters of satisfaction do not prove to be relevant in this case. However, there is a high turnover in the sectors of employees who do not progress in their positions.

4. **Next Steps**: 
  - Identify specific areas for improvement: Review the results of the analysis to detect patterns or areas where employees express dissatisfaction, such as working conditions, internal communication or professional development.
  - Better understand the role of managers by department and attempt to correlate job satisfaction and time worked with the same manager.
  - To plot a correlation between satisfaction parameters specific to women
  - Evaluate the performance of senior managers and relate it to their contribution to the company.
  