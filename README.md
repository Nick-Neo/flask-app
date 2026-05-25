# Flask App

A simple Flask web application with user login, comments/scratchpad functionality, SQLite database, Docker support, and Kubernetes deployment files.

---

## Features

- Flask web application
- User authentication (Login & Logout)
- SQLite database using Flask-SQLAlchemy
- Comment / Scratchpad functionality
- HTML templates and static assets
- Docker container support
- Kubernetes deployment support
- CI/CD ready structure

---

## Tech Stack

- Python 3
- Flask
- Flask-SQLAlchemy
- Flask-Login
- SQLite
- Docker
- Kubernetes

---

## Project Structure

```text
flask-app/
│
├── .github/workflows/
├── static/
├── templates/
├── Dockerfile
├── deployment.yaml
├── service.yaml
├── flask_app.py
├── requirements.txt
└── .gitignore
```

---

## Installation

### 1. Clone Repository

```bash
git clone https://github.com/Nick-Neo/flask-app.git
cd flask-app
```

---

### 2. Create Virtual Environment

Linux / MacOS:

```bash
python -m venv venv
source venv/bin/activate
```

Windows:

```powershell
python -m venv venv
venv\Scripts\activate
```

---

### 3. Install Dependencies

```bash
pip install -r requirements.txt
```

---

### 4. Set Environment Variable

Linux / MacOS:

```bash
export SECRET_KEY="your-secret-key"
```

Windows PowerShell:

```powershell
$env:SECRET_KEY="your-secret-key"
```

---

### 5. Run Application

```bash
python flask_app.py
```

Open your browser:

```text
http://localhost:5000
```

---

## Application Routes

| Route | Description |
|------|-------------|
| `/` | Homepage |
| `/scratchpad/` | Scratchpad / Comments page |
| `/login/` | Login page |
| `/logout/` | Logout page |

---

# Docker Setup

## Build Docker Image

```bash
docker build -t flaskapp .
```

---

## Run Docker Container

```bash
docker run -p 5000:5000 -e SECRET_KEY="your-secret-key" flaskapp
```

---

## Access Application

```text
http://localhost:5000
```

---

# Kubernetes Deployment

## Deploy Application

```bash
kubectl apply -f deployment.yaml
```

---

## Deploy Service

```bash
kubectl apply -f service.yaml
```

---

## Check Pods

```bash
kubectl get pods
```

---

## Check Services

```bash
kubectl get svc
```

---

# CI/CD Pipeline

This project structure supports CI/CD deployment workflows using:

- GitHub Actions
- Docker Hub
- Kubernetes

Recommended production workflow:

1. Push code to GitHub
2. GitHub Actions builds Docker image
3. Docker image pushed to Docker Hub
4. Kubernetes automatically deploys latest stable version

---

# Notes

- Database used: SQLite (`comments.db`)
- Default application port: `5000`
- Docker image currently configured as:

```text
nickneo23/flaskapp:latest
```

For production environments, avoid using the `latest` tag.

### Problems with `latest`

- Unpredictable deployments
- Difficult troubleshooting
- Rollback becomes harder
- Different environments may run different versions
- Kubernetes may pull unexpected image versions
- CI/CD pipelines become less reliable

Recommended:

```text
nickneo23/flaskapp:v1
```

---

# Future Improvements

- User Registration
- Password Reset
- MySQL / PostgreSQL Support
- HTTPS & Reverse Proxy
- Kubernetes Ingress
- Monitoring & Logging
- Cloud Deployment (Azure / AWS / GCP)

---

# Author

## Nick Neo

GitHub:
https://github.com/Nick-Neo

---

# License

This project is for educational and learning purposes.
