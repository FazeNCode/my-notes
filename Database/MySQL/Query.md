QUERY DATA FROM TABLE


This way, you will only see a filtered list of tables instead of looking through all of them:
```
SHOW TABLES LIKE  ‘a%’; 
```

In case you need more information about the tables in your database, use the following query to list all the tables along with their types:
```
SHOW FULL TABLES;
```

Display all the columns in the table
```
SHOW COLUMNS FROM TABLE-NAME;
```

Display everything from employee_details table
```
SELECT * FROM employee_details;
```

Display only the first and last name columns from the employee_details table
```
SELECT first_name, last_name  FROM employee_details;
```

When setting Auto commit off you must manually commit the changes.
```
SET AUTOCOMMIT = OFF;
```

Manually commiting  
```
COMMIT;
```


To rollback to when we COMMIT; to save changes manually
```
ROLLBACK;
```



