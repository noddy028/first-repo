
```sql
select * from user
```

```SQL
select * from student
```

INSERT INTO Departments (department_id, department_name) VALUES
    -> (101, 'HR'),
    -> (102, 'Finance'),
    -> (104, 'IT');
Query OK, 3 rows affected (0.02 sec)
Records: 3  Duplicates: 0  Warnings: 0

mysql> INSERT INTO Projects (project_id, project_name, emp_id) VALUES
    -> (201, 'ProjectA', 1),
    -> (202, 'ProjectB', 2),
    -> (203, 'ProjectC', 6),
    -> (204, 'ProjectD', 3);
Query OK, 4 rows affected (0.01 sec)
Records: 4  Duplicates: 0  Warnings: 0

mysql> select * from departments;
+---------------+-----------------+
| department_id | department_name |
+---------------+-----------------+
|           101 | HR              |
|           102 | Finance         |
|           104 | IT              |
+---------------+-----------------+
3 rows in set (0.00 sec)

mysql> select * from projects;
+------------+--------------+--------+
| project_id | project_name | emp_id |
+------------+--------------+--------+
|        201 | ProjectA     |      1 |
|        202 | ProjectB     |      2 |
|        203 | ProjectC     |      6 |
|        204 | ProjectD     |      3 |
+------------+--------------+--------+
4 rows in set (0.00 sec)

mysql> select * from employees;
+--------+----------+---------------+----------+
| emp_id | emp_name | department_id | salary   |
+--------+----------+---------------+----------+
|      1 | Alice    |           101 | 70000.00 |
|      2 | Bob      |           102 | 60000.00 |
|      3 | Charlie  |           103 | 50000.00 |
|      4 | David    |          NULL | 40000.00 |
|      5 | Eva      |           102 | 65000.00 |
+--------+----------+---------------+----------+
5 rows in set (0.00 sec)

mysql>
mysql> Get the list of employees along with their department names (only if they belong to a department)
    -> ^C
mysql> SELECT
    ->     e.emp_id,
    ->     e.emp_name,
    ->     d.department_name
    -> FROM
    ->     Employees e
    -> INNER JOIN
    ->     Departments d
    -> ON
    ->     e.department_id = d.department_id;
+--------+----------+-----------------+
| emp_id | emp_name | department_name |
+--------+----------+-----------------+
|      1 | Alice    | HR              |
|      2 | Bob      | Finance         |
|      5 | Eva      | Finance         |
+--------+----------+-----------------+
3 rows in set (0.01 sec)

mysql> select e.emp_id,e.emp_name,d.department_name from Employees e inner join departments d on e.department_id=d.department_id;
+--------+----------+-----------------+
| emp_id | emp_name | department_name |
+--------+----------+-----------------+
|      1 | Alice    | HR              |
|      2 | Bob      | Finance         |
|      5 | Eva      | Finance         |
+--------+----------+-----------------+
3 rows in set (0.00 sec)

mysql>