

To create a database

```
CREATE DATABASE database-name; 
```

You must run the use command to utilize the database, afterwards you can create tables.

```
USE database-name;
```

To delete the database

```
DROP DATABASE database-name;
```


Creates a table with the information, and values given, accordingly.
The “employee_email” column, has been set to UNIQUE, which wont accept multiple of the same entries of data into that specific column 

```
CREATE TABLE employee_details (
employee_number INT(15),
employee_email VARCHAR(50) UNIQUE ,
hourly_pay DECIMAL(5, 2),
hire_date DATE
);

```

If for any reason you would like to rename the table, you can run the rename command.

```
RENAME TABLE employee_details TO workers;
```


