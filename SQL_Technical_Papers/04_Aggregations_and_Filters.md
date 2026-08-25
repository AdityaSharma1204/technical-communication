# Aggregations and Filters in SQL

SQL provides filtering and aggregation features for retrieving and analyzing data.

## Filtering

The `WHERE` clause filters individual rows.

```sql
SELECT *
FROM employees
WHERE salary > 50000;
```

Common operators include `=`, `>`, `<`, `>=`, `<=`, `IN`, `BETWEEN`, `LIKE`, and `IS NULL`.

## Aggregate Functions

Aggregate functions calculate values from multiple rows. Common functions are:

* `COUNT()`
* `SUM()`
* `AVG()`
* `MIN()`
* `MAX()`

Example:

```sql
SELECT AVG(salary)
FROM employees;
```

## GROUP BY

`GROUP BY` creates groups before aggregation.

```sql
SELECT department, AVG(salary)
FROM employees
GROUP BY department;
```

This calculates the average salary for each department.

## HAVING

`HAVING` filters groups after aggregation.

```sql
SELECT department, AVG(salary) AS average_salary
FROM employees
GROUP BY department
HAVING AVG(salary) > 60000;
```

The key difference is that `WHERE` filters rows before grouping, while `HAVING` filters groups after aggregation.

These features are fundamental for reports, dashboards, statistics, and business analysis.
