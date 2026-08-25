# Database Indexes

An index is a database structure that helps find rows more efficiently. Without a suitable index, the database may need to examine many rows to find matching records.

## Creating an Index

```sql
CREATE INDEX employee_name_index
ON employees(name);
```

This can improve queries that search using `name`.

## Unique Index

A unique index prevents duplicate indexed values.

```sql
CREATE UNIQUE INDEX employee_email_index
ON employees(email);
```

## Composite Index

An index can contain multiple columns.

```sql
CREATE INDEX department_salary_index
ON employees(department_id, salary);
```

The order of columns in a composite index matters because databases can use leading columns more effectively.

## Advantages

Indexes can:

* Speed up searches.
* Improve filtering.
* Improve some joins.
* Help with sorting.
* Enforce uniqueness.

## Disadvantages

Indexes also have costs:

* They consume storage.
* Inserts can become slower.
* Updates can become slower.
* Deletes can become slower.
* They require maintenance.
