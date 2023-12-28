
ALTER TABLE 
ALTER TABLE employee_details

ADD employee_age INT(20);
To add a new column “employee_age” 
DROP COLUMN employee_email;
To drop the email column from the table
RENAME COLUMN phone_number TO employee_email;
To rename the column “phone_number” to “email” 
database-name READ ONLY = 1;
Altering the database to read only mode, in read-only you cannot drop the database

MODIFY email VARCHAR(100);
AFTER  employee_numbers;  	
	
FIRST;

ADD CONSTRAINT 
UNIQUE(column_name);
This will first add a constraint, the constraint will be a UNIQUE column, whichever specified 
If we try to add a duplicate column, we will be presented with the error below
Error Code: 1062. Duplicate entry 'Bob' for key 'dummy.first_name'


