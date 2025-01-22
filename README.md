# ETL-Pipeline-with-Kestra
Automated ETL pipeline using Kestra that: 1️⃣ Parallel-loads orders/products CSV data into PostgreSQL 2️⃣ Joins relational data 3️⃣ Syncs results to MongoDB 4️⃣ Triggers via PostgreSQL table changes (30s polling) Key Features: Idempotent design • Cross-DB sync • Self-cleaning triggers • Bulk operations.
