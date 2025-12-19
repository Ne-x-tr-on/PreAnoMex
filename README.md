# PreAnoMex

**PreAnoMex** – *Preventive Anomaly Monitoring for Industrial Systems*

PreAnoMex is an **industrial anomaly detection API** designed to monitor automated systems, detect early signs of mechanical and electrical faults, and enable predictive maintenance. It was initially developed and tested using sensor data from automated conveyor systems, making it a **practical, industry-grounded solution**.

---

## Features

- **Real-Time Anomaly Detection:** Continuously monitors machine sensor data for unusual patterns.
- **Predictive Maintenance:** Flags potential failures before they happen to reduce downtime.
- **Industrial Focus:** Designed for conveyor systems, motors, pumps, and other electromechanical equipment.
- **Multi-Sensor Support:** Handles vibration, temperature, current, speed, and other sensor inputs.
- **API-First Design:** Easy to integrate with existing industrial software and dashboards.
- **Scalable & Extensible:** Can be adapted for multiple machines or production lines.

---

## Architecture

PreAnoMex follows a modular architecture:

1. **Data Collection Layer**
   - Collects sensor data from PLCs, Arduino, IoT gateways, or industrial sensors.
   - Supports time-series data storage (e.g., InfluxDB, TimescaleDB).

2. **Analysis Layer**
   - Statistical anomaly detection (thresholds, rolling mean, standard deviation).
   - Machine Learning models (Isolation Forest, Autoencoders, LSTM) for predictive insights.

3. **API Layer**
   - RESTful endpoints for anomaly detection, health checks, and data ingestion.
   - Example endpoints:
     - `POST /api/v1/analyze` – Submit sensor data for anomaly analysis
     - `GET /api/v1/health` – Check system status
     - `POST /api/v1/train-baseline` – Train the model on new normal data

4. **Notification / Dashboard Layer**
   - Provides alerts for detected anomalies
   - Optional integration with dashboards for monitoring

---

## Installation

```bash
# Clone the repository
git clone https://github.com/yourusername/preanomex.git

# Navigate to project folder
cd preanomex

# Install dependencies (Python example)
pip install -r requirements.txt

# Start API server
uvicorn preanomex.main:app --reload
