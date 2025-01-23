# ETL-Pipeline-with-Kestra
Automated ETL pipeline using Kestra that:


1️⃣ Parallel-loads orders/products CSV data into PostgreSQL 


2️⃣ Joins relational data


3️⃣ Syncs results to MongoDB 


4️⃣ Triggers via PostgreSQL table changes (30s polling) Key Features: Idempotent design • Cross-DB sync • Self-cleaning triggers • Bulk operations.


# Order Details ETL Pipeline with Kestra

This workflow loads order data from CSV sources into PostgreSQL, joins it with product data, and transfers the combined results to MongoDB. It includes automatic triggering based on PostgreSQL conditions.

![WhatsApp Image 2025-01-22 at 22 59 43_870010c2](https://github.com/user-attachments/assets/6921cfd6-d465-4ad2-a7f2-50699d7c8378)



## Features
- **Parallel Data Loading**: Simultaneous processing of orders and products data
- **PostgreSQL-MongoDB Integration**: Relational to document database synchronization
- **Scheduled Trigger**: Conditional execution based on PostgreSQL table changes
- **Idempotent Operations**: Automatic table cleanup before data insertion

## Prerequisites
- [Kestra](https://kestra.io) instance (v0.15.0+)
- PostgreSQL database
- MongoDB instance
- Kestra plugins:
  - JDBC PostgreSQL plugin
  - MongoDB plugin
  - Core plugins
 
![image (1) (1)](https://github.com/user-attachments/assets/e81f4c19-a9e7-4fa4-8079-37eab1e881d0)

## Configuration
Replace these template variables in `load_order_details_to_mongo.yaml`:
```yaml
# PostgreSQL Configuration
{{url}}          # PostgreSQL JDBC URL (e.g., jdbc:postgresql://localhost:5432/orders)
{{username}}     # PostgreSQL username
{{password}}     # PostgreSQL password

# MongoDB Configuration
{{mongo_url}}    # MongoDB connection string (e.g., mongodb://user:pass@localhost:27017)
{{db_name}}      # MongoDB database name

'''


