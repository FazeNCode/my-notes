
ALTER TABLE 

```
ALTER TABLE employee_details
```

To add a new column “employee_age” 
```
ADD employee_age INT(20);
```


To drop the email column from the table
```
DROP COLUMN employee_email;
```


To rename the column “phone_number” to “email” 
```
RENAME COLUMN phone_number TO employee_email;
```



Altering the database to read only mode, in read-only you cannot drop the database
```
database-name READ ONLY = 1;
```




This will first add a constraint, the constraint will be a UNIQUE column, whichever specified 
If we try to add a duplicate column, we will be presented with an error, Example below.
Error Code: 1062. Duplicate entry 'Bob' for key 'dummy.first_name'

```
MODIFY email VARCHAR(100);
AFTER  employee_numbers;  	
	
FIRST;

ADD CONSTRAINT 
UNIQUE(column_name);
```


