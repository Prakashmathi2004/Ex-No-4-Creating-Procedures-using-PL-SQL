# Ex. No. 4: Creating Procedures using PL/SQL

### AIM: To create a procedure using PL/SQL

### Steps:
1. Create employee table with following attributes (empid NUMBER, empname VARCHAR(10), dept VARCHAR(10),salary NUMBER);
2. Create a procedure named as insert_employee data.
3. Inside the procedure block, write the query for inserting the values into the employee table.
4. End the procedure.
5. Call the insert_employee procedure to insert the values into the employee table.
6. Display the employee table

### Program:
```sql
CREATE TABLE employee(empid NUMBER,
empname VARCHAR(10),
 dept VARCHAR(10),
salary NUMBER);

CREATE OR REPLACE PROCEDURE insert_employee AS
BEGIN
INSERT INTO employee(empid, empname, dept, salary)
VALUES (1,'PRAVEEN','CSE',50000);
INSERT INTO employee(empid, empname, dept, salary)
VALUES (2,'PRAKASH','IT',60000);
INSERT INTO employee(empid, empname, dept, salary)
VALUES (3,'SANTHOSH','Finance',55000);
COMMIT;
FOR emp_rec IN (SELECT * FROM employee) LOOP
DBMS_OUTPUT.PUT_LINE('Employee ID: ' || emp_rec.empid || 'Name' || emp_rec.empname
|| 'Department' || emp_rec.dept || 'Salary' || emp_rec.salary);
END LOOP;
END;
/
```

### Output:
<img width="593" alt="image" src="https://github.com/Prakashmathi2004/Ex-No-4-Creating-Procedures-using-PL-SQL/assets/118350045/a0dfdfc3-8445-418b-96af-6cb60c5c738b">


### Result:
Thus a procedure has been successfully created and executed.
