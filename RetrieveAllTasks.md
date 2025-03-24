# Retrieve All Tasks

Fetches a list of all technical writer tasks with optional filters.

## HTTP Method and URI  
- **Method:** `GET`  
- **Endpoint:** `/tasks`  

## Required Headers  
- `X-API-KEY`: Your unique API key (required for authentication).  

## Query Parameters (Optional)  

| Parameter      | Type   | Description |
|--------------|--------|-------------|
| `status`     | string | Filter by task status (`OPEN`, `IN_PROGRESS`, `COMPLETED`). |
| `component`  | string | Filter by task component (`API_DOCS`, `HELP_CENTER`, `SDK_DOCS`, `OAS_FILE`). |
| `updatedAfter` | string (date) | Filter tasks updated after a specific date (`YYYY-MM-DD`). |

## Success Response  

**Status Code:** `200 OK`  

**Response Body:**  

```json
[
  {
    "task_id": "12345",
    "title": "Update API Documentation",
    "description": "Revise the authentication section.",
    "status": "IN_PROGRESS",
    "component": "API_DOCS",
    "connected_tasks": []
  },
  {
    "task_id": "67890",
    "title": "Create SDK Guide",
    "description": "Develop a comprehensive guide for the new SDK.",
    "status": "OPEN",
    "component": "SDK_DOCS",
    "connected_tasks": []
  }
]
