House Price Prediction API 🏠
Production-Ready ML Model Deployment with FastAPI
📌 Project Overview
This project demonstrates the transition of a Machine Learning model from a static artifact (.pkl) to a production-ready web service. I developed a high-performance REST API to serve real-time house price predictions using FastAPI and Pydantic.

This implementation follows industry-standard MLOps patterns, ensuring that the model is loaded efficiently, inputs are strictly validated, and the service is easily monitorable.

🚀 Key Features
Efficient Inference: Model and metadata are loaded into memory once at startup via the FastAPI startup_event, preventing latency during requests.

Strict Data Validation: Utilized Pydantic Schemas to enforce data types for 13 house features, ensuring the API rejects malformed inputs with clear error messages.

Automated Documentation: Fully compatible with Swagger UI, providing interactive documentation at the /docs endpoint.

Health Monitoring: Integrated a /health endpoint to monitor model load status and service connectivity.

🛠️ Tech Stack
Language: Python 3.x

Framework: FastAPI

Validation: Pydantic

Server: Uvicorn (ASGI)

ML Libraries: Scikit-learn, NumPy, Joblib

📂 Project Structure
Plaintext

├── main.py          # FastAPI application & endpoint definitions
├── api.py           # Core business logic & model inference
├── schemas.py       # Pydantic data models for request/response validation
├── model.pkl        # Pre-trained Scikit-learn model
└── model_metadata.json # Metadata (features, version, RMSE)
⚙️ Setup & Installation
Clone the repository:

Bash

git clone https://github.com/your-username/house-price-api.git
cd house-price-api
Install dependencies:

Bash

pip install fastapi uvicorn scikit-learn numpy
Run the service:

Bash

uvicorn main:app --reload
Access Interactive Docs: Navigate to http://127.0.0.1:8000/docs to test the endpoints.

📡 API Endpoints Summary
GET /health: Returns service status and confirms model is loaded.

GET /model/info: Retrieves model version, training date, and RMSE metrics.

POST /predict: Accepts house features and returns a predicted price.
