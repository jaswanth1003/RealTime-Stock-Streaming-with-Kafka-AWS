# RealTime-Stock-Streaming-with-Kafka-AWS

# Project Overview

This project implements a real-time stock market data pipeline that ingests, processes, and analyzes over 1 million stock market records using:

- **Kafka** for real-time streaming

-  **AWS S3** for scalable storage

-  **AWS Glue** for ETL processing

-  **AWS Athena** for SQL-based querying and analytics

-  **IAM Roles** for secure access control

The pipeline is designed to achieve 99.9% uptime, ensuring minimal latency and high scalability for real-time financial data processing.

# Architecture Workflow

![image](https://github.com/user-attachments/assets/a23c6657-4f2f-46c0-9351-859e44a66d27)


**System Components**

1. **Data Ingestion - Kafka Producer**

- A Python-based stock market simulator reads stock data from a CSV dataset.
 
- The Kafka producer publishes stock data in real-time (1,000+ records/second) to a Kafka topic.

- The Kafka broker is hosted on AWS EC2, ensuring high availability and fault tolerance.

2. **Data Storage - AWS S3**

- The Kafka consumer processes incoming stock data and writes it to Amazon S3 .

-  Data is structured and partitioned by timestamp and stock symbol for optimized querying.

![image](https://github.com/user-attachments/assets/882614fa-5fb1-4d10-ad33-ed09d833ad0b)

3. **Data Processing - AWS Glue & AWS Glue Data Catalog**

- AWS Glue Crawler scans and registers 1 M+ records daily in the Glue Data Catalog.

![image](https://github.com/user-attachments/assets/5ce85549-cb28-4a27-a3d6-d8ae6ceb7d46)

# IAM Roles & Permissions

# IAM Policies Used

-  **Kafka Broker IAM Role** - Grants access to read stock data from the dataset.

-  **S3 Access Role** - Allows the Kafka consumer to write data to S3.

- **AWS Glue Role** - Enables Glue ETL jobs to read/write data from S3 and the Glue Data Catalog.

-  **Athena Query Role** - Allows Athena to access Glue tables and S3 data. 

# Solution Highlights

- **Real-time Stock Data Processing**: Streams stock market data using Kafka and AWS services.

- **Scalable Storage with AWS S3**: Stores structured and partitioned stock data for efficient access.

- **Faster Query Execution**: Uses AWS Athena to analyze stock market trends with SQL queries.

- **Secure IAM Role Management**: Ensures restricted access to Kafka, S3, Glue, and Athena.

- **Optimized Data Flow**: Provides a structured pipeline for reliable and scalable data processing.

- **Extensible Architecture**: Can be integrated with AI/ML models for predictive analytics.

This solution focuses on real-time stock data streaming using Kafka, ensuring efficient ingestion, storage, and organization with AWS services for scalable and reliable data processing.




  
