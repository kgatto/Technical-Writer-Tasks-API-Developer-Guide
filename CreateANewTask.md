# Create a New Task  

Adds a new technical writer task to the system.  

## HTTP Method and URI  
- **Method:** `POST`  
- **Endpoint:** `/task`  

## Required Headers  
- `Content-Type: application/json`  
- `X-API-KEY`: Your unique API key (required for authentication).  

## Request Body Structure  

```json
{
  "title": "Write API Overview",
  "description": "Create a high-level overview of the API functionalities.",
  "status": "OPEN",
  "component": "API_DOCS",
  "connected_tasks": [
    {
      "task_id": "12345",
      "title": "Update API Documentation",
      "description": "Revise the authentication section.",
      "status": "IN_PROGRESS"
    }
  ]
}

## Success Response

Status Code: 201 Created

Response Body:

{
  "task_id": "98765",
  "title": "Write API Overview",
  "description": "Create a high-level overview of the API functionalities.",
  "status": "OPEN",
  "component": "API_DOCS",
  "connected_tasks": []
}

## Python Code Example: Authenticate & Make a POST Request

import requests

API_URL = "https://api.techwriter.xyz/task"
API_KEY = "your_api_key_here"

headers = {
    "Content-Type": "application/json",
    "X-API-KEY": API_KEY
}

data = {
    "title": "Write API Overview",
    "description": "Create a high-level overview of the API functionalities.",
    "status": "OPEN",
    "component": "API_DOCS",
    "connected_tasks": []
}

response = requests.post(API_URL, json=data, headers=headers)

if response.status_code == 201:
    print("Task Created Successfully!")
    print(response.json())
else:
    print(f"Error: {response.status_code} - {response.text}")


## JavaScript (Node.js) Code Example: Authenticate & Make a POST Request

const axios = require('axios');

const API_URL = "https://api.techwriter.xyz/task";
const API_KEY = "your_api_key_here";

const headers = {
    "Content-Type": "application/json",
    "X-API-KEY": API_KEY
};

const data = {
    title: "Write API Overview",
    description: "Create a high-level overview of the API functionalities.",
    status: "OPEN",
    component: "API_DOCS",
    connected_tasks: []
};

axios.post(API_URL, data, { headers })
    .then(response => {
        console.log("Task Created Successfully!", response.data);
    })
    .catch(error => {
        console.error("Error:", error.response ? error.response.data : error.message);
    });

## Status Codes Explanation

201 Created	Task successfully created.
400 Bad Request	Invalid request body or missing fields.
401 Unauthorized	API key is missing or invalid.
