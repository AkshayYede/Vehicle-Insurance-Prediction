# 🚗 MLOps Project – Vehicle Insurance Prediction

Welcome to this **MLOps project**, crafted to demonstrate a robust, scalable pipeline for managing vehicle insurance data. This project showcases the end-to-end journey from data ingestion to model deployment using industry-standard tools and cloud services.


---

## 📁 Project Structure & Environment Setup

### 1. Project Initialization

* Run `template.py` to generate the project folder structure and placeholder files.

### 2. Package Management

* Configure project packaging using:

  * `setup.py`
  * `pyproject.toml`

### 3. Virtual Environment & Dependencies

```bash
conda create -n venv python=3.10 -y
conda activate venv
pip install -r requirements.txt
pip list  # Verify installation
```

---

## 📊 MongoDB Atlas for Data Management

### 4. MongoDB Setup

* Create a **free M0 cluster** on [MongoDB Atlas](https://www.mongodb.com/cloud/atlas).
* Allow access from all IPs (`0.0.0.0/0`).
* Store your Python connection URI safely.

### 5. Data Push to MongoDB

* Use the `notebook/` directory to load and push data with `mongoDB_demo.ipynb`.
* Verify successful data ingestion via **Browse Collections**.

---

## 🧰 Logging, Exception Handling, and EDA

### 6. Logging & Exception Handling

* Create reusable modules for clean logging and exception tracking.
* Test using `demo.py`.

### 7. EDA & Feature Engineering

* Conduct exploratory data analysis and prepare features using the provided notebooks.

---

## 📥 Data Ingestion Pipeline

### 8. Ingestion Modules

* Define MongoDB connection functions in `configuration/mongo_db_connection.py`.
* Build ingestion components in:

  * `data_access/`
  * `components/data_ingestion.py`
* Update:

  * `entity/config_entity.py`
  * `entity/artifact_entity.py`

### Set MongoDB URL (example):

```bash
export MONGODB_URL="mongodb+srv://<username>:<password>@cluster.mongodb.net/..."
```

---

## 🔍 Data Validation, Transformation, and Model Training

### 9. Data Validation

* Define data schema in `config/schema.yaml`.
* Implement validations in `utils/main_utils.py`.

### 10. Data Transformation

* Handle transformations in `components/data_transformation.py`.
* Use `entity/estimator.py` for estimator logic.

### 11. Model Training

* Implement training logic in `components/model_trainer.py`.

---

## ☁️ AWS Integration: Model Deployment

### 12. AWS Setup

* Create IAM user with **AdministratorAccess**.
* Export AWS credentials:

```bash
export AWS_ACCESS_KEY_ID="your_key"
export AWS_SECRET_ACCESS_KEY="your_secret"
```

* Update `constants/__init__.py` with S3 details.

### 13. S3 Bucket for Model Storage

* Create an S3 bucket (e.g., `my-model-mlopsproj`).
* Use `src/aws_storage/` and `entity/s3_estimator.py` to manage model upload/download.

---

## 🚀 Model Evaluation & Deployment

### 14. Evaluation & Model Pusher

* Evaluate and prepare models for deployment.
* Set up the **prediction pipeline** in `app.py`.

### 15. Web UI Setup

* Place front-end files in `static/` and `templates/`.

---

## 🔄 CI/CD with Docker, GitHub Actions & AWS

### 16. Docker & GitHub Actions

* Create:

  * `Dockerfile`
  * `.dockerignore`
* Store GitHub secrets:

  * `AWS_ACCESS_KEY_ID`
  * `AWS_SECRET_ACCESS_KEY`
  * `AWS_DEFAULT_REGION`
  * `ECR_REPO`

### 17. EC2 & ECR Setup

* Launch EC2, install Docker, and configure as a **self-hosted GitHub runner**.

---

## 🛠️ Final Deployment

### 18. Deployment & Access

---

## 🧠 Project Workflow Summary

```
Data Ingestion ➜ Data Validation ➜ Data Transformation
         ➜ Model Training ➜ Model Evaluation ➜ Model Deployment
                       ➜ CI/CD with GitHub, Docker, and AWS
```
