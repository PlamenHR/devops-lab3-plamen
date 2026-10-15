Service / Услугата
Purpose / Предназначение
The service is a simple REST API for creating and reading notes. It also provides health and version endpoints that can be used to check whether the service is running and which version is deployed. The service is intended for the DevOps lab exercises and demonstrates a small API that can be documented, tested and deployed.

Endpoints / Адреси
| Method | Path | What it does / Какво прави |
|---|---|---|
| GET | /health | Checks whether the service is running and healthy. |
| GET | /version | Returns the current version of the service. |
| GET | /notes | Returns all available notes. |
| POST | /notes | Creates a new note. |
| GET | /notes/{id} | Returns a specific note by its ID. |

Dependencies / Зависимости
The service requires Python and the packages listed in requirements.txt. The application must be able to start its HTTP server and listen on port 8000.
