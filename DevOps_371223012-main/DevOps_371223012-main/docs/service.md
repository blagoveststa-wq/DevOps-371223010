# Service

## Purpose

The service provides a simple REST API for creating, listing, and retrieving notes. It is intended for applications or users who need a lightweight way to store and access notes through HTTP endpoints.

## Endpoints

| Method | Path | What it does |
|---|---|---|
| GET | `/health` | Checks whether the service is running and responding to requests. |
| GET | `/version` | Returns the current service version. |
| GET | `/notes` | Returns a list of available notes. |
| POST | `/notes` | Creates a new note using the data provided in the request body. |
| GET | `/notes/{id}` | Retrieves a specific note by its unique ID. |

## Dependencies

The service requires a runtime environment compatible with its implementation language, the necessary application dependencies, and network access to expose its HTTP API. If notes must persist between restarts, it also requires a storage mechanism, such as a database or persistent file storage. Configuration values, including the listening port and storage settings, must be provided as required by the implementation.