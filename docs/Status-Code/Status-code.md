# Status Codes

This page outlines the standard error status codes returned by the Decentralized Waste Management API. These status codes help developers understand and troubleshoot issues when making requests to the API.

---

## Common HTTP Status Codes

| Status Code | Message               | Description                                                                          |
| ----------- | --------------------- | ------------------------------------------------------------------------------------ |
| **200**     | OK                    | The request was successful, and the response contains the expected data.             |
| **201**     | Created               | The request was successful, and a new resource was created.                          |
| **400**     | Bad Request           | The request payload is missing required fields or contains invalid values.           |
| **401**     | Unauthorized          | Authentication is required or failed due to invalid credentials.                     |
| **403**     | Forbidden             | The client does not have permission to access this resource.                         |
| **404**     | Not Found             | The requested resource does not exist.                                               |
| **409**     | Conflict              | A conflict occurred, such as duplicate data or resource already exists.              |
| **422**     | Unprocessable Entity  | The request payload is well-formed but cannot be processed (e.g., validation error). |
| **500**     | Internal Server Error | An unexpected error occurred on the server.                                          |
| **503**     | Service Unavailable   | The service is temporarily unavailable (e.g., under maintenance).                    |

---
