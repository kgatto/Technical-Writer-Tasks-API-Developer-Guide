## Authentication

The **Technical Writer Tasks API** uses API key-based authentication to ensure secure access. Every request to the API must include a valid API key in the request headers.

### 1. **How Authentication Works**
- API keys act as unique identifiers for users or applications interacting with the API.
- The API key must be included in the `X-API-KEY` header of every request.
- Requests missing a valid API key will receive a `401 Unauthorized` response.

### 2. **Obtaining an API Key**
To use the API, you need an API key. The process for obtaining an API key will depend on the system managing the API:
- If this is a private API, an administrator or developer must generate and share the key with authorized users.
- If there is a developer portal, you may need to register an account and generate an API key from your dashboard.

### 3. **Using the API Key**
#### Example Request with Authentication
When making requests, include your API key in the `X-API-KEY` header:

#### **cURL Example**
```sh
curl -X GET "https://api.techwriter.xyz/tasks" \
     -H "X-API-KEY: your_api_key_here"  
