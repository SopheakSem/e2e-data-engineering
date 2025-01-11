# Realtime Data Streaming | End-to-End Data Engineering Project

## Table of Contents
- [Introduction](#introduction)
- [System Architecture](#system-architecture)
- [What You'll Learn](#what-youll-learn)
- [Technologies](#technologies)
- [Getting Started](#getting-started)
- [Watch the Video Tutorial](#watch-the-video-tutorial)

## Introduction

This project serves as a comprehensive guide to building an end-to-end data engineering pipeline. It covers each stage from data ingestion to processing and finally to storage, utilizing a robust tech stack that includes Apache Airflow, Python, Apache Kafka, Apache Zookeeper, Apache Spark, and Cassandra. Everything is containerized using Docker for ease of deployment and scalability.

## System Architecture

![System Architecture](https://github.com/airscholar/e2e-data-engineering/blob/main/Data%20engineering%20architecture.png)

The project is designed with the following components:

- **Data Source**: We use `randomuser.me` API to generate random user data for our pipeline.
- **Apache Airflow**: Responsible for orchestrating the pipeline and storing fetched data in a PostgreSQL database.
- **Apache Kafka and Zookeeper**: Used for streaming data from PostgreSQL to the processing engine.
- **Control Center and Schema Registry**: Helps in monitoring and schema management of our Kafka streams.
- **Apache Spark**: For data processing with its master and worker nodes.
- **Cassandra**: Where the processed data will be stored.

## What You'll Learn

- Setting up a data pipeline with Apache Airflow
- Real-time data streaming with Apache Kafka
- Distributed synchronization with Apache Zookeeper
- Data processing techniques with Apache Spark
- Data storage solutions with Cassandra and PostgreSQL
- Containerizing your entire data engineering setup with Docker

## Technologies

- Apache Airflow
- Python
- Apache Kafka
- Apache Zookeeper
- Apache Spark
- Cassandra
- PostgreSQL
- Docker

## Getting Started

1. Set up ENV
    python3 -m venv myenv                                       
    source myenv/bin/activate
    pip install kafka-python apache-airflow pyspark

2. Clone the repository:
    ```bash
    git clone https://github.com/airscholar/e2e-data-engineering.git
    ```

3. Navigate to the project directory:
    ```bash
    cd e2e-data-engineering
    ```

4. Run Docker Compose to spin up the services:
    ```bash
    docker compose up -d
    ```
5. secret key Same
    1. schedule 
        secret_key = EKDzN+fbjb9j/K/MFVa6IA==
    2. Webserver
        secret_key = GWq3I6xq/SCSBfkUWRyvfQ==

6. Submit Spark
    spark-submit --master spark://localhost:7077 spark_stream.py

7. Verify cassandra
    
    docker exec -it cassandra cqlsh -u cassandra -p cassandra localhost 9042

    select * from spark_streams.created_users

For more detailed instructions, please check out the video tutorial linked below.

## Watch the Video Tutorial

For a complete walkthrough and practical demonstration, check out our [YouTube Video Tutorial](https://www.youtube.com/watch?v=GqAcTrqKcrY).
