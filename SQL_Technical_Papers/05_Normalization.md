# Database Normalization

Normalization is the process of organizing database tables to reduce unnecessary duplication and improve data integrity.

## First Normal Form (1NF)
1NF requires atomic values and avoids repeating groups.

Instead of:

```text
student_id | courses
1          | SQL, Python
```

use separate rows:

```text
student_id | course
1          | SQL
1          | Python
```

## Second Normal Form (2NF)
A table must be in 1NF, and every non-key attribute must depend on the whole primary key. This is especially important for composite keys.

## Third Normal Form (3NF)
A table must be in 2NF, and non-key attributes should not depend on other non-key attributes.

For example, instead of storing:

```text
employee_id
employee_name
department_id
department_name
```

separate employees and departments into related tables.

## Benefits

Normalization:

* Reduces duplicate data.
* Improves consistency.
* Makes updates easier.
* Reduces update and deletion anomalies.
* Creates clearer relationships.

Highly normalized databases may require more joins. For specific performance requirements, controlled denormalization can sometimes be appropriate.

Normalization is mainly a database design technique used to organize relational data logically and efficiently.
