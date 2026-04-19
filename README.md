# Climate Saathi: Early Warning Platform for Climate Resilience

[cite_start]Climate Saathi is a modular, cloud-backed IoT and Machine Learning platform designed to monitor, predict, and issue early warnings for climate-related service disruptions at government schools and Primary Health Centres (PHCs)[cite: 69]. [cite_start]The platform transforms reactive crisis management into proactive resilience by generating real-time risk scores, digital twins, and multi-channel early warnings[cite: 6, 62].

## Problem Statement
[cite_start]India ranks 26th on UNICEF's Children's Climate Risk Index (extremely high risk) due to compound threats like water scarcity, floods, and heatwaves[cite: 4]. [cite_start]These threats cause frequent disruptions in public infrastructure, such as pump failures, contaminated water, and heat-related cold-chain breaks, which harm communities without prior warning[cite: 5].

## Key Features
* [cite_start]**7–14 Days Predictive Horizon:** Anticipates water shortages, sanitation overflows, and power failures up to two weeks in advance[cite: 2, 72].
* [cite_start]**Facility Digital Twin:** Provides a live, queryable UI with sensor widgets, 14-day prediction overlays, alert logs, and scenario simulations[cite: 34].
* [cite_start]**Multi-Hazard Coverage:** Monitors water, sanitation, energy, heatwave, flood, and cold-chain risks within a single unified platform[cite: 60].
* [cite_start]**Explainable AI:** Incorporates SHAP-based explanations for model outputs to ensure field officials understand the driving factors behind risk scores[cite: 75].
* [cite_start]**Multi-Channel Alerts:** Delivers automated, deduplicated early warnings via SMS, WhatsApp, In-App push, and localized IVR[cite: 31, 151, 158].

## Technical Architecture
[cite_start]The system is built on a tightly integrated five-layer architecture[cite: 81]:
1.  [cite_start]**Edge / Ingestion:** Uses solar-charged ESP32 sensor nodes connected via LoRaWAN (The Things Stack/ChirpStack) or Bluetooth fallback[cite: 83, 88].
2.  [cite_start]**Data Store:** Utilizes TimescaleDB for time-series sensor data and PostgreSQL for facility master data, configurations, and metadata[cite: 83].
3.  [cite_start]**Analytics:** Orchestrates daily/hourly ETL pipelines using Apache Airflow to ingest external data from IMD, NASA POWER, NASA FIRMS, and CGWB[cite: 83, 112].
4.  [cite_start]**Application:** Features FastAPI-based microservices for risk scoring, forecasting, anomaly detection, and a Digital Twin Engine[cite: 83].
5.  [cite_start]**Presentation:** A React/Vite web application for state/district dashboards and a Streamlit app for the prototype[cite: 83, 162].

## Predictive Engine (Machine Learning)
* [cite_start]**Multi-Label Risk Scorer (LightGBM):** Predicts simultaneous binary risk labels (water, sanitation, energy, disease) per facility over a 7–14 day horizon[cite: 122, 123].
* [cite_start]**Water Level Forecaster (PyTorch LSTM):** Forecasts tank and groundwater levels 14 days ahead, producing continuous trajectories[cite: 130, 131].
* [cite_start]**PV Output Anomaly Detector:** Identifies solar under-performance by comparing expected output (calculated via a single-diode physics model) against actual sensor data[cite: 134, 135].

## Impact Targets
* [cite_start]Achieve a >90% target alert specificity[cite: 2].
* [cite_start]Reduce unplanned service disruptions by 40%[cite: 11].
* [cite_start]Provide 48+ hours of advance warning for critical water issues[cite: 54].

---

**Climate Saathi - IoT & AI Early Warning Platform**
*Mar 2026 – Apr 2026*
* [cite_start]Engineered a cloud-backed IoT and Machine Learning platform integrating hardware sensor data with open climate datasets (IMD, NASA POWER) to predict service disruptions at schools and health centres[cite: 6, 69].
* [cite_start]Developed a 3-tier predictive engine featuring a LightGBM Multi-Label Risk Scorer, a PyTorch LSTM Water Level Forecaster, and a physics-informed PV Anomaly Detector to generate a 7–14 day early warning horizon[cite: 122, 131, 134].
* [cite_start]Architected an automated data pipeline using Apache Airflow to orchestrate ETL tasks, processing APIs and MQTT streams into a TimescaleDB time-series and PostgreSQL relational database[cite: 102, 105, 112].
* [cite_start]Built an interactive Streamlit digital twin dashboard featuring interactive maps, 14-day forecast charts, SHAP-based model explainability, and multi-channel simulated alert queues (SMS/IVR)[cite: 47, 189, 190].
* [cite_start]Implemented deterministic 3-level decision fusion logic combining sensor streams, domain features, and external hazard layers to suppress false positives and target >90% alert specificity[cite: 2, 139, 141].
