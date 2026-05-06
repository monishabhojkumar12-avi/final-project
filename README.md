# 🧠 Time-Based Browsing Pattern Analyzer using Deep Learning with RAM Usage Correlation

## 📌 Project Overview

This project builds an AI-driven system to analyze user browsing behavior over selectable time windows (3/4/5 days). It identifies patterns, clusters sessions, predicts future behavior using deep learning, and correlates browsing activity with system RAM usage.

The goal is to provide **behavior insights, performance optimization, and actionable recommendations** while ensuring privacy-safe processing.

---

## 🎯 Problem Statement

Analyze browsing history to:

* Detect time-based browsing patterns (hour/day/session)
* Identify dominant website categories (social, learning, shopping, etc.)
* Cluster user behavior into meaningful session types
* Predict next browsing category OR detect anomalous sessions
* Correlate browsing activity with RAM usage
* Generate actionable recommendations

---

## 🚀 Features

* 📊 Time-based behavior analysis (hourly, daily)
* 🔗 Sessionization of browsing activity
* 🧠 Unsupervised clustering (KMeans / GMM / DBSCAN)
* 🤖 Deep learning (LSTM / GRU / Autoencoder)
* 💻 RAM usage correlation (system + browser)
* 📈 Recommendation engine
* 📊 Optional dashboard (Streamlit)

---

## 🧰 Tech Stack

* Python, Pandas, NumPy
* SQLite (browser history extraction)
* scikit-learn (clustering, metrics)
* TensorFlow / Keras (LSTM, Autoencoder)
* psutil (RAM monitoring)
* Matplotlib / Seaborn (visualization)
* Streamlit (optional dashboard)

---

## 📂 Project Structure

```
├── data/
│   ├── raw/
│   ├── processed/
├── notebooks/
├── models/
├── src/
│   ├── data_collection.py
│   ├── preprocessing.py
│   ├── sessionization.py
│   ├── clustering.py
│   ├── lstm_model.py
│   ├── anomaly_detection.py
│   ├── ram_analysis.py
│   ├── recommendation_engine.py
├── app/ (optional Streamlit dashboard)
├── README.md
```

---

## ⚙️ Workflow

### 1️⃣ Data Collection

* Extract browsing history from browser SQLite DB (Chrome/Edge)
* Log RAM usage using `psutil` (every 5–10 seconds)

---

### 2️⃣ Data Preprocessing

* Clean URLs → extract domain
* Remove sensitive query strings
* Map domains to categories
* Generate time features (hour, date, day)

---

### 3️⃣ Sessionization

* Create sessions using inactivity threshold (e.g., 15 minutes)
* Generate session-level features:

  * number of events
  * category ratios
  * switching behavior

---

### 4️⃣ RAM Correlation

* Align browsing events with RAM logs (nearest timestamp join)
* Compute:

  * mean RAM per session
  * peak RAM usage

---

### 5️⃣ Clustering (Unsupervised Learning)

* Apply:

  * KMeans / GMM / DBSCAN
* Evaluate using:

  * Silhouette Score
* Interpret clusters (e.g., "Late-night social browsing")

---

### 6️⃣ Deep Learning

#### Option A: LSTM / GRU

* Input: category sequences
* Output: next category prediction
* Metrics:

  * Accuracy
  * Macro F1-score
  * Confusion Matrix
  * Baseline comparison

#### Option B: Autoencoder

* Input: session features
* Output: anomaly score
* Identify unusual sessions

---

### 7️⃣ Recommendation Engine

Generate insights such as:

* Reduce social media usage after 10 PM
* Close memory-heavy tabs
* Optimize browsing during peak productivity hours

---

## 📊 Results

* Top websites/domains for selected time window
* Hourly & daily usage patterns
* Behavior clusters with labels
* RAM usage insights (memory-heavy categories)
* Deep learning predictions or anomaly detection
* Actionable recommendations

---

## 📈 Evaluation Metrics

### Data Pipeline

* Extraction completeness
* URL parsing accuracy
* Sessionization correctness

### Clustering

* Silhouette Score
* Cluster interpretability

### Deep Learning (LSTM)

* Accuracy
* Macro F1-score
* Confusion Matrix
* Baseline comparison

### Autoencoder

* Reconstruction error
* Explainable anomalies

### RAM Analysis

* Category-wise RAM comparison
* Identification of top memory-heavy domains

---

## 💡 Use Cases

* 🧑‍💼 Employee productivity analytics
* 🌙 Digital wellbeing monitoring
* 💻 System performance optimization
* 🔐 Behavioral anomaly detection
* 🎓 Learning pattern analysis

---

## 🔒 Privacy & Ethics

* No sensitive URL data stored
* Only domain/category-level analysis
* Local data processing (no external sharing)

---

## 📦 Dataset

* Self-generated dataset from local machine
* Includes:

  * Browser history logs
  * RAM usage logs

---

## 📌 Future Improvements

* Real-time monitoring system
* Advanced attention-based models
* Cross-device behavior tracking
* Personalized recommendation engine

---

## 🙌 Acknowledgements

This project combines concepts from:

* Behavior Analytics
* Time Series Modeling
* Deep Learning
* System Monitoring

---
