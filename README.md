# 🚦 Decision Support System for Dynamic Public Transport Planning During Major Events in Berlin

**Team Members:**
Jhanavi Venkatesh, Sahil Santosh Dangat, Yansong Xie, Het Nimeshkumar Modi, Pradeep Singh Yadav

**Course:** Decision Support Systems

---

## 📌 Project Overview

This project presents a **Decision Support System (DSS)** designed to improve public transport planning during **major events in Berlin** (concerts, sports matches, festivals).

By combining **machine learning, pricing strategies, and optimization techniques**, the system predicts passenger demand **24 hours in advance** and converts these predictions into **actionable operational decisions**.

The DSS focuses on three core decision layers:

1. **Demand Forecasting (LSTM)** – Predict passenger surges
2. **Dynamic Pricing** – Adjust fares to influence demand
3. **Vehicle Allocation Optimization** – Reduce vehicles while meeting demand

---

## 🎯 Objectives

* Anticipate demand spikes during large-scale events
* Improve vehicle utilization efficiency
* Reduce operational costs
* Support data-driven decision-making for transport authorities

---

## 🧠 System Architecture

```
Historical Ridership + Weather + Event Data
                ↓
           LSTM Model
                ↓
       Predicted Passenger Demand
        ↓                 ↓
 Dynamic Pricing     Vehicle Allocation Optimization
        ↓                 ↓
        DSS Dashboard (Loooker Studio)
```

---

## 📂 Repository Structure

```
├── data/
│   ├── ridership.csv
│   ├── weather_data.csv
│   ├── transport_data.csv
│   ├── predicted_demand_output.csv
│   ├── dynamic_pricing_output.csv
│   └── vehicle_allocation_results.csv
│
├── models/
│   └── lstm_demand_model.h5
│
├── scripts/
│   ├── lstm_prediction.py
│   ├── dynamic_pricing.py
│   └── vehicle_optimization.py
│
├── main_pipeline.py
└── README.md
```

---

## ⚙️ Installation & Setup

### 1️⃣ Clone the repository

```bash
git clone https://github.com/YOUR_USERNAME/Transport-DSS-Project.git
cd Transport-DSS-Project
```

### 2️⃣ Install dependencies

```bash
pip install pandas numpy tensorflow scikit-learn matplotlib
```

> ⚠️ **Mac M-Series users:**
> Use `tensorflow-macos` and `tensorflow-metal`

---

## 🚀 How to Run the Demo

### Step 1: Generate Demand Forecast (LSTM)

```bash
python scripts/lstm_prediction.py
```

Generates:
`predicted_demand_output.csv`

---

### Step 2: Apply Dynamic Pricing

```bash
python scripts/dynamic_pricing.py
```

Pricing is computed using:

```
Dynamic_Price = Base_Price × (1 + α × (Predicted_Demand − Avg_Demand) / Avg_Demand)
```

Price bounds are enforced for realism.

Generates:
`dynamic_pricing_output.csv`

---

### Step 3: Optimize Vehicle Allocation  🚍 *(Optimization Module)*

```bash
python scripts/vehicle_optimization.py
```

---

## 🚍 Optimization Module – Vehicle Allocation

### Overview

This module converts **predicted passenger demand** into an **efficient vehicle deployment plan**, ensuring capacity constraints are respected while minimizing the number of vehicles used.

---

### Objective

* Minimize total vehicles required
* Respect fixed vehicle capacity (300 passengers)
* Compare baseline vs optimized allocation

---

### Input

* Predicted demand values from LSTM
* Vehicle capacity = **300 passengers**

Demand values exceeding capacity are **split into capacity-sized units** before allocation.

---

### Methodology

**Baseline Scenario**

* One vehicle per demand unit
* No consolidation
* Represents non-optimized planning

**Optimized Scenario**

* Greedy capacity-based allocation
* Vehicles are filled until capacity is reached
* New vehicle is assigned only when required

---

### Output

**`vehicle_allocation_results.csv`**

| Column                | Description            |
| --------------------- | ---------------------- |
| Vehicle_ID            | Vehicle identifier     |
| Assigned_Zones        | Demand units served    |
| Total_Load            | Passenger load         |
| Capacity_Used_Percent | Utilization percentage |

---

### Results

| Scenario           | Vehicles Used   |
| ------------------ | --------------- |
| Baseline           | 35              |
| Optimized          | 25              |
| **Vehicles Saved** | **10 (~28.5%)** |

---

### Impact

* Fewer vehicles deployed
* Higher capacity utilization
* Lower operational costs
* Clear decision support for planners

---

### Limitations

* No routing or geographic constraints
* Fixed vehicle capacity
* Planning-focused (not real-time dispatch)

---

## 📊 DSS Dashboard (Looker Studio)

A **single-page dashboard** visualizes:

* Actual vs Predicted Demand
* Dynamic Pricing response to demand
* Optimized vehicle utilization
* Vehicles saved through optimization

The dashboard connects directly to the generated CSV outputs.

---

## 📈 Key Takeaway

This DSS demonstrates how **AI-driven forecasting combined with optimization techniques** can transform raw data into **practical, cost-saving transport decisions** during major urban events.




