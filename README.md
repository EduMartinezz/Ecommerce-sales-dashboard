### 🛒 Real-Time E-Commerce Sales Dashboard
An **interactive Streamlit dashboard** for monitoring **e-commerce sales metrics,** analyzing customer behavior, and forecasting future sales.
This project demonstrates a **full end-to-end workflow: data cleaning,** exploratory analysis, business KPIs, forecasting (Prophet/ARIMA), and real-time simulation via Streamlit.

## 📖 Project Overview
- Leverages the **Online Retail dataset (2010–2012 shifted to 2024–2025)** to simulate live sales.
- Provides **exploratory data analysis (EDA)** of customers, products, and regions.
- Computes **key metrics**: Revenue, Orders, Average Order Value (AOV).
- Implements **forecasting models** (Prophet, ARIMA) with backtesting.
- Includes a **Live Mode simulator** to mimic real-time streaming orders.
- Deployable in **Streamlit + ngrok (Colab-ready).**

### 🚀 Features
## 1. Data Cleaning & Preprocessing
- Handles missing values and schema coercion.
- Removes cancellations/returns (optional keep).
- Computes **Revenue = Quantity × UnitPrice**.
- Optionally shifts dates to **2024–2025** for “real-time” demos.

## 2. Exploratory Data Analysis (EDA)
- **Daily revenue trends** with plots.
- **Top products, customers, and countries.**
- Revenue by **weekday and hour.**

## 3. Business Metrics
- **KPIs:** Revenue, Orders, AOV, Customers, Items sold.
- **RFM analysis** (Recency, Frequency, Monetary).
- Downloadable **RFM snapshot.**

## 4. Forecasting
- **Prophet** (if available) or **ARIMA**(auto-ARIMA fallback).
- Adjustable **forecast horizon** (7–90 days).
- **Backtest evaluation** (RMSE, MAPE).
- Downloadable forecast CSV.

## 5. Live Mode (Simulator)
- Generates **synthetic orders** in the current filter context.
- Batch streaming of rows per tick.
- **Live KPIs (24h):** Revenue, Orders, AOV.
Real-time **minute-level revenue** plot.

### 📊 Example Dashboard
## Forecasting Tab (Prophet/ARIMA)


## Live Mode Dashboard




## 🛠️ Tech Stack
- **Language**: Python
- **Libraries**: pandas, numpy, matplotlib, prophet, pmdarima, streamlit
- **Deployment**: Streamlit + ngrok (for Colab public URL)
- **Environment**: Google Colab / Local Python

### ▶️ Quickstart
## 1) Clone & install
git clone https://github.com/your-username/ecommerce-dashboard.git
cd ecommerce-dashboard
pip install -r requirements.txt

## 2) Run locally
streamlit run app_sales.py

## Run in Colab (with ngrok)
!pip install streamlit pyngrok prophet pmdarima
!pkill -f streamlit || true
!streamlit run app_sales.py --server.port 8501 &>/content/logs.txt &

from pyngrok import ngrok
ngrok.set_auth_token("YOUR_TOKEN")
print("App:", ngrok.connect(8501))


## 📈 Example Results
**KPIs (sample 24h):**
| Metric      | Value     |
| ----------- | --------- |
| **Revenue** | \$876,311 |
| **Orders**  | 1,273     |
| **AOV**     | \$688     |

## Forecasting (30-day, Prophet):

- **MAE** ≈ 5,400
- **MAPE** ≈ 8.2%
- Captures **weekly & monthly seasonality.**

## 📂 Project Structure
├── app_sales.py
├── E_Commerce_Sales_Dashboard.ipynb
├── requirements.txt
├── README.md
└── screenshots/

