---
sidebar_position: 3
---

# Group company by Waste Type

---

#### **Endpoint**
`GET {{base_url}}/company/waste-types`

#### **Description**
Fetches a list of waste categories along with companies that offer waste management services for those categories.

---

#### **Request**

##### **Headers**
- **x-api-key**: (required) API key for accessing the endpoint.

##### **Query Parameters**
None

---

#### **Response**

##### **Success Response**
**Status Code**: `200 OK`

**Body**:
```json
{
    "success": true,
    "message": "Waste type fetched",
    "data": [
        {
            "_id": "673ca09b7db821b0bfa13778",
            "wasteType": "Steel",
            "companies": [
                "Reliable4 Cycle",
                "Reliableii Cycle"
            ],
            "totalCompanies": 2
        },
        {
            "_id": "673c9ed575382bd0d3adeb29",
            "wasteType": "Glass",
            "companies": [
                "Reliable4 Cycle",
                "CCMI2"
            ],
            "totalCompanies": 2
        }
    ]
}
```

**Fields**:
- **success**: Boolean indicating if the request was successful.
- **message**: A brief description of the result.
- **data**: Array containing waste types and associated companies.
    - **_id**: Unique identifier for the waste type.
    - **wasteType**: Name of the waste category (e.g., Steel, Glass).
    - **companies**: List of companies offering services for the given waste type.
    - **totalCompanies**: Number of companies offering services for the waste type.

---

##### **Error Response**
**Status Code**: `401 Unauthorized`  
**Body**:
```json
{
    "success": false,
    "message": "Unauthorized"
}
```

**Status Code**: `500 Internal Server Error`  
**Body**:
```json
{
    "success": false,
    "message": "An unexpected error occurred"
}
```

---

#### **Example Request**

```http
GET /company/waste-types HTTP/1.1
Host: {{base_url}}
x-api-key: <your_api_key>
```

---

#### **Example Success Response**

```json
{
    "success": true,
    "message": "Waste type fetched",
    "data": [
        {
            "_id": "673ca09b7db821b0bfa13778",
            "wasteType": "Steel",
            "companies": [
                "Reliable4 Cycle",
                "Reliableii Cycle"
            ],
            "totalCompanies": 2
        },
        {
            "_id": "673c9ed575382bd0d3adeb29",
            "wasteType": "Glass",
            "companies": [
                "Reliable4 Cycle",
                "CCMI2"
            ],
            "totalCompanies": 2
        }
    ]
}
```

---

#### **Notes**
- Ensure a valid `x-api-key` header is included in the request.
- For troubleshooting, contact the API support team if persistent errors occur.