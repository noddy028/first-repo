# SQL Query Documentation

## Table: `departments`
```sql
SELECT * FROM departments;
```
| department_id | department_name |
|---------------|-----------------|
| 101           | HR              |
| 102           | Finance         |
| 104           | IT              |

---

## Table: `projects`
```sql
SELECT * FROM projects;
```
| project_id | project_name | emp_id |
|------------|--------------|--------|
| 201        | ProjectA     | 1      |
| 202        | ProjectB     | 2      |
| 203        | ProjectC     | 6      |
| 204        | ProjectD     | 3      |

---

## Table: `employees`
```sql
SELECT * FROM employees;
```
| emp_id | emp_name | department_id | salary   |
|--------|----------|----------------|----------|
| 1      | Alice    | 101            | 70000.00 |
| 2      | Bob      | 102            | 60000.00 |
| 3      | Charlie  | 103            | 50000.00 |
| 4      | David    | NULL           | 40000.00 |
| 5      | Eva      | 102            | 65000.00 |

---

## Query: Employees with Departments
```sql
SELECT 
    e.emp_id,
    e.emp_name,
    d.department_name
FROM 
    Employees e
INNER JOIN 
    departments d 
ON 
    e.department_id = d.department_id;
```

### Result:
| emp_id | emp_name | department_name |
|--------|----------|-----------------|
| 1      | Alice    | HR              |
| 2      | Bob      | Finance         |
| 5      | Eva      | Finance         |

<!-- This will retrieve emp_id,emp_name and department_name from the respective tables according to the aliases given -->