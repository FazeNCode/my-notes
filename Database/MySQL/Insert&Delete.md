INSERT AND DELETE FROM TABLE

INSERT INTO employee_details
VALUES 
("Faisal", "Chops", 1, 647-893-9110, "Faisal_chop@outlook.com", 50.00, "2023/03/23"),
("Sponge", "Bob",  2, 647-833-9110, "Sponge_bob@outlook.com", 50.00, "2023/03/23"),
("Sandy", "Chop",  3, 647-813-9110, "Sandy_chop@outlook.com", 60.00, "2023/03/23"),
("Bob", "Builds",     4,  647-823-9110, "Bob_builds@outlook.com", 40.00, "2023/03/23");
This will add the values given above to our “employee_details” table

INSERT INTO employee_details (first_name, last_name, employee_id)
VALUES ("Sponge", "bob", 1);
Instead of inserting information of employees for every column, we can define which columns we want filled in. the rest will stay NULL

INSERT INTO employee_details
VALUES(CURRENT_DATE(), CURRENT_TIME(), NOW());
Will set the current date and time 
VALUES(CURRENT_DATE() -1
Will set the current date -1 day in the past. Add +1 to set one day in future


DELETE FROM employee_info
Will delete all the data in the “employee_info” table
Make sure to add the WHERE clause preventing it from deleting your whole table

DELETE FROM employee_info
WHERE employee_id = 6;
Will delete the employee row with the id #6

