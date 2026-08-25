# Database Transactions

A transaction is a group of database operations treated as one logical unit. Transactions are useful when several operations must succeed together.

## BEGIN

A transaction can be started with:

```sql
BEGIN;
```

## COMMIT

`COMMIT` permanently applies successful changes.

```sql
BEGIN;

UPDATE products
SET stock = stock - 1
WHERE product_id = 10;

COMMIT;
```

## ROLLBACK

`ROLLBACK` cancels changes made during the transaction.

```sql
BEGIN;

UPDATE products
SET stock = stock - 1
WHERE product_id = 10;

ROLLBACK;
```

## SAVEPOINT

A savepoint allows a transaction to roll back part of its work.

```sql
BEGIN;

INSERT INTO orders VALUES (101, 1);

SAVEPOINT order_savepoint;

ROLLBACK TO order_savepoint;

COMMIT;
```
