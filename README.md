# Flower Classification

A machine learning API for classifying Iris flower species using a K-Nearest Neighbors classifier, served through a FastAPI REST endpoint. The project follows a production-ready ML architecture with a packaged model, Docker deployment, and CI/CD automation.

## Features

- **Iris species classification** using a K-Nearest Neighbors (KNN) classifier
- **FastAPI REST API** with automatic Swagger/OpenAPI documentation
- **Scikit-learn pipeline** for streamlined prediction
- **Pydantic request/response validation**
- **Docker containerization** for portable deployment
- **CI/CD with GitHub Actions** for automated testing and Docker image publishing
- **CORS support** for cross-origin requests

## Tech Stack

- **Language:** Python 3.10
- **API Framework:** FastAPI, Uvicorn
- **ML Libraries:** scikit-learn 1.3.0, NumPy, Pandas
- **Validation:** Pydantic
- **Configuration:** StrictYAML, ruamel.yaml
- **Serialization:** Joblib
- **Containerization:** Docker
- **CI/CD:** GitHub Actions

## Setup / Installation

```bash
git clone https://github.com/bnarasimha21/flower-classification.git
cd flower-classification
pip install -r flower_classification_project/requirements/requirements.txt
```

### Train the Model

```bash
python flower_classification_project/flower_classification_model/train_pipeline.py
```

### Run the API

```bash
cd flower_classification_project/flower_classification_api
pip install -r requirements.txt
python app/main.py
```

### Docker

```bash
cd flower_classification_project/flower_classification_api
docker build -t flower_classification_api .
docker run -p 8001:8001 flower_classification_api
```

## Usage

### Health Check

```bash
curl http://localhost:8001/api/v1/health
```

### Classify a Flower

```bash
curl -X POST http://localhost:8001/api/v1/predict \
  -H "Content-Type: application/json" \
  -d '{
    "inputs": [
      {
        "SepalLengthCm": 5.1,
        "SepalWidthCm": 3.5,
        "PetalLengthCm": 1.4,
        "PetalWidthCm": 0.2
      }
    ]
  }'
```

### Interactive Docs

Visit `http://localhost:8001/docs` for the Swagger UI.

## License

MIT
