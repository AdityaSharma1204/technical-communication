# Database Locking Mechanisms

Locking controls concurrent access to database resources. It helps prevent conflicting transactions from changing the same data incorrectly.

## Row-Level Lock

A row-level lock protects a specific row.

```sql
BEGIN;

SELECT *
FROM accounts
WHERE account_id = 1
FOR UPDATE;

UPDATE accounts
SET balance = balance - 500
WHERE account_id = 1;

COMMIT;
```

`FOR UPDATE` requests a lock on the selected row.

## Table-Level Lock

A table-level lock applies to a table rather than a single row. It can be useful for operations requiring stronger protection, but it may reduce concurrency.

## Shared and Exclusive Locks

Shared locks generally allow compatible reads while preventing conflicting changes. Exclusive locks prevent other conflicting operations on the protected resource.

The exact lock modes depend on the database system.

## Deadlocks

A deadlock occurs when transactions wait for each other.

For example:

```text
Transaction A locks Row 1
Transaction B locks Row 2
A waits for Row 2
B waits for Row 1
```

Neither transaction can continue until the database resolves the deadlock.

## Best Practices

* Keep transactions short.
* Lock only what is necessary.
* Access resources in a consistent order.
* Handle deadlock errors appropriately.
