# SQL Joins

A SQL join combines related rows from two or more tables. Joins are important because relational databases commonly store related information in separate tables.

## INNER JOIN
Returns only matching rows from both tables.

```sql
SELECT customers.name, orders.amount
FROM customers
INNER JOIN orders
ON customers.customer_id = orders.customer_id;
```

## LEFT JOIN
Returns every row from the left table and matching rows from the right table. If no match exists, right-side values are `NULL`.

## RIGHT JOIN
Returns every row from the right table and matching rows from the left table.

## FULL OUTER JOIN
Returns matching rows and unmatched rows from both tables.

## CROSS JOIN
Produces every possible combination of rows from two tables. It should be used carefully because the result can become very large.

## SELF JOIN
A table can also be joined with itself. This is useful for relationships such as employees and their managers.

```sql
SELECT employee.employee_name, manager.employee_name
FROM employees AS employee
LEFT JOIN employees AS manager
ON employee.manager_id = manager.employee_id;
```

Choosing the correct join depends on whether unmatched rows should be included. Joins are commonly used with filtering, aggregation, and ordering to build useful database queries.
