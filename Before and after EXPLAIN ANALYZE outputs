# PostgreSQL Performance Lab

## Overview
This repository contains a hands-on PostgreSQL performance lab covering table creation, large-data generation, query tuning with `EXPLAIN ANALYZE`, transaction isolation behavior, and PgBouncer configuration.

## Objectives
- Create a large `orders` table and load it with approximately 2,000,000 rows.
- Measure a slow aggregation query before and after adding an index.
- Demonstrate `READ COMMITTED` and `REPEATABLE READ` transaction behavior.
- Configure PgBouncer and document connection pooling benefits.

## Repository Structure
- `schema/` – table definition
- `data/` – data generation script
- `performance/` – slow query, index tuning, and EXPLAIN outputs
- `isolation/` – transaction isolation demos and notes
- `pgbouncer/` – PgBouncer config and connection notes
- `docs/` – reports and reflections

## Setup Instructions
1. Create a PostgreSQL database named `bootcamp`.
2. Run the table creation script from `schema/orders_table.sql`.
3. Run the data load script from `data/generate_orders.sql`.
4. Execute the query in `performance/slow_query.sql` and save the plan to `performance/before_explain.txt`.
5. Apply the index in `performance/index_optimization.sql` and rerun the query to capture `performance/after_explain.txt`.
6. Review the isolation demos in `isolation/` and the PgBouncer configuration in `pgbouncer/`.

## Commands Used
```sql
CREATE TABLE orders (...);
INSERT INTO orders (...)
SELECT ... FROM generate_series(1, 2000000) AS s(i);
ANALYZE orders;

EXPLAIN (ANALYZE, BUFFERS)
SELECT ...;

CREATE INDEX idx_pending_recent
ON orders (created_at DESC, customer_id)
WHERE status = 'pending';

psql -h 127.0.0.1 -p 6432 -U postgres bootcamp
```
