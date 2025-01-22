# ETL-Pipeline-with-Kestra
Automated ETL pipeline using Kestra that:
1️⃣ Parallel-loads orders/products CSV data into PostgreSQL 
2️⃣ Joins relational data
3️⃣ Syncs results to MongoDB 
4️⃣ Triggers via PostgreSQL table changes (30s polling) Key Features: Idempotent design • Cross-DB sync • Self-cleaning triggers • Bulk operations.

![Pipeline]([https://datavidhya-static-content.s3.ap-south-1.amazonaws.com/architecture/DataVidhya+Projects+(1)_page-0001.jpg](https://drive.google.com/file/d/1WTH_Sq8nBIoGEzAOD8hxIfsVFEGKatm3/view?usp=sharing))
# Order Details ETL Pipeline with Kestra

This workflow loads order data from CSV sources into PostgreSQL, joins it with product data, and transfers the combined results to MongoDB. It includes automatic triggering based on PostgreSQL conditions.

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
