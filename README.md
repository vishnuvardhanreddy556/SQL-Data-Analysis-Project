
# 📊 EdTechLearnPro — End-to-End SQL Analytics Project

## 📌 Project Overview

EdTechLearnPro is an end-to-end SQL Analytics project developed using Microsoft SQL Server and SQL Server Management Studio (SSMS). The project focuses on designing and implementing a complete relational database for an EdTech platform and performing business-oriented data analysis. The project covers database creation, table design, data import, data cleaning, analytical queries, advanced SQL concepts, database programming, performance optimization, automation, auditing, and final business insights.

## 🎯 Project Objective

The main objective of this project is to build a structured EdTech database and use SQL to analyze student enrollments, courses, trainers, payments, and marketing activities. The project demonstrates how SQL can be used not only for data storage and retrieval but also for solving real-world business problems and generating meaningful analytical insights.

## 🗄️ Part 1 — Database & Schema

The project begins with the creation of the `EdTechLearnPro` database in SQL Server. The database environment was configured in SQL Server Management Studio, providing the foundation for all subsequent tables, relationships, queries, procedures, functions, and analytical operations.

## 🏗️ Part 2 — DDL & Constraints

The database schema was created using Data Definition Language (DDL). The major tables created were `STUDENTS`, `COURSES`, `TRAINERS`, `TRAINERCOURSEMAPPING`, `ENROLLMENTS`, `PAYMENTS`, and `MARKETING`. Data integrity was maintained using Primary Key, Foreign Key, UNIQUE, CHECK, DEFAULT, and NOT NULL constraints. These constraints ensure that the database maintains valid and consistent relational data.

## 📥 Part 3 — Data Import & Cleaning

The project datasets were imported into SQL Server from Excel sources. Student, course, trainer, trainer-course mapping, enrollment, payment, and marketing data were loaded into their respective tables. During the import process, duplicate records were identified and removed from the TrainerCourseMapping dataset, resulting in a cleaned dataset containing 24 unique mapping records.

## 🔎 Part 4 — DQL Analysis

Data Query Language was used to retrieve and analyze information from the database. The analysis included identifying the top five cities by enrollment, students enrolled in more than two courses, students without payment records, the highest revenue month, the top three courses by enrollment, enrollments with discounts above the average discount, and states having more than ten paid enrollments. These queries demonstrated the practical use of SELECT, WHERE, TOP, ORDER BY, GROUP BY, HAVING, aggregate functions, and subqueries.

## 🔗 Part 5 — JOINs

SQL JOIN operations were used to combine information from multiple relational tables. Student and course information was combined through enrollments, courses were connected with their assigned trainers, enrollment records were connected with payment information, and marketing data was compared with enrollment activity based on the enrollment month. This part demonstrated how relational databases can combine information stored across different tables for analytical purposes.

## 📊 Part 6 — GROUP BY & HAVING

Grouped analytical queries were performed to understand different aspects of the EdTech platform. Monthly revenue was calculated from payment data, enrollment counts were calculated for each course, average course fees were analyzed by category, trainer satisfaction was evaluated, and student registrations were analyzed by state. GROUP BY, HAVING, COUNT, SUM, AVG, and ORDER BY were used to generate these analytical results.

## 🧩 Part 7 — Subqueries & CTEs

Subqueries and Common Table Expressions were implemented to perform more advanced analysis. The project identified courses having above-average enrollment, students enrolled in the most expensive course, and enrollment records with the highest discount. A Common Table Expression was also created to organize monthly revenue calculations and make the analytical query easier to manage.

## 📈 Part 8 — Window Functions

Advanced SQL window functions were used for ranking, comparison, and data-quality analysis. `RANK()` was used to rank payment revenue within months, while `DENSE_RANK()` was used to rank courses based on monthly enrollments. `LAG()` and `LEAD()` were implemented to compare revenue with previous and subsequent months. `ROW_NUMBER()` was used to identify potential duplicate enrollment records, and the duplicate validation returned no duplicate records for the tested combination.

## 👁️ Part 9 — SQL Views

Reusable SQL views were created to simplify analytical reporting. The `vw_MonthlyRevenue` view provides monthly revenue information, while the `vw_TrainerPerformance` view provides trainer performance information based on assigned courses. These views create a reusable reporting layer that can be queried without rewriting the underlying analytical logic.

## ⚡ Part 10 — Indexes

Indexes were created to improve database query performance. Indexes were implemented on `STUDENTS.EMAIL`, `COURSES.COURSENAME`, and `ENROLLMENTS.ENROLLMENTDATE`, along with a composite index on `ENROLLMENTS(STUDENTID, COURSEID)`. The project also considered the importance of avoiding unnecessary indexes because excessive indexing can consume storage and negatively affect INSERT, UPDATE, and DELETE operations.

