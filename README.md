# Real-Time Data Streaming

## 📑 Table of Contents

- [📖 Overview](#-overview)
- [🏗️ System Architecture](#️-system-architecture)
- [📂 Project Structure](#-project-structure)
- [🛠️ Technologies](#-technologies)
- [🚀 Getting Started](#-getting-started)


## 📖 Overview

This project demonstrates a real-time **ETL pipeline** that streams user data from an external API into **Apache Kafka**, processes the stream using **Apache Spark Structured Streaming**, and stores the processed data into **Apache Cassandra** for further querying. The entire workflow is orchestrated with **Apache Airflow** and containerized using **Docker** for easy deployment.


## 🏗️ System Architecture

![System Architecture](https://github.com/totan286/RealTimeStreaming/blob/main/System%20Architecture.png)

The project is designed with the following components:

- **Data Source**: `randomuser.me` API generates random user data.
- **Apache Airflow**: Orchestrates the pipeline and pushes data to Kafka.
- **Apache Kafka + Zookeeper**: Message broker for streaming events.
- **Schema Registry & Control Center**: Kafka ecosystem tools for schema management & monitoring.
- **Apache Spark**: Reads from Kafka, transforms JSON into structured DataFrame, writes to Cassandra.
- **Cassandra**: Storage layer for streaming data.
- **PostgreSQL** *(optional)*: Used by Airflow as metadata DB.


## 📂 Project Structure

```bash
.
├── dags/
│   └── kafka_stream.py    # Airflow DAG to push API data into Kafka
├── spark_stream.py        # Spark job: consume Kafka → transform → load Cassandra
├── requirements.txt       # Python dependencies
└── README.md              # Documentation
```

## 🛠️ Technologies

- Apache Airflow
- Python
- Apache Kafka
- Apache Zookeeper
- Apache Spark
- Cassandra
- PostgreSQL
- Docker

## 🚀 Getting Started
### Prerequisites

- **Docker Desktop**
- **Git** 

### Setup Instructions


1. Clone the repository:
    ```bash
    git clone https://github.com/totan286/RealTimeStreaming.git
    ```

2. Navigate to the project directory:
    ```bash
    cd RealTimeStreaming
    ```

3. Run Docker Compose to spin up the services:
    ```bash
    docker-compose up
    ```
