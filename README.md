# Project Setup

## I. Run or Test Locally
Requires:  
    Python  
    Docker Desktop 

### 1. Create & Activate Environment  
```bash
python3.10 -m venv venv    # Pin to v3.10
source venv/bin/activate   # Mac/Linux
venv\Scripts\activate.bat  # Windows
```

### 2. Install Dependencies
```bash
pip install -r requirements.txt
```

### 3. Load and Run PostgreSQL Container
```bash
docker compose up -d db
```

### 4. Test Locally 
```bash
pytest
```

### 5. Run Locally 
```bash
uvicorn app.main:app --reload --host 0.0.0.0 --port 8000
``` 

## II. DockerHub
DockerHub URL: https://hub.docker.com/repository/docker/nosaomoregie/601_m11no
```bash
docker pull nosaomoregie/601_m12no
```

## III. Container Order
Start the db container before other services so database initialization completes first:
```bash
docker compose up --build --wait db
```

