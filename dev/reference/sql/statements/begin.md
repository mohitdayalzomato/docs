---
title: BEGIN | TiDB SQL Statement Reference
summary: An overview of the usage of BEGIN for the TiDB database.
category: reference
---

# BEGIN

This statement starts a new transaction inside of TiDB. It is similar to the statements `START TRANSACTION` and `SET autocommit=0`.

In the absense of a `BEGIN` statement, every statement will by default autocommit in its own transaction. This behavior ensures MySQL compatibility.

## Synopsis

**BeginTransactionStmt:**

![BeginTransactionStmt](/media/sqlgram-dev/BeginTransactionStmt.png)

## Examples

```sql
mysql> CREATE TABLE t1 (a int NOT NULL PRIMARY KEY);
Query OK, 0 rows affected (0.12 sec)

mysql> BEGIN;
Query OK, 0 rows affected (0.00 sec)

mysql> INSERT INTO t1 VALUES (1);
Query OK, 1 row affected (0.00 sec)

mysql> COMMIT;
Query OK, 0 rows affected (0.01 sec)
```

## MySQL compatibility

This statement is understood to be fully compatible with MySQL. Any compatibility differences should be [reported via an issue](/dev/report-issue.md) on GitHub.

## See also

* [COMMIT](/dev/reference/sql/statements/commit.md)
* [ROLLBACK](/dev/reference/sql/statements/rollback.md)
* [START TRANSACTION](/dev/reference/sql/statements/start-transaction.md)
