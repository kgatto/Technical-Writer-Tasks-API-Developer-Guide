# Technical Writer Tasks API

## 1. Retrieve All Tasks

- **HTTP Method:** `GET`
- **URI:** `/tasks`
- **Description:** Fetches a list of all technical writer tasks, with optional filters.

### Required Headers:

- `X-API-KEY`: Your unique API key.

### Query Parameters:

- `status` (optional): Filter tasks by their status. Valid values:
  - `OPEN`
  - `IN_PROGRESS`
  - `COMPLETED`
- `component` (optional): Filter tasks by their associated component. Valid values:
  - `API_DOCS`
  - `HELP_CENTER`
  - `SDK_DOCS`
  - `OAS_FILE`
- `updatedAfter` (optional): Filter tasks updated after a specific date in `YYYY-MM-DD` format.

### Success Response:

- **Status Code:** `200 OK`
- **Body:**

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

Error Responses:
Retrieve All Tasks (GET /tasks)
Status Code	Description
401 Unauthorized	API key is missing or invalid.
Create a New Task (POST /tasks)
Status Code	Description
400 Bad Request	The request body is malformed or missing required fields.
401 Unauthorized	API key is missing or invalid.
