QUERY DATA FROM TABLE

SHOW TABLES LIKE  ‘a%’; 
This way, you will only see a filtered list of tables instead of looking through all of them:
SHOW FULL TABLES;
In case you need more information about the tables in your database, use the following query to list all the tables along with their types:
SHOW COLUMNS FROM TABLE-NAME;
This will show all the columns in the table

SELECT * FROM employee_details;
Display everything from employee_details table
SELECT first_name, last_name  FROM employee_details;
Display only the first and last name columns from the employee_details table


SET AUTOCOMMIT = OFF;
Will have to manually commit changes it when it’s turned OFF
COMMIT;
Will commit the changes when called upon
ROLLBACK;
To rollback to when we COMMIT; to save changes manually