## ⚙️ Part 11 — Stored Procedures

Reusable stored procedures were implemented for common business operations. The `sp_MonthlyRevenue` procedure accepts a month as an input parameter and returns the corresponding revenue. The `sp_AddStudent` procedure validates whether a Student ID already exists before inserting a new student and returns a result message through an output parameter. The `sp_TrainerPerformance` procedure accepts a satisfaction-score threshold and returns trainers above that threshold along with the number of qualifying trainers through an output parameter.

## 🧮 Part 12 — User-Defined Functions

Two types of user-defined functions were implemented. The scalar function `fn_NetFeeAfterDiscount` calculates the final course fee after applying a percentage discount. The table-valued function `fn_EnrollmentsByCourse` returns enrollment records for a specified CourseID. These functions demonstrate how reusable business logic can be incorporated into SQL queries.

## 🚨 Part 13 — Exception Handling

SQL Server exception handling was implemented using `TRY...CATCH`. An `ErrorLog` table was created to store the Error ID, error message, error date, and user-friendly error message. A controlled divide-by-zero error was used to test the exception-handling mechanism, and the error was successfully captured and logged while a user-friendly message was returned.

## 🔐 Part 14 — Triggers

Three database triggers were implemented for validation, automation, and auditing. An `INSTEAD OF INSERT` trigger was used because SQL Server does not support a traditional BEFORE INSERT trigger; it prevents enrollment discounts greater than 50 percent. An `AFTER INSERT` trigger on the Payments table automatically sets `AmountPaid` to zero when the payment status is Unpaid. An `AFTER UPDATE` trigger records old and new payment amounts and payment statuses in the `AuditLog` table, providing an audit trail for payment changes.

## 📈 Part 15 — Final Analytics

The final analytics section focused on business-oriented insights. Customer Acquisition Cost (CAC) was calculated for marketing channels using total marketing spend divided by total leads generated. Marketing ROI was analyzed using available marketing and payment information. A month-by-city enrollment analysis was created to understand geographic demand over time. Course revenue was calculated and ranked, while trainer satisfaction was compared with enrollment activity. Month-over-month revenue growth was calculated using the `LAG()` window function to compare current-month revenue with previous-month revenue.

## 💡 Part 16 — Final Insights Report

The final insights report summarizes the major findings obtained from the SQL analysis. Revenue trends provide visibility into business performance over time, while CAC analysis helps evaluate marketing efficiency. Course enrollment and revenue analysis can identify high-performing courses, and city-wise enrollment analysis provides information about geographic demand. Trainer satisfaction and enrollment activity can be compared to understand trainer performance patterns. The project also highlights the importance of database constraints, exception handling, duplicate detection, triggers, and audit logging for maintaining data quality and reliability.

## 🔗 ER Diagram

The final Entity Relationship Diagram represents the relationships between the major entities in the EdTechLearnPro database. Students are connected to enrollments, courses are connected to enrollments and trainer-course mappings, enrollments are connected to payments, and trainers are connected to courses through TrainerCourseMapping. Marketing data is maintained separately for marketing analytics.

## 🧠 SQL Skills Demonstrated

This project demonstrates practical experience with SQL Server, DDL, DML, DQL, database constraints, relational JOINs, aggregate functions, GROUP BY and HAVING, subqueries, CTEs, window functions, views, indexes, stored procedures, input and output parameters, scalar functions, table-valued functions, TRY...CATCH, error logging, triggers, audit logging, ER modeling, and business analytics.

## 🛠️ Technologies Used

**Microsoft SQL Server | SQL Server Management Studio (SSMS) | SQL | Microsoft Excel | Relational Database Design | Data Analytics**

## 📊 Project Outcome

The EdTechLearnPro project demonstrates a complete end-to-end SQL workflow, starting from relational database design and data import and progressing through advanced SQL analysis, database programming, performance optimization, automation, auditing, and business insights. The project provides a strong foundation for further integration with Power BI, Tableau, Python, and advanced data analytics.

## 🚀 Future Enhancements

Future improvements can include Power BI and Tableau dashboard integration, student cohort analysis, customer lifetime value analysis, course completion analysis, marketing conversion analysis, campaign attribution, automated reporting, predictive enrollment analysis, and machine learning-based student behavior prediction.

## 👨‍💻 Author

**Vishnu Vardhan Reddy**

**Data Analytics | SQL | Python | Power BI | Tableau | Excel**

## ⭐ Project Status

**Completed ✅**
