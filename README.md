 Climate Saathi: Early Warning Platform for Climate Resilience

Climate Saathi is a modular, cloud-backed IoT and Machine Learning platform designed to monitor, predict, and issue early warnings for climate-related service disruptions at government schools and Primary Health Centres (PHCs): 69]. _start]The platform transforms reactive crisis management into proactive resilience by generating real-time risk scores, digital twins, and multi-channel early warnings: 6, 62].

## Problem Statement
India ranks 26th on UNICEF's Children's Climate Risk Index (extremely high risk) due to compound threats like water scarcity, floods, and heatwaves. These threats cause frequent disruptions in public infrastructure, such as pump failures, contaminated water, and heat-related cold-chain breaks, which harm communities without prior warning.

## Key Features
* **7–14 Days Predictive Horizon:** Anticipates water shortages, sanitation overflows, and power failures up to two weeks in advance: 2, 72].
* **Facility Digital Twin:** Provides a live, queryable UI with sensor widgets, 14-day prediction overlays, alert logs, and scenario simulations: 34].
* **Multi-Hazard Coverage:** Monitors water, sanitation, energy, heatwave, flood, and cold-chain risks within a single unified platform: 60].
* **Explainable AI:** Incorporates SHAP-based explanations for model outputs to ensure field officials understand the driving factors behind risk scores: 75].
* **Multi-Channel Alerts:** Delivers automated, deduplicated early warnings via SMS, WhatsApp, In-App push, and localized IVR: 31, 151, 158].

## Technical Architecture
The system is built on a tightly integrated five-layer architecture: 81]:
1. **Edge / Ingestion:** Uses solar-charged ESP32 sensor nodes connected via LoRaWAN (The Things Stack/ChirpStack) or Bluetooth fallback: 83, 88].
2. **Data Store:** Utilizes TimescaleDB for time-series sensor data and PostgreSQL for facility master data, configurations, and metadata: 83].
3. **Analytics:** Orchestrates daily/hourly ETL pipelines using Apache Airflow to ingest external data from IMD, NASA POWER, NASA FIRMS, and CGWB: 83, 112].
4.**Application:** Features FastAPI-based microservices for risk scoring, forecasting, anomaly detection, and a Digital Twin Engine: 83].
5.**Presentation:** A React/Vite web application for state/district dashboards and a Streamlit app for the prototype: 83, 162].

## Predictive Engine (Machine Learning)
* **Multi-Label Risk Scorer (LightGBM):** Predicts simultaneous binary risk labels (water, sanitation, energy, disease) per facility over a 7–14 day horizon: 122, 123].
* **Water Level Forecaster (PyTorch LSTM):** Forecasts tank and groundwater levels 14 days ahead, producing continuous trajectories.
* **PV Output Anomaly Detector:** Identifies solar under-performance by comparing expected output (calculated via a single-diode physics model) against actual sensor data.

## Impact Targets
* [_start]Achieve a >90% target alert specificity[: 2].
* [_start]Reduce unplanned service disruptions by 40%[: 11].
* _start]Provide 48+ hours of advance warning for critical water issues: 54].

---

**Climate Saathi - IoT & AI Early Warning Platform**
*Mar 2026 – Apr 2026*
* _start]Engineered a cloud-backed IoT and Machine Learning platform integrating hardware sensor data with open climate datasets (IMD, NASA POWER) to predict service disruptions at schools and health centres: 6, 69].
* _start]Developed a 3-tier predictive engine featuring a LightGBM Multi-Label Risk Scorer, a PyTorch LSTM Water Level Forecaster, and a physics-informed PV Anomaly Detector to generate a 7–14 day early warning horizon: 122, 131, 134].
* _start]Architected an automated data pipeline using Apache Airflow to orchestrate ETL tasks, processing APIs and MQTT streams into a TimescaleDB time-series and PostgreSQL relational database: 102, 105, 112].
* _start]Built an interactive Streamlit digital twin dashboard featuring interactive maps, 14-day forecast charts, SHAP-based model explainability, and multi-channel simulated alert queues (SMS/IVR): 47, 189, 190].
* _start]Implemented deterministic 3-level decision fusion logic combining sensor streams, domain features, and external hazard layers to suppress false positives and target >90% alert specificity: 2, 139, 141].
