# 25MCI10047_LakshayAggarwal_25MAM_KAR-1_DBMS
DBMS Practical MST-1

## Question 1

```sql

CREATE TABLE Purchases (
    purchase_id SERIAL PRIMARY KEY,
    customer_id INT,
    product_id INT,
    purchase_date DATE
);

INSERT INTO Purchases (customer_id, product_id, purchase_date) VALUES
(101, 1, '2026-03-01'),
(102, 1, '2026-03-01'),
(103, 2, '2026-03-01'),
(104, 1, '2026-03-01'),
(105, 3, '2026-03-02'),
(101, 2, '2026-03-02'),
(102, 2, '2026-03-02'),
(106, 1, '2026-03-01'),
(107, 3, '2026-03-02'),
(108, 1, '2026-03-03');

--- Question 1
SELECT p1.product_id, 
p1.purchase_date,
p1.customer_id as Customer1,
p2.customer_id as Customer2
from Purchases p1
join Purchases p2
on p1.product_id=p2.product_id
and p1.purchase_date=p2.purchase_date
and p1.customer_id<p2.customer_id;




```

<img width="538" height="210" alt="image" src="Output Q1.png" />

## Question 2
```sql
CREATE TABLE Employees (
    emp_id INT PRIMARY KEY,
    emp_name VARCHAR(50),
    manager_id INT,
    department VARCHAR(50),
    salary INT
);
INSERT INTO Employees VALUES
(1, 'Amit', NULL, 'Management', 120000),
(2, 'Ravi', 1, 'Engineering', 80000),
(3, 'Neha', 1, 'Engineering', 82000),
(4, 'Karan', 2, 'Engineering', 60000),
(5, 'Simran', 2, 'Engineering', 62000),
(6, 'Pooja', 3, 'Engineering', 61000),
(7, 'Rahul', 3, 'Engineering', 64000),
(8, 'Arjun', 1, 'HR', 70000);

---question 2
CREATE VIEW HighSalaryEmployees AS
SELECT emp_id, emp_name, salary
FROM Employees
WHERE salary > 50000;

SELECT * FROM HighSalaryEmployees;
```
<img width="227" height="82" alt="image" src="output Q2.png" />
