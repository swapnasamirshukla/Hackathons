Problem Statement:
  You are working as a data scientist with HR Department of a large insurance company focused on sales team attrition. Insurance sales teams help insurance companies generate new   business by contacting potential customers and selling one or more types of insurance. The department generally sees high attrition and thus staffing becomes a crucial aspect.

To aid staffing, you are provided with the monthly information for a segment of employees for 2016 and 2017 and tasked to predict whether a current employee will be leaving the organization in the upcoming two quarters (01 Jan 2018 - 01 July 2018) or not, given:

  1.Demographics of the employee (city, age, gender etc.)
  2.Tenure information (joining date, Last Date)
  3.Historical data regarding the performance of the employee (Quarterly rating, Monthly business acquired, designation, salary)

Approach

Model the Problem as a Survival Analysis Problem : What is the probability of an Employee resigning as the number of days in the company increases
Generate Features:-
  1. Count no. of times Quarterly Rating has changed for an employee
  2. Calculate the number of times designation has changed for an employee
  3. Generate Quarter and Year from Reporting Date
  4. Times an employee did no business
  5. Times the generated business had to be pulled off/cancelled
  6. Total Business Value Generated
  7. Times Quarter on Quarter Business Value has dropped
  8. Total Days Worked: In case an employee has not resigned, Total Days = 30/06/2018-Date of joining
  
  Model Used : CoxPHFitter (https://lifelines.readthedocs.io/en/latest/fitters/regression/CoxPHFitter.html)
