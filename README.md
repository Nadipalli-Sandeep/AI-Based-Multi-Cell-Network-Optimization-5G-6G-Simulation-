<div align="center">

```
███╗   ██╗███████╗████████╗ ██████╗ ██████╗ ████████╗
████╗  ██║██╔════╝╚══██╔══╝██╔═══██╗██╔══██╗╚══██╔══╝
██╔██╗ ██║█████╗     ██║   ██║   ██║██████╔╝   ██║   
██║╚██╗██║██╔══╝     ██║   ██║   ██║██╔═══╝    ██║   
██║ ╚████║███████╗   ██║   ╚██████╔╝██║        ██║   
╚═╝  ╚═══╝╚══════╝   ╚═╝    ╚═════╝ ╚═╝        ╚═╝   
```

# AI-Based Multi-Cell Network Optimizer

**Intelligent 5G/6G congestion control using machine learning — from 12 failure events to zero.**

[![Open in Colab](https://colab.research.google.com/assets/colab-badge.svg)](https://colab.research.google.com/drive/1dq8h6bBlYOMVn3pvw0RCdfJ1xS88mi4H?usp=sharing)
![Python](https://img.shields.io/badge/Python-3.8+-3776AB?style=flat&logo=python&logoColor=white)
![Scikit-learn](https://img.shields.io/badge/Scikit--learn-ML-F7931E?style=flat&logo=scikit-learn&logoColor=white)
![Status](https://img.shields.io/badge/Status-Production--Ready-brightgreen?style=flat)

</div>

---

## The Problem with Modern Wireless Networks

5G and 6G networks serve millions of simultaneous users — and they fail silently. Congestion builds up until latency spikes, QoS degrades, and users notice. Traditional rule-based systems react too late.

This project takes a different approach: **predict the congestion before it happens, then prevent it entirely.**

---

## Results at a Glance

| Metric | Before | After | Improvement |
|--------|--------|-------|-------------|
| Congestion Events | 12 | **0** | ✅ 100% eliminated |
| Latency (ms) | 96.04 | **69.90** | ⚡ ~27% faster |
| QoS Score | 0.88 | **1.00** | 📈 Perfect score |
| Energy Usage | High | **Reduced** | 🔋 Leaner operation |

> Optimized traffic stays continuously below the congestion threshold — no tuning, no manual intervention.

---

## How It Works

```
Raw Traffic Data
      │
      ▼
┌─────────────────────┐
│  Multi-Cell         │   Simulates N base stations (RAN)
│  Simulation Layer   │   Each cell generates distinct traffic patterns
└────────┬────────────┘
         │
         ▼
┌─────────────────────┐
│  Random Forest      │   Trained on historical traffic
│  Traffic Predictor  │   Outputs: predicted load per cell per timestep
└────────┬────────────┘
         │
         ▼
┌─────────────────────┐
│  Dynamic Congestion │   Threshold computed from traffic distribution
│  Detector           │   Flags cells approaching overload
└────────┬────────────┘
         │
         ▼
┌─────────────────────┐
│  Adaptive           │   Severity-weighted traffic reduction
│  Controller         │   No fixed rules — responds to predicted load
└────────┬────────────┘
         │
         ▼
┌─────────────────────┐
│  Load Balancer      │   Redistributes excess load across healthy cells
│                     │   Mimics real-world RAN scheduling strategies
└─────────────────────┘
```

---

## Architecture Deep Dive

### 1. Multi-Cell Simulation
Each simulated cell operates as an independent base station with slightly varied traffic patterns — modeling realistic distributed network behavior. This is the **RAN (Radio Access Network)** abstraction layer.

### 2. Traffic Prediction via Random Forest
The ML core uses a **Random Forest Regressor** — an ensemble of decision trees that captures non-linear traffic patterns without overfitting. Training data is historical traffic per cell; the model learns seasonal load patterns, peak periods, and cross-cell correlation.

```python
# Core prediction loop (simplified)
model = RandomForestRegressor(n_estimators=100)
model.fit(X_train, y_train)
predicted_traffic = model.predict(X_future)
```

### 3. Dynamic Threshold Detection
Instead of a fixed congestion threshold (which ignores traffic distribution shifts), this system computes thresholds **dynamically** from traffic statistics — more robust against changing network conditions.

### 4. Adaptive Optimization
Control actions are proportional to congestion severity — minor stress triggers minor corrections; severe overload triggers aggressive redistribution. This avoids the oscillation problems common in binary (on/off) control systems.

### 5. Load Balancing
Excess traffic from congested cells is redistributed to underutilized neighbors — exactly how commercial RAN orchestration works at scale.

---

## Visualizations

### Traffic Optimization
- 🔵 **Actual traffic** — raw observed load  
- 🟠 **Predicted traffic** — ML forecast  
- 🟢 **Optimized traffic** — post-control output  
- 🔴 **Congestion threshold** — the line that must not be crossed

![Traffic Optimization](images/traffic.png)

### Latency Improvement

Before-and-after comparison across simulation timesteps — the drop is sharp and sustained.

![Latency Improvement](images/latency.png)

---

## Real-World Mapping

| This Project | 5G/6G Reality |
|-------------|---------------|
| Simulated Cells | Base Stations (gNodeB) |
| Traffic Load | User plane data (eMBB, URLLC) |
| Prediction Model | AI-RAN inference engine |
| Adaptive Controller | Network slice scheduler |
| Load Balancer | Inter-cell interference coordination (ICIC) |
| QoS Score | E2E user experience KPI |

---

## Tech Stack

```
Python 3.8+
├── scikit-learn     → Random Forest model, MSE evaluation
├── numpy            → Traffic simulation, numerical ops
├── pandas           → Data pipeline, time-series windowing
└── matplotlib       → Visualization (traffic, latency plots)
```

---

## Getting Started

### Option 1: Google Colab (Zero Setup)

Click the badge at the top → Run All Cells → View results in ~60 seconds.

### Option 2: Local Setup

```bash
git clone https://github.com/your-username/your-repo-name.git
cd your-repo-name
pip install -r requirements.txt
jupyter notebook "AI-Based Network Congestion Control.ipynb"
```

---

## Why This Matters

The 5G/6G era isn't just about faster speeds — it's about networks that are **self-aware and self-healing**. This project demonstrates that:

- ML can predict congestion before users experience it
- Adaptive control outperforms static thresholds
- AI + systems engineering together solve problems neither can alone

These are the same architectural ideas behind production-grade **AI-RAN** systems being deployed by Nokia, Ericsson, and Samsung today.

---

## Author

**Jaya Sandeep Nadipalli**  
M.Tech — Data Science & AI, IIT Tirupati

📧 [nadipalli.sandeep8@gmail.com](mailto:nadipalli.sandeep8@gmail.com)  
🔗 [linkedin.com/in/jayasandeep](https://linkedin.com/in/jayasandeep)

---

<div align="center">
<sub>Built at the intersection of machine learning and systems engineering.</sub>
</div>
