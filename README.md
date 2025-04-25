# 🚀 Application Monitoring Dashboard

A real-time log analytics and monitoring system using **Apache Kafka**, **Prometheus**, **Grafana**, and **PostgreSQL**. This platform captures simulated API traffic, processes logs, and visualizes insights through Grafana dashboards.

---

## 📁 Project Structure

```
Application-Monitoring-Dashboard/
├── api/                # API service (simulated endpoints)
├── grafana/            # Grafana config & dashboards
├── kafka-consumer/     # Consumes logs and stores in DB
├── kafka-producer/     # Produces log events to Kafka
├── load-generator/     # Sends fake traffic to the API
├── log-viewer-cli/     # CLI to inspect stored logs
├── prometheus/         # Prometheus config for scraping metrics
├── docker-compose/     # docker-compose.yml file for the stack
```

---

## 🔌 Tech Stack

- **Kafka** – Message broker for event streaming  
- **PostgreSQL** – Stores processed logs  
- **Grafana** – Dashboard for metrics & logs  
- **Prometheus** – Monitoring and scraping metrics  
- **Docker Compose** – For easy setup and deployment

---

## 🧪 Getting Started

### 1. Clone the Repository

```bash
git clone https://github.com/aruk04/Application-Monitoring-Dashboard.git
cd Application-Monitoring-Dashboard
```

### 2. Start All Services

```bash
docker-compose -f docker-compose/docker-compose.yml up --build
```

---

## 📈 Accessing Grafana

- Navigate to: [http://localhost:3000](http://localhost:3000)  
- Default Login:  
  - **Username:** `admin`  
  - **Password:** `admin`

---

## 🔎 Example SQL Query for Dashboard

```sql
SELECT
  timestamp AS "time",
  COUNT(*) AS "Total Logs"
FROM logs
GROUP BY timestamp
ORDER BY timestamp;
```

---

## ⚙️ Environment Overview

- Kafka handles log streaming between producer and consumer.
- Consumer writes logs into PostgreSQL.
- Prometheus scrapes metrics.
- Grafana visualizes data from PostgreSQL and Prometheus.

---

