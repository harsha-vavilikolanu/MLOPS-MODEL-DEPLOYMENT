# ML Model Deployment Strategies and Model Serving Using FastAPI

## Student Details

- **Name:** Sri Harsha
- **Registration Number:** 231FA04092
- **Section:** 15

---

## Project Overview

This project demonstrates the end-to-end deployment of a Machine Learning classification model using the Titanic dataset. The model predicts whether a passenger survived based on input passenger information.

The project explores different inference strategies—**online inference, batch inference, and streaming inference**—and integrates the trained model with a REST API using FastAPI. It also demonstrates input validation, model serving, and API testing.

## Objectives

- Develop and train a machine learning classification pipeline.
- Save and load the trained model using Joblib.
- Implement online inference for individual passenger records.
- Perform batch inference on multiple passenger records.
- Simulate streaming inference with a one-second processing interval.
- Deploy the model through a FastAPI application.
- Validate incoming data using Pydantic.
- Test API endpoints using Swagger UI and a Python client.

## Technologies Used

| Technology | Purpose |
|---|---|
| Python | Core programming language |
| Pandas | Data manipulation and processing |
| Scikit-learn | Model training and preprocessing pipeline |
| Joblib | Model serialization and loading |
| FastAPI | REST API development and model serving |
| Uvicorn | ASGI server for running the API |
| Pydantic | Request data validation |
| Requests | Sending HTTP requests from the client |

## Key Features

### 1. Machine Learning Pipeline
Trains a classification pipeline using the Titanic dataset to predict passenger survival.

### 2. Online Inference
Accepts an individual passenger record and generates a prediction.

### 3. Batch Inference
Processes multiple passenger records and saves the generated predictions to a CSV file.

### 4. Streaming Inference
Processes passenger records sequentially with a one-second delay to simulate streaming prediction.

### 5. FastAPI Model Serving
Exposes the trained model through HTTP endpoints, making predictions accessible to external applications.

### 6. Input Validation
Uses Pydantic schemas to validate incoming API requests and handle invalid input data.

### 7. API Testing
Supports interactive testing through Swagger UI and automated requests through a Python client.

## Project Structure

```text
ML-Model-Deployment/
│
├── model.pkl
├── inference_unseen.csv
├── batch_predictions.csv
├── app.py
├── client.py
├── online_inference.py
├── batch_inference.py
├── streaming_inference.py
├── requirements.txt
└── README.md
```

**File descriptions:**

- `model.pkl` — Serialized machine learning pipeline.
- `inference_unseen.csv` — Passenger records used for inference.
- `batch_predictions.csv` — Output file containing batch prediction results.
- `app.py` — FastAPI application and prediction endpoints.
- `client.py` — Python client for testing the API.
- `online_inference.py` — Script for individual predictions.
- `batch_inference.py` — Script for batch predictions.
- `streaming_inference.py` — Script for sequential, simulated streaming predictions.
- `requirements.txt` — List of required Python packages.
- `README.md` — Project documentation and setup instructions.

## Installation and Setup

### Prerequisites

Ensure that Python and pip are installed on your system.

### Step 1: Clone the Repository

```bash
git clone <your-repository-url>
cd ML-Model-Deployment
```

Replace `<your-repository-url>` with your actual Git repository URL.

### Step 2: Install Dependencies

```bash
pip install -r requirements.txt
```

### Step 3: Start the FastAPI Server

```bash
uvicorn app:app --reload
```

The API will be available at:

`http://127.0.0.1:8000`

### Step 4: Open Swagger UI

Navigate to the following URL in your browser to explore and test the API interactively:

`http://127.0.0.1:8000/docs`

### Step 5: Test the API Client

Open another terminal in the project directory and execute:

```bash
python client.py
```

Ensure the FastAPI server is running before executing the client.

## API Endpoints

| Method | Endpoint | Description |
|---|---|---|
| GET | `/health` | Checks API availability and model status. |
| POST | `/predict` | Accepts passenger information and returns a survival prediction. |

### Example Prediction Request

The exact request fields depend on the Pydantic schema defined in `app.py`.

A typical passenger record may include:

```json
{
  "Pclass": 3,
  "Sex": "male",
  "Age": 25,
  "SibSp": 0,
  "Parch": 0,
  "Fare": 7.25,
  "Embarked": "S"
}
```

The actual field names, accepted values, and required fields must match the implementation in your application.

## Inference Strategies

| Strategy | Description | Typical Use Case |
|---|---|---|
| Online inference | Predicts one record per request. | Real-time applications |
| Batch inference | Processes multiple records together. | Large datasets and scheduled jobs |
| Streaming inference | Processes records sequentially as they arrive. | Simulated continuous data processing |

**Note:** The streaming implementation in this project simulates streaming behavior using a one-second delay. It is not a production-grade distributed streaming system.

## Expected Outcomes

After completing the project, you should be able to:

- Train and serialize a machine learning pipeline.
- Load a saved model for inference.
- Implement online, batch, and simulated streaming prediction workflows.
- Serve a machine learning model through a REST API.
- Validate request data using Pydantic.
- Test API functionality using Swagger UI and Python HTTP requests.
- Understand the differences between common model inference strategies.

## Conclusion

This project demonstrates a practical approach to machine learning model deployment and serving. By combining Scikit-learn with FastAPI, it provides an interface for generating predictions from a trained Titanic survival classification model.

The implementation covers model serialization, multiple inference strategies, REST API integration, request validation, and API testing. It provides a foundation for understanding how machine learning models can be integrated into software applications and extended toward more advanced deployment workflows.

---

**Project:** ML Model Deployment Strategies and Model Serving Using FastAPI  
**Student:** Sri Harsha  
**Registration Number:** 231FA04092  
**Section:** 15
