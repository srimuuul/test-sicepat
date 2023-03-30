# DB Schema

```
CREATE TABLE tbl_employee (
  emp_code varchar(20),
  emp_name varchar(20),
  emp_status varchar(20)
);
```

```
CREATE TABLE tbl_income (
  emp_code varchar(20),
  emp_income int
);
```

```
INSERT INTO tbl_employee (emp_code, emp_name, emp_status)
VALUE
  ('Emp001', 'Abdi', 'R'),
  ('Emp002', 'Budi', 'P'),
  ('Emp003', 'Cahya', 'P'),
  ('Emp004', 'Danu', 'P');
```

```
INSERT INTO tbl_income (emp_code, emp_income)
VALUE
  ('Emp001', 10000000),
  ('Emp002', 9000000),
  ('Emp003', 15000000),
  ('Emp004', 12000000);
```

# SQL Query

## 1a - Show data employee with parameter name & status
```
SELECT * FROM tbl_employee WHERE emp_name LIKE '%di' AND emp_status = 'P';
```

## 1b - Show employee name, status, and income where status is `R or Resign`
```
SELECT
  tbl_employee.emp_name,
  tbl_employee.emp_status,
  tbl_income.emp_income
FROM tbl_employee, tbl_income
WHERE tbl_employee.emp_code = tbl_income.emp_code AND tbl_employee.emp_status = 'R';
```

## 1c - Show employee code, name, status, and income with descending sorting of income
```
SELECT
  tbl_employee.emp_code,
  tbl_employee.emp_name,
  tbl_employee.emp_status,
  tbl_income.emp_income
FROM tbl_employee, tbl_income
WHERE tbl_employee.emp_code = tbl_income.emp_code
ORDER BY tbl_income.emp_income DESC;
```