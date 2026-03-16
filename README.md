# Flask Backend

This project is a simple **Flask backend API** used in a microservices architecture.  
It exposes a basic endpoint that confirms the backend service is running.

The service is containerized using **Docker** and deployed automatically using a **Jenkins CI/CD pipeline**.

---

## Project Structure

```
flask-backend/
│
├── app.py
├── Dockerfile
├── Jenkinsfile
├── requirements.txt
└── README.md
```

---

## Application

The Flask application exposes one endpoint:

```
GET /
```

Response:

```
Flask Backend Running!
```

The application runs on **port 5000**.

---

## Running Locally

Install dependencies:

```bash
pip3 install -r requirements.txt
```

Run the application:

```bash
python3 app.py
```

Access the service:

```
http://localhost:5000
```

---

## Docker

Build Docker image:

```bash
docker build -t flask-backend .
```

Run container:

```bash
docker run -p 5000:5000 flask-backend
```

---

## Jenkins Pipeline

The Jenkins pipeline performs the following steps:

1. Install Python dependencies from `requirements.txt`
2. Restart the Flask service using **PM2**

Pipeline stages:
- Install Dependencies
- Restart Flask

---

## Technologies Used

- Python
- Flask
- Docker
- Jenkins
- PM2
