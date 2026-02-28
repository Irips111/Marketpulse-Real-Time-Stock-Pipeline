# Marketpulse-Real-Time-Stock-Pipeline
A scalable real-time data engineering pipeline for streaming, processing, and visualizing stock market data using Kafka, PySpark, PostgreSQL, and Power BI, with full monitoring and CI/CD support.


## Project Overview

This project was developed as an end-to-end data engineering case study focused on building a real-time stock market data pipeline for MarketPulse Analytics. The objective was to design a scalable and fault-tolerant streaming architecture capable of ingesting live stock market data, processing it in real time, storing it for analytics, and visualizing insights through interactive dashboards.

The project eliminates latency and reliability issues found in traditional batch systems by implementing a modern streaming pipeline using Apache Kafka and PySpark. It also incorporates system monitoring tools to ensure observability and operational stability.

This project demonstrates practical data engineering skills, including real-time data ingestion, stream processing, distributed computing, database integration, containerized infrastructure, CI/CD automation, and monitoring.

## Project Features
* Real-time stock market data ingestion using Alpha Vantage API
* Kafka-based streaming architecture for scalable data flow
* Distributed data processing using PySpark
* Historical data storage in PostgreSQL
* Interactive dashboards built with Power BI
* Containerized infrastructure using Docker and Docker Compose
* System monitoring with Prometheus and Grafana
* CI/CD automation using GitHub Actions
* Fault-tolerant and scalable architecture
* Reproducible project structure suitable for production-style deployment


## Troubleshooting & Common Errors
1. Kafka Broker Connection Errors
Issue: Producer or consumer unable to connect to Kafka.
Resolution: Verified Docker network configuration and ensured correct bootstrap-server settings.

2. Spark Streaming Failures
Issue: Spark consumer failed to process streaming data.
Resolution: Confirmed correct Kafka topic configuration and ensured Spark dependencies were properly installed.

3. PostgreSQL Connection Refused
Issue: Database connection failed during ingestion.
Resolution: Checked container readiness and verified environment variables for database credentials.

4. Data Latency
Issue: Delays during high-volume market periods.
Resolution: Optimized Kafka partitioning and improved Spark batch interval configurations.

5. Prometheus Metrics Not Displaying
Issue: No metrics visible in Grafana dashboards.
Resolution: Verified Prometheus scrape configuration and correct service endpoints.

## Project Files
producer/: Python scripts for API integration and Kafka producer logic
consumer/: PySpark streaming consumer and data transformation scripts
config/: Configuration files and environment variables
monitoring/: Prometheus and Grafana configuration files
docker-compose.yml: Docker orchestration for all services
requirements.txt: Python dependencies
.github/workflows/: GitHub Actions CI/CD configuration
README.md: Project documentation

## Designing and Implementing the Data Pipeline
To build a scalable real-time system, I began by integrating the Alpha Vantage API to stream live stock market data. I created a Python-based producer that publishes this data into Apache Kafka topics, forming a distributed streaming backbone. A PySpark consumer subscribes to Kafka topics and processes the data in real-time, applying transformations such as price change calculations, moving averages, and aggregations for analytical reporting. The processed data is stored in PostgreSQL to support historical analysis and dashboard visualization.

For observability and reliability, I hooked up Prometheus to collect system performance metrics from Kafka, Spark, and PostgreSQL. Grafana visualizes these metrics in real-time, enabling pipeline health monitoring. Power BI connects to PostgreSQL, delivering interactive dashboards that display real-time stock trends, volatility metrics, trading volume analysis, and portfolio performance indicators.

I containerized the entire infrastructure using Docker and orchestrated it with Docker Compose, ensuring portability, scalability, and consistent deployment environments. GitHub Actions automates testing and workflow validation, maintaining code quality and deployment consistency.

This project showcases the design and implementation of a production-style real-time data engineering pipeline.

##  How to Run This Project
1. Clone the repository
git clone https://github.com/your-username/marketpulse-real-time-stock-pipeline.git
cd marketpulse-real-time-stock-pipeline

2. Start services using Docker
docker compose up --build -d

3. Run the producer (if not containerized)
python producer/main.py

4. Run the consumer
python consumer/consumer.py

5. Access Monitoring Tools
   Prometheus → http://localhost:9090
   Grafana → http://localhost:3000

6. Connect Power BI
Connect Power BI to PostgreSQL using:
Host: localhost
Port: 5432 (or mapped port)
Database: stock_data
Username and password: defined in your .env file

## Data Source
Alpha Vantage API – Real-Time Stock Market Data

## Specialization
Data Engineering
Real-Time Streaming Systems
Distributed Processing
Monitoring & Observability
Financial Analytics

## License

This project is licensed under the MIT License.
