# Runbook

## Start locally / Локално стартиране

Install the required dependencies:

```bash
python -m pip install -r requirements.txt
```

Start the service on port 8000:

```bash
python -m uvicorn app.main:app --host 127.0.0.1 --port 8000
```

## Check that it works / Проверка, че работи

Check the health endpoint:

```bash
curl http://127.0.0.1:8000/health
```

The service should return a successful response showing that it is healthy.

You can also open:

```text
http://127.0.0.1:8000/health
```

in a web browser.

## Run the tests / Тестове

Run the automated tests:

```bash
python -m pytest
```

## When something breaks / Когато нещо се счупи

First, check the installed Python version:

```bash
python --version
```

Then check that the required packages are installed:

```bash
python -m pip install -r requirements.txt
```

Finally, check the service health endpoint:

```bash
curl -v http://127.0.0.1:8000/health
```

## Running with Docker / Стартиране с Docker

### 1. Build the image

Run this command from the repository root:

```powershell
docker build -t notes-api:v3 .
```

### 2. Start the container

```powershell
docker run -d --name lab3-api-runbook -p 8003:8000 notes-api:v3
```

Port 8003 is used on the host computer, while the application listens on port 8000 inside the container.

### 3. Check the application

In PowerShell:

```powershell
Invoke-RestMethod http://localhost:8003/health
```

Expected response:

```json
{"status":"ok"}
```

API documentation is available at:

http://localhost:8003/docs

### 4. Check container status and logs

```powershell
docker ps
docker logs lab3-api-runbook
```

### 5. Stop and remove the container

```powershell
docker stop lab3-api-runbook
docker rm lab3-api-runbook
```

### Troubleshooting

If the container does not start, check its logs using `docker logs lab3-api-runbook`.

If port 8003 is already in use, choose another free host port.

Make sure Docker Desktop is running before executing Docker commands.

