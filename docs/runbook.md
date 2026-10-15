# Runbook

## Start locally / Локално стартиране

Install the required dependencies:

```bash
python -m pip install -r requirements.txt
```

Start the service on port 9000:

```bash
python -m uvicorn app.main:app --host 127.0.0.1 --port 9000
```

## Check that it works / Проверка, че работи

Check the health endpoint:

```bash
curl http://127.0.0.1:9000/health
```

The service should return a successful response showing that it is healthy.

You can also open:

```text
http://127.0.0.1:9000/health
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
curl -v http://127.0.0.1:9000/health
```
