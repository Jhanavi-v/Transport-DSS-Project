# Decision Support System  for Dynamic Public Transport Planning During Major Events in Berlin

**Team Members:** Jhanavi Venkatesh, Sahil Santosh Dangat, Yansong Xie, Het Nimeshkumar modi, Pradeep Singh Yadav
**Course:** Descision Support system 

## 📌 Project Overview
This project is a Decision Support System (DSS) designed to optimize public transport during major events (concerts, sports games, festivals). By leveraging **Machine Learning (LSTM)**, the system predicts passenger surges 24 hours in advance and automatically recommends:
1.  **Dynamic Pricing:** Adjusting fares to manage demand.
2.  **Route Optimization:** Allocating extra buses to critical routes.

## 📂 Repository Structure
* `data/` - Contains raw ridership logs, weather data, and the simulation output (`final_dashboard_data.csv`).
* `models/` - Contains the trained LSTM Neural Network (`lstm_demand_model.h5`).
* `scripts/` - Logic modules for Pricing Strategy and Route Optimization.
* `main_pipeline.py` - The integration script that runs the simulation.

## ⚙️ Installation & Setup
1.  **Clone the repository:**
    ```bash
    git clone [https://github.com/YOUR_USERNAME/Transport-DSS-Project.git](https://github.com/YOUR_USERNAME/Transport-DSS-Project.git)
    cd Transport-DSS-Project
    ```

2.  **Install dependencies:**
    ```bash
    pip install pandas numpy tensorflow scikit-learn
    ```
    *(Note: Mac M-Series users require `tensorflow-macos` and `tensorflow-metal`)*

## 🚀 How to Run the Demo
This system uses a **Python Backend** . 

**Step 1: Generate the Prediction**
Run the main pipeline to simulate a specific scenario (e.g., a stormy concert night).
```bash
python main_pipeline.py
