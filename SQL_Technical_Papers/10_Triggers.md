# Database Triggers

A trigger is database logic that automatically runs when a specified event occurs. Common events include `INSERT`, `UPDATE`, and `DELETE`.

Triggers are useful when an action should happen automatically whenever data changes.

## BEFORE Trigger

A `BEFORE` trigger runs before the database operation. It can validate or modify data.

```sql
CREATE OR REPLACE FUNCTION check_salary()
RETURNS TRIGGER AS $$
BEGIN
    IF NEW.salary < 0 THEN
        RAISE EXCEPTION 'Salary cannot be negative';
    END IF;

    RETURN NEW;
END;
$$ LANGUAGE plpgsql;
```

The trigger can be attached to a table:

```sql
CREATE TRIGGER salary_check
BEFORE INSERT OR UPDATE
ON employees
FOR EACH ROW
EXECUTE FUNCTION check_salary();
```

## AFTER Trigger

An `AFTER` trigger runs after the operation. It is commonly used for audit logging.

Examples include:

* Recording changes.
* Maintaining audit tables.
* Updating related information.

## Row-Level and Statement-Level

A row-level trigger runs once for every affected row.

A statement-level trigger runs once for the entire SQL statement, regardless of how many rows it changes.

## Advantages

Triggers can enforce database-level rules and automatically record important changes.

## Disadvantages

Triggers can make application behaviour harder to understand and debug. Too many triggers can also increase database workload.

Triggers should therefore be used when automatic database-level behaviour is genuinely required.
