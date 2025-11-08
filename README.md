
# 10Pearls AQI Predictor

The 10Pearls AQI Predictor is a serverless application that forecasts the Air Quality Index (AQI) for Karachi, Pakistan, over the next 72 hours. It fetches air quality data from the Open-Meteo API, processes it using a feature pipeline, trains machine learning models, and visualizes predictions through an interactive Streamlit dashboard. The project is automated with GitHub Actions for hourly data updates and daily model retraining, and it is containerized using Docker for scalability.

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

## CI/CD Automation

The project includes GitHub Actions workflows for automation:

- **Hourly Feature Updates**: `.github/workflows/fetch_features.yaml` runs `fetch_features.py` every hour.
- **Daily Model Training**: `.github/workflows/train_model.yaml` runs `train_model.py` daily at midnight UTC.
