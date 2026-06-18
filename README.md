# Real-Time Stock Market Data Pipeline

## Overview

This project implements an end-to-end real-time stock market data pipeline using a modern data engineering stack. Live stock market data is collected from the Finnhub API, streamed through Apache Kafka, stored in MinIO object storage, transformed and modeled using DBT and Snowflake, and finally visualized through interactive Power BI dashboards.

The project demonstrates the complete lifecycle of real-time data processing, from ingestion to analytics-ready reporting.

---

## Project Objectives

- Collect live stock market data from an external API
- Stream data in real time using Apache Kafka
- Store raw data in object storage (MinIO)
- Build a scalable cloud data warehouse using Snowflake
- Transform and model data using DBT
- Implement a Medallion Architecture (Bronze, Silver, Gold)
- Create business-ready dashboards using Power BI

---

## Architecture

```text
Finnhub API
     │
     ▼
Python Producer
     │
     ▼
Apache Kafka
     │
     ▼
Python Consumer
     │
     ▼
MinIO (Raw JSON Storage)
     │
     ▼
Snowflake Data Warehouse
     │
     ▼
DBT Transformations
(Bronze → Silver → Gold)
     │
     ▼
Power BI Dashboard
```

---

## Technologies Used

| Technology | Purpose |
|------------|----------|
| Python | Data ingestion and streaming |
| Apache Kafka | Real-time message streaming |
| MinIO | Object storage for raw data |
| Snowflake | Cloud data warehouse |
| DBT | Data transformation and modeling |
| Apache Airflow | Workflow orchestration |
| Power BI | Data visualization |
| Docker | Infrastructure management |

---

## Data Source

The project uses the Finnhub Stock Market API to retrieve real-time stock market information.

Tracked stock symbols:

- AAPL (Apple)
- GOOGL (Google)
- MSFT (Microsoft)
- AMZN (Amazon)
- TSLA (Tesla)

---

## Pipeline Components

### 1. Data Ingestion

A Python producer continuously requests stock quotes from the Finnhub API and publishes them to a Kafka topic.

Features:

- Real-time API integration
- JSON serialization
- Continuous streaming

### 2. Real-Time Streaming

Apache Kafka acts as the central messaging system that enables scalable and reliable data streaming between services.

Features:

- Decoupled architecture
- Real-time message processing
- Scalable streaming pipeline

### 3. Raw Data Storage

A Kafka consumer reads messages and stores each record as a JSON file in MinIO object storage.

Features:

- Raw data persistence
- Data lake architecture
- Historical record storage

### 4. Data Warehouse

Snowflake is used as the central data warehouse for storing and managing stock market data.

Features:

- Cloud-native architecture
- Scalable storage and compute
- SQL analytics support

---

## DBT Data Modeling

The project follows the Medallion Architecture approach.

### Bronze Layer

Raw stock data is parsed and loaded into structured tables.

Responsibilities:

- JSON parsing
- Data type conversion
- Initial standardization

### Silver Layer

Data quality improvements and cleaning operations.

Responsibilities:

- Null value handling
- Data validation
- Data formatting

### Gold Layer

Business-ready datasets optimized for analytics.

Responsibilities:

- KPI calculations
- Volatility analysis
- Trend analysis
- Candlestick metrics

---

## Analytics and KPIs

The project generates several analytical metrics:

### Stock Price Analysis

- Average Open Price
- Average Close Price
- Average High Price
- Average Low Price

### Volatility Analysis

Measures stock risk using standard deviation calculations.

### Daily Change Analysis

Tracks percentage gains and losses for each stock.

### Trend Analysis

Monitors stock price behavior over time.

---

## Dashboard Features

Power BI dashboards provide:

- Interactive stock filtering
- Price trend visualization
- Risk (volatility) comparison
- Daily percentage change analysis
- KPI summary cards
- Historical stock performance

---


## Example Workflow

1. Producer fetches stock quotes from Finnhub.
2. Data is published to Kafka.
3. Consumer reads Kafka messages.
4. Raw JSON files are stored in MinIO.
5. Snowflake loads raw data.
6. DBT transforms data through Bronze, Silver, and Gold layers.
7. Power BI consumes Gold-layer tables for visualization.

---

## Key Features

- Real-time stock data ingestion
- Kafka-based streaming architecture
- Data lake storage with MinIO
- Snowflake cloud data warehouse
- DBT transformation pipeline
- Medallion Architecture
- Interactive Power BI dashboards
- End-to-end modern data engineering workflow

---

## Future Improvements

Potential enhancements include:

- Spark Streaming integration
- Machine learning-based stock forecasting
- Real-time alerting system
- Additional financial indicators
- Cloud deployment on AWS or Azure
- CI/CD automation

---

## Learning Outcomes

This project provided hands-on experience with:

- Real-time data engineering
- Event-driven architectures
- Data warehousing
- Data modeling with DBT
- Workflow orchestration
- Business intelligence and reporting
