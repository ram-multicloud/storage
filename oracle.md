## sample oracle query to run in db 
```sql 

CREATE USER myapp_user IDENTIFIED BY MyPassword123;

GRANT CONNECT, RESOURCE TO myapp_user;
GRANT UNLIMITED TABLESPACE TO myapp_user;

CREATE TABLE employees (
    emp_id      NUMBER PRIMARY KEY,
    first_name  VARCHAR2(50),
    last_name   VARCHAR2(50),
    email       VARCHAR2(100),
    hire_date   DATE,
    salary      NUMBER(10,2)
);

SELECT table_name FROM user_tables WHERE table_name = 'EMPLOYEES';

INSERT INTO employees (emp_id, first_name, last_name, email, hire_date, salary)
VALUES (1, 'John', 'Doe', 'john.doe@example.com', TO_DATE('2023-01-15','YYYY-MM-DD'), 55000);

INSERT INTO employees (emp_id, first_name, last_name, email, hire_date, salary)
VALUES (2, 'Jane', 'Smith', 'jane.smith@example.com', TO_DATE('2023-03-10','YYYY-MM-DD'), 62000);

INSERT INTO employees (emp_id, first_name, last_name, email, hire_date, salary)
VALUES (3, 'Mike', 'Johnson', 'mike.johnson@example.com', TO_DATE('2023-06-01','YYYY-MM-DD'), 58000);

COMMIT;

SELECT * FROM employees;

```
