# ACID

ACID describes four properties that make database transactions reliable.

## 1. Atomicity
Atomicity means a transaction is treated as one complete unit. Either all operations succeed or none are applied.

```sql
BEGIN;

UPDATE accounts SET balance = balance - 1000
WHERE account_id = 1;

UPDATE accounts SET balance = balance + 1000
WHERE account_id = 2;

COMMIT;
```

If an operation fails, `ROLLBACK` can undo the transaction.

## 2. Consistency
Consistency means a transaction changes the database from one valid state to another. Constraints such as `PRIMARY KEY`, `FOREIGN KEY`, `UNIQUE`, `NOT NULL`, and `CHECK` help maintain consistency.

## 3. Isolation
Isolation controls how concurrent transactions interact. One transaction should not incorrectly interfere with another transaction's intermediate work.

## 4. Durability
Durability means committed changes remain stored even after a system failure or restart.

## Importance
ACID is especially important for banking, payments, inventory, reservations, and other systems where incorrect or partial updates can cause serious problems.
