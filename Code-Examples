## Python Example: Creating a New Task

```python
import requests
import json

url = 'https://api.techwriter.xyz/tasks'
api_key = 'your_api_key_here'

headers = {
    'X-API-KEY': api_key,
    'Content-Type': 'application/json'
}

data = {
    "title": "Draft User Guide",
    "description": "Create the initial draft of the user guide.",
    "status": "OPEN",
    "component": "HELP_CENTER",
    "connected_tasks": []
}

response = requests.post(url, headers=headers, data=json.dumps(data))

if response.status_code == 201:
    print('Task created successfully:', response.json())
else:
    print('Failed to create task:', response.status_code, response.text)
