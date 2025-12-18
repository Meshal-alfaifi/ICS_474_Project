# 🚦 FlowSight: Real-Time Traffic Analytics Pipeline

![Python](https://img.shields.io/badge/Python-3.8%2B-blue)
![Spark](https://img.shields.io/badge/Apache%20Spark-3.5-orange)
![Kafka](https://img.shields.io/badge/Apache%20Kafka-Streaming-black)
![Streamlit](https://img.shields.io/badge/Streamlit-Dashboard-red)
![Status](https://img.shields.io/badge/Status-Completed-success)

> **Course Project:** ICS 474 - Big Data Analytics  
> **Option 1:** Rebuild & Optimize an Existing Open-Source Project  
> **Environment:** Google Colab (Cloud-Native)

---

## 📖 Overview

**FlowSight** is an end-to-end Big Data pipeline designed to simulate, process, and visualize real-time traffic data in a Smart City context. 

Unlike traditional static datasets, FlowSight handles continuous data streams. It simulates IoT sensors generating high-velocity traffic data (Speed, Vehicle Count, Temperature) and processes them using the **Lambda Architecture** principles. The system ensures zero data loss via a **Hybrid Storage Strategy** and utilizes Machine Learning to predict future congestion.

---

## 🏗️ Architecture

The pipeline is built entirely within a Python environment, orchestrating distributed systems dynamically.

1.  **Ingestion Layer:** Python-based simulator generating IoT sensor data.
2.  **Messaging Layer:** **Apache Kafka** & Zookeeper for high-throughput buffering.
3.  **Storage Layer (Dual-Write):**
    * **Hot Path:** **PostgreSQL** for real-time dashboard queries.
    * **Cold Path:** **Parquet Data Lake** for historical batch analysis.
4.  **Processing Layer:** **PySpark** performing windowed aggregations (1-minute tumbling windows).
5.  **Smart Layer (AI):** **Random Forest Regressor** (Scikit-Learn) for congestion prediction.
6.  **Presentation Layer:** **Streamlit** dashboard with **PyDeck** 3D geospatial visualization.

---

## 🚀 Key Features

* **☁️ Cloud-Native Deployment:** Fully scriptable infrastructure that provisions Java, Kafka, and Postgres in a Google Colab ephemeral environment.
* **⚡ Real-Time Streaming:** Sub-second latency from data generation to visualization.
* **🧠 AI "Smart Layer":** Integrated Machine Learning model that predicts traffic speed based on environmental factors (Temperature & Density).
* **📊 3D Geospatial Dashboard:** Interactive map visualizing traffic intensity using 3D column layers.
* **💾 Hybrid Storage:** Demonstrates "Polyglot Persistence" by combining SQL (Relational) and Parquet (Columnar) storage.

---

## 🛠️ Tech Stack

| Component | Technology | Description |
| :--- | :--- | :--- |
| **Language** | Python 3.10 | Core logic and scripting |
| **Streaming** | Apache Kafka | Message broker for decoupling |
| **Processing** | PySpark | Distributed batch processing & aggregation |
| **Database** | PostgreSQL | Relational storage for live app data |
| **Data Lake** | Parquet | Columnar storage for historical analysis |
| **ML** | Scikit-Learn | Random Forest for speed prediction |
| **UI/Web** | Streamlit | Interactive dashboard frontend |
| **Tunneling** | Ngrok | Exposing local ports to the public web |

---

## ⚙️ How to Run

Since this project uses Google Colab, no local installation is required.

1.  **Open the Notebook:**
    Upload the `FlowSight_Project.ipynb` file to Google Colab.

2.  **Step 1: Install Infrastructure**
    Run **Cell 1** to install Java, PostgreSQL, and Kafka. Wait for the success message: `✅ Infrastructure Setup Complete`.

3.  **Step 2: Start Pipeline**
    Run **Cell 2**. This will start the simulation loop.
    * *Note:* This cell runs indefinitely. **Stop it manually** after ~60 seconds to generate a batch of data.

4.  **Step 3: Process Data**
    Run **Cell 2B** to trigger the Spark Aggregation job on the generated Parquet files.

5.  **Step 4: Train AI**
    Run **Cell 3** to train the Random Forest model on the PostgreSQL data.

6.  **Step 5: Launch Dashboard**
    Run **Cell 4** & **Cell 5**.
    * Copy the **Ngrok URL** provided in the output (e.g., `http://xxxx-xx.ngrok-free.app`).
    * Paste it into your browser to view the live dashboard.

---

## 📸 Screenshots

### 1. The 3D Geospatial Dashboard
*Real-time visualization of traffic density using PyDeck.*
*(Add your screenshot here)*

### 2. AI Prediction Module
*Predicting traffic speed based on vehicle count and temperature.*
*(Add your screenshot here)*

---

## 📝 License

This project is intended for educational purposes as part of the ICS 474 course at KFUPM.
