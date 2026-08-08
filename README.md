# realtime-data-pipeline-kafka-airflow-spark

Real-time data pipeline ingesting streaming events with Kafka, orchestrated by Airflow, transformed with Spark, and served from a PostgreSQL warehouse. Built for scalable, production-style batch + streaming analytics.

## Architecture

```
Data Sources → Kafka → Spark Streaming → PostgreSQL Warehouse
                    ↑
               Airflow (Orchestration)
```

## Tech Stack

- **Apache Kafka** - Message broker for streaming ingestion
- **Apache Airflow** - Workflow orchestration & scheduling
- **Apache Spark (PySpark)** - Stream & batch processing
- **PostgreSQL** - Analytical data warehouse
- **Faker** - Synthetic data generation for testing

## Project Structure

```
├── dags/                 # Airflow DAGs (to be added)
├── spark/jobs/           # Spark streaming/batch jobs (to be added)
├── kafka/                # Kafka producer/consumer code (to be added)
├── postgres/             # Database schema & migrations
├── config/               # Configuration files (to be added)
├── tests/                # Unit & integration tests (to be added)
├── docker-compose.yml    # Container orchestration
├── requirements.txt      # Python dependencies
└── README.md             # This file
```

## Getting Started

```bash
# Start all services
docker-compose up -d

# Access Airflow UI
# http://localhost:8080

# Access Kafka UI (if enabled)
# http://localhost:8081
```

## Pipeline Flow

1. **Generate** - Faker produces synthetic events → Kafka topics
2. **Ingest** - Spark Structured Streaming reads from Kafka → Bronze layer
3. **Transform** - Spark jobs process Bronze → Silver → Gold layers
4. **Orchestrate** - Airflow DAGs schedule and monitor all jobs
5. **Serve** - PostgreSQL warehouse exposes Gold tables for analytics

## CI/CD

GitHub Actions workflow configured in `.github/workflows/ci.yml`

## License

MIT