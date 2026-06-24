# Vehicle Insurance MLOps Pipeline

An end-to-end MLOps project for predicting customer interest in vehicle insurance using a production-ready machine learning pipeline. The project demonstrates data ingestion from MongoDB Atlas, automated model training, model versioning with AWS S3, containerized deployment using Docker, and CI/CD automation through GitHub Actions and AWS EC2.

## Project Highlights

* Automated Data Ingestion from MongoDB Atlas
* Data Validation using schema-based checks
* Feature Engineering and Data Transformation
* Machine Learning Model Training Pipeline
* Model Evaluation and Performance Monitoring
* Model Registry using AWS S3
* FastAPI-based Prediction Service
* Interactive Web UI for Predictions
* Docker Containerization
* Amazon ECR Image Registry
* AWS EC2 Deployment
* GitHub Actions CI/CD Pipeline
* Self-Hosted GitHub Runner Deployment

---

## Project Structure

```text
Vehicle_insurance/
│
├── config/
├── notebook/
├── static/
├── templates/
│
├── src/
│   ├── components/
│   │   ├── data_ingestion.py
│   │   ├── data_validation.py
│   │   ├── data_transformation.py
│   │   ├── model_trainer.py
│   │   ├── model_evaluation.py
│   │   └── model_pusher.py
│   │
│   ├── configuration/
│   ├── data_access/
│   ├── entity/
│   ├── cloud_storage/
│   ├── logger/
│   ├── exception/
│   ├── utils/
│   └── pipline/
│
├── .github/workflows/
├── Dockerfile
├── app.py
├── requirements.txt
└── setup.py
```

---

## 🔄 ML Pipeline Workflow

### 1. Data Ingestion

* Fetches data directly from MongoDB Atlas
* Converts MongoDB documents into Pandas DataFrames
* Stores raw data in feature store

### 2. Data Validation

* Schema validation
* Missing column checks
* Data integrity verification

### 3. Data Transformation

* Feature preprocessing
* Data cleaning
* Transformation object serialization

### 4. Model Training

* Trains machine learning model
* Stores trained artifacts
* Generates model performance metrics

### 5. Model Evaluation

* Compares current model against production model
* Threshold-based model promotion

### 6. Model Registry

* Stores production-ready models in AWS S3
* Supports model versioning

---

## Prediction Service

The FastAPI application provides:

### Training Endpoint

```http
GET /train
```

Triggers the complete training pipeline.

### Prediction Endpoint

```http
POST /
```

Accepts vehicle-related customer information and returns insurance purchase prediction.

---

## AWS Services Used

### Amazon S3

* Model Registry
* Model Version Storage

### Amazon ECR

* Docker Image Storage

### Amazon EC2

* Application Hosting
* Self-Hosted GitHub Runner

### IAM

* Secure AWS Access Management

---

## CI/CD Workflow

### Continuous Integration

1. Push code to GitHub
2. GitHub Actions triggered
3. Build Docker image
4. Push image to Amazon ECR

### Continuous Deployment

1. Self-hosted EC2 runner receives job
2. Pull latest Docker image
3. Stop old container
4. Deploy new container
5. Expose application on configured port

---

##  Docker Deployment

Build image:

```bash
docker build -t vehicle-insurance .
```

Run container:

```bash
docker run -p 5080:5080 vehicle-insurance
```

---

## Tech Stack

### Machine Learning

* Scikit-Learn
* Imbalanced-Learn
* NumPy
* Pandas

### Backend

* FastAPI
* Uvicorn

### Database

* MongoDB Atlas

### Cloud

* AWS S3
* AWS ECR
* AWS EC2

### DevOps

* Docker
* GitHub Actions
* Self Hosted Runner

### Utilities

* Boto3
* PyYAML
* Python Dotenv

---

## Installation

```bash
git clone https://github.com/<username>/Vehicle_insurance.git

cd Vehicle_insurance

conda create -n vehicle python=3.10 -y

conda activate vehicle

pip install -r requirements.txt
```

Set environment variables:

```bash
export MONGODB_URL=<mongodb-url>

export AWS_ACCESS_KEY_ID=<key>

export AWS_SECRET_ACCESS_KEY=<secret>
```

Run application:

```bash
python app.py
```

---

## Author

👩‍💻 Vaishnavi Waghmare

