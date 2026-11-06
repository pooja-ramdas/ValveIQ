# ValveIQ - Smart Pipeline Sentinel

**ValveIQ** is an AI-powered predictive fault detection and condition-monitoring system designed for crude oil pipeline networks and valve infrastructure. By analyzing multi-sensor telemetry data sequentially over time using deep learning (LSTM), ValveIQ identifies abnormal operations and predicts pipeline conditions before catastrophic failures or leaks occur.

---

## 🚀 Features

- **Sequential LSTM Neural Network**: Deep learning model trained to identify temporal degradation patterns and sensor anomalies across pipeline segments.
- **Multivariate Telemetry Monitoring**:
  - Pressure & Temperature dynamics (including Pressure-Temperature product)
  - Acoustic and physical Vibration
  - Pipe Age & Material Corrosion levels
  - Volumetric Flow Rate & Fluid Salinity
  - Corrosion-Flow interaction ratios
- **Multi-Class Fault Severity Classification**:
  - Normal (Class 0): Stable operational conditions
  - Warning (Class 1): Sub-critical anomalies detected; inspection recommended
  - Critical (Class 2): High-risk fault condition; immediate shutdown / intervention required
- **Dual Application Interfaces**:
  - **Flask Web App & REST API** (main.py): Interactive UI (	emplates/home.html) with real-time JSON prediction API endpoint (/predict).
  - **Streamlit Application** (pp.py): Lightweight dashboard for testing model predictions directly.

---

## 📁 Repository Structure

`
├── app.py                                       # Streamlit web interface
├── main.py                                      # Flask server & REST API
├── lstm_model.h5                                # Trained sequential LSTM model
├── lstm_final (1).ipynb                         # Model training and data exploration notebook
├── final_sequential_lstm_pipeline_dataset.csv   # Sequential sensor pipeline dataset
├── requirements.txt                             # Python dependencies
├── templates/                                   # HTML frontend templates
│   ├── home.html                                # Interactive ValveIQ dashboard
│   ├── base.html                                # Shared base layout
│   └── index.html                               # Landing interface
├── static/                                      # Demo video and assets
└── .vscode/                                     # IDE launch configurations
`

---

## 🛠️ Getting Started

### 1. Clone the repository
`ash
git clone https://github.com/Pooja-Ramdas/ValveIQ.git
cd ValveIQ
`

### 2. Set up virtual environment & dependencies
`ash
python -m venv venv
source venv/bin/activate  # On Windows: .\venv\Scripts\activate
pip install -r requirements.txt
`

### 3. Run the Applications

**Run with Flask:**
`ash
python main.py
`
Open your browser at http://localhost:5000

**Run with Streamlit:**
`ash
streamlit run app.py
`
