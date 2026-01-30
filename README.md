# Vorhersage-der-Versicherungspraemie
# Insurance Premium Prediction API

This project provides a machine‑learning powered Insurance Premium Prediction Model that classifies a person’s expected insurance premium into one of the following categories:

- **High**
- **Medium**
- **Low**

The API also returns a **confidence score** for the predicted category.  
It is built using **FastAPI** and packaged as a **Docker image** for easy deployment.

---

## 🚀 Features

- Predicts insurance premium category with confidence value  
- FastAPI `/prediction` endpoint  
- Dockerized for portability  
- Interactive Swagger UI  
- Health and home endpoints for quick checks  

---

## 📦 Docker Setup

### Build the Docker Image
```bash
docker build -t sgphule/ml-fast-api .
```
### Push Image to Docker Hub
```bash
docker push sgphule/ml-fast-api:latest
```
### Pull Image from Docker Hub
```bash
docker pull sgphule/ml-fast-api:latest
```
### Run the Docker Container
```bash
docker run -p 8000:8000 sgphule/ml-fast-api
```
### API Endpoints
Home
http://localhost:8000
Health Check
http://localhost:8000/health
Swagger Docs
http://localhost:8000/docs

### Example request body for POST http://localhost:8000/prediction
```bash
{
  "age": 30,
  "weight": 70,
  "height": 1.75,
  "income_lpa": 62,
  "smoker": false,
  "city": "Berlin",
  "occupation": "Engineer"
}
```

### Example Cities
Berlin, Hamburg, Munich, Frankfurt, Cologne, Stuttgart, Düsseldorf, Leipzig, Nuremberg, Bonn,
Duisburg, Bielefeld, Wuppertal, Dortmund, Bremen, Bochum, Münster, Dresden, Essen, Hanover

### Example Occupations
Teacher, Doctor, Entrepreneur, Lawyer, Scientist, Artist, Engineer

### Example Response
```bash
{
  "predicted response": {
    "predicted_category": "high",
    "confidence": 0.9983,
    "class_probabilities": {
      "high": 0.9983,
      "low": 0,
      "medium": 0.0017
    }
  }
}
```



