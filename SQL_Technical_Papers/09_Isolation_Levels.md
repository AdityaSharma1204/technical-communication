# Database Isolation Levels

Isolation levels control how concurrent transactions interact with each other. They determine what changes one transaction can see from another transaction.

The commonly discussed levels are:

1. Read Uncommitted
2. Read Committed
3. Repeatable Read
4. Serializable

## Read Uncommitted

This provides weak isolation and may allow dirty reads, where a transaction reads data that another transaction has not committed.

## Read Committed

Dirty reads are prevented. A query sees data committed before that query begins. PostgreSQL uses Read Committed as its default isolation level.

## Repeatable Read

A transaction gets a more stable view of data. Repeated reads of the same data remain consistent according to the database's implementation.

## Serializable

Serializable is the strongest standard isolation level. Concurrent transactions should produce a result equivalent to some serial execution.

Serializable provides strong consistency but can cause transactions to fail and require retries when concurrent operations conflict.
