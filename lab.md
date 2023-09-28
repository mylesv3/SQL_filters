Retrieve after-hours failed login attempts
------------------------------------------

There was a potential security incident that occurred after business hours (after 18:00). All after-hours login attempts that failed need to be investigated.

The following code demonstrates how I created a SQL query to filter for failed login attempts that occurred after business hours.

![Screenshot of the command line with the SQL query for this task and its output](https://lh5.googleusercontent.com/rz5vjTotF_AhNIJdfFSWKT21EiTSen2cDuLSlIJ9xvkWkT_Ain8mP8DkafbUiA5Tla4dYyjfW2HyK3_L0T4CP2UhJCyHyQQNp54S3WtNoRk2dH9aVytkZZxsqKlbK1ZAmT173fGZcoYeiIvku1ixoPIDlsQdBXVWijesQjglqsXLRNW7eI0E2mpHcYGGfTs)

The first part of the screenshot is my query, and the second part is a portion of the output. This query filters for failed login attempts that occurred after 18:00. First, I started by selecting all data from the log_in_attempts  table. Then, I used a WHERE clause with an AND operator to filter my results to output only login attempts that occurred after 18:00 and were unsuccessful. The first condition is login_time > '18:00', which filters for the login attempts that occurred after 18:00. The second condition is success = FALSE, which filters for the failed login attempts. 

Retrieve login attempts on specific dates
-----------------------------------------

A suspicious event occurred on 2022-05-09. Any login activity that happened on 2022-05-09 or on the day before needs to be investigated.

The following code demonstrates how I created a SQL query to filter for login attempts that occurred on specific dates.

![Screenshot of the command line with the SQL query for this task and its output](https://lh3.googleusercontent.com/OIAWRmS2vzT92KHCqVE4cePmnWEjzA0-cxnUIXxR6U45n1RHSVsA1hi5wireaN1_XS6ba6_BzyCY1wwSbhZy7zVKQpsRJZoR8FazkwyN2fiwCNXc2-xBPGFvi9iHZ2QKdgI8P5mXjgcfVxV7pI03iOMP8tzyp0WaXNvZzxlGTEG7sYJ6rEcwuYUqK_7aXt4)

The first part of the screenshot is my query, and the second part is a portion of the output. This query returns all login attempts that occurred on 2022-05-09 or 2022-05-08. First, I started by selecting all data from the log_in_attempts table. Then, I used a WHERE clause with an OR operator to filter my results to output only login attempts that occurred on either 2022-05-09 or 2022-05-08. The first condition is login_date = '2022-05-09', which filters for logins on 2022-05-09. The second condition is login_date = '2022-05-08', which filters for logins on 2022-05-08.

Retrieve login attempts outside of Mexico
-----------------------------------------

After investigating the organization's data on login attempts, I believe there is an issue with the login attempts that occurred outside of Mexico. These login attempts should be investigated.

The following code demonstrates how I created a SQL query to filter for login attempts that occurred outside of Mexico.

![Screenshot of the command line with the SQL query for this task and its output](https://lh4.googleusercontent.com/3OXynQcidJA6rdAM9GzdyWfTBOmuKJDDe9D4gmKiAzQDbk3WymhS4CBqLRdyg9OmTCvVw60S4oB5VHajqSlML6GBG8N6TdxMzZX8Oo3mdL1f1B_keRQaIc4y7Wsr0cqRAslKzUjCWKbAo4_qY2V1sxiV3eVYyFeV2oWEkPQcA5CySwmJ8aLp7mgPQ7tYb08)

The first part of the screenshot is my query, and the second part is a portion of the output. This query returns all login attempts that occurred in countries other than Mexico. First, I started by selecting all data from the log_in_attempts table. Then, I used a WHERE clause with NOT to filter for countries other than Mexico. I used LIKE with MEX% as the pattern to match because the dataset represents Mexico as MEX and MEXICO. The percentage sign (%) represents any number of unspecified characters when used with LIKE. 

Retrieve employees in Marketing
-------------------------------

My team wants to update the computers for certain employees in the Marketing department. To do this, I have to get information on which employee machines to update.

The following code demonstrates how I created a SQL query to filter for employee machines from employees in the Marketing department in the East building.

![Screenshot of the command line with the SQL query for this task and its output](https://lh5.googleusercontent.com/inkL8c9mE8LMKXqSQjvUrW2YAQKkCA8-Rt1p-kJJ2lMpiF7WGnnwBimNrJSSwsHHSKrWcwLkeuQYxEgiHBVb3KHTxy-qIeRnIgie9zeey2KjEnuKiJPaHxT9_0u46LQDGTs7JY9b-9j3sLzy8T9YcG3fhsVl9kK8lNwstZGLWKh3CKCBF6imTm1iukNx81w)

The first part of the screenshot is my query, and the second part is a portion of the output. This query returns all employees in the Marketing department in the East building. First, I started by selecting all data from the employees table. Then, I used a WHERE clause with AND to filter for employees who work in the Marketing department and in the East building. I used LIKE with East% as the pattern to match because the data in the office column represents the East building with the specific office number. The first condition is the department = 'Marketing' portion, which filters for employees in the Marketing department. The second condition is the office LIKE 'East%' portion, which filters for employees in the East building.

Retrieve employees in Finance or Sales
--------------------------------------

The machines for employees in the Finance and Sales departments also need to be updated. Since a different security update is needed, I have to get information on employees only from these two departments.

The following code demonstrates how I created a SQL query to filter for employee machines from employees in the Finance or Sales departments.

![Screenshot of the command line with the SQL query for this task and its output](https://lh5.googleusercontent.com/Vw1QNhfOdvQwQD9qOl3bUQf16dqcxb5L_kmP_SjIw6K4T_SocU7Gct95lWX1Eu6lmuseQE0HFe8h7lY1HhDH9JvI9bfEn2DUmz6NCjCmBs3-KmiwaL1caK9uOrjpbXxldCX9nuivRpZGIWeJNezD4MLQl93NM-0AxvggfVWIF9GYzYhVVxHCKFXOSVpXDnc)

The first part of the screenshot is my query, and the second part is a portion of the output. This query returns all employees in the Finance and Sales departments. First, I started by selecting all data from the employees table. Then, I used a WHERE clause with OR to filter for employees who are in the Finance and Sales departments. I used the OR operator instead of AND because I want all employees who are in either department. The first condition is department = 'Finance', which filters for employees from the Finance department. The second condition is department = 'Sales', which filters for employees from the Sales department.

Retrieve all employees not in IT
--------------------------------

My team needs to make one more security update on employees who are not in the Information Technology department. To make the update, I first have to get information on these employees.

The following demonstrates how I created a SQL query to filter for employee machines from employees not in the  Information Technology department.

![Screenshot of the command line with the SQL query for this task and its output](https://lh6.googleusercontent.com/GblnwDx9a8L3WnmMZO_4JeDSP483pGtOCLdZlidWAWiaGtTZmQCZIVgROQesPXE2Hr0rqe4Zux61HK6rpghTKGT81db8lQ7SPRNFe_ssHIrJxRzFa-9e5gTK8rJA3m1YUzW-ya7ccIA1IVvN6JgHVvu-K1cQ1B7Jtu0viqi4PuGdd3ivgadQTUlRS3wSUk8)

The first part of the screenshot is my query, and the second part is a portion of the output. The query returns all employees not in the Information Technology department. First, I started by selecting all data from the employees table. Then, I used a WHERE clause with NOT to filter for employees not in this department.

Summary
-------

I applied filters to SQL queries to get specific information on login attempts and employee machines. I used two different tables, log_in_attempts and employees. I used the AND, OR, and NOT operators to filter for the specific information needed for each task. I also used LIKE and the percentage sign (%) wildcard to filter for patterns.

