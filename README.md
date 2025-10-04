# Flask Application with Prometheus Metrics and Grafana Dashboard

##   Project Overview
This project demonstrates monitoring of a Flask web application using **Prometheus** and **Grafana**.  
The Flask app exposes custom metrics which are scraped by Prometheus, and visualized in Grafana dashboards.  

##    Features
- Flask application with sample endpoints:
  - `/checkout`
  - `/payment`
  - `/inventory`
  - `/metrics` (Prometheus endpoint)
- Prometheus metrics:
  - `checkout_requests_total`
  - `payment_failures_total`
  - `inventory_updates_total`
  - `request_latency_seconds`
- Grafana dashboards to visualize metrics:
  - Checkout requests
  - Failed payments
  - Inventory updates
  - Average request latency

##   Tech Stack
- **Flask** (Python web framework)
- **Prometheus** (Monitoring system)
- **Grafana** (Visualization tool)
- **Azure App Service** (Deployment target)

##   Setup Instructions
1. Clone the repo:
  git clone https://github.com/<your-username>/flask-prometheus-grafana.git
  cd flask-prometheus-grafana
Create a virtual environment and install dependencies:
pip install -r requirements.txt
Run the Flask app:
python app.py
The app runs at http://127.0.0.1:5000
Access Prometheus metrics at:http://127.0.0.1:5000/metrics

Configure Prometheus to scrape metrics:
scrape_configs:
  - job_name: 'flask_app'
    static_configs:
      - targets: ['localhost:5000']
Access Grafana at: http://localhost:3000
Add Prometheus as a data source

Create dashboards using queries like:
checkout_requests_total
payment_failures_total
rate(request_latency_seconds_sum[1m]) / rate(request_latency_seconds_count[1m])

Sample Dashboard
Checkout Requests
Failed Payments
Inventory Updates
Average Request Latency

