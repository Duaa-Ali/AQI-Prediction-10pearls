
# 10Pearls AQI Predictor

The 10Pearls AQI Predictor is a serverless application that forecasts the Air Quality Index (AQI) for Karachi, Pakistan, over the next 72 hours. It combines real-time data ingestion, automated model training, and interactive visualization to deliver continuously updated air quality insights.

---

## Overview

This project leverages modern MLOps and cloud automation practices to predict AQI trends for Karachi.
It fetches air quality data from the Open-Meteo API, processes it using a feature pipeline, trains machine learning models, and visualizes predictions through an interactive Streamlit dashboard. The project is automated with GitHub Actions for hourly data updates and daily model retraining, and it is containerized using Docker for scalability.

---

## Key Features

🔄 Automated Data Pipeline:
Fetches and processes air quality and weather data hourly using the Open-Meteo API.

🤖 Machine Learning Forecasting:
Trains regression models (e.g., Random Forest, Ridge) daily to predict AQI for the next 72 hours.

📈 Interactive Dashboard:
A Streamlit-based interface for exploring real-time and forecasted AQI trends.

☁️ Serverless CI/CD Automation:
Fully automated workflows using GitHub Actions:

fetch_features.yaml – hourly feature updates

train_model.yaml – daily model retraining

🐳 Containerized Deployment:
Uses Docker for environment consistency and scalable deployment.

---

## Architecture Overview

1. Data Collection:
Hourly data fetched from the Open-Meteo API (PM2.5, temperature, humidity, wind speed).

2. Feature Engineering:
Feature pipeline processes the data and stores it in Hopsworks.

3. Model Training:
Daily retraining selects the best-performing model using RMSE evaluation.

4. Prediction & Visualization:
Forecasts are displayed in a live Streamlit dashboard with historical trends and insights.

5. CI/CD Automation:
GitHub Actions handle hourly feature updates and daily model retraining automatically.

---

## Repository Structure

- `fetch_features.py`: Fetches and processes air quality data, storing features in Hopsworks.  
- `train_model.py`: Trains machine learning models and saves the best model to Hopsworks.  
- `app.py`: Streamlit application for visualizing AQI forecasts and historical data.  
- `Dockerfile`: Defines the Docker image for the Streamlit app.  
- `docker-compose.yml`: Configures the Docker service.  
- `requirements.txt`: Lists Python dependencies.  
- `.github/workflows/fetch_features.yaml`: GitHub Actions workflow for hourly feature updates.  
- `.github/workflows/train_model.yaml`: GitHub Actions workflow for daily model training.
