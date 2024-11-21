---
sidebar_position: 1
---

# Create a Recycler

Here is the markdown documentation for the endpoint:

---

# Endpoint: Create Recycler

This endpoint is used to onboard recyclers by registering their company details in the decentralized waste management system.

## URL

`{{base_url}}/company/create`

## Method

`POST`

---

## Request Payload

```json
{
    "companyId": 104, // Pass from Contract
    "companyName": "Reliable4 Cycle",
    "email": "company4@gmail.com",
    "phoneNumber": "08155319087",
    "physicalAddress": "Bayeiku Road",
    "lat": 6.571665072719812,
    "lon": 3.5308016142074226,
    "licenseDocument": "http://gateway.cloud/ipfs/xxxx", // IPFS Hash
    "companyLogo": null, // Optional
    "wasteTypeId": "673ca09b7db821b0bfa13778",
    "min_weight": 50, // In Kg By Default
    "amount": 10,
    "description": "This is my category One." // Optional
}
```

### Request Parameters

| Field            | Type     | Required | Description                                    |
|-------------------|----------|----------|------------------------------------------------|
| `companyId`      | Integer  | Yes      | Unique identifier for the company (from contract). |
| `companyName`    | String   | Yes      | Name of the recycler company.                 |
| `email`          | String   | Yes      | Email address for the recycler company.       |
| `phoneNumber`    | String   | Yes      | Contact number of the recycler company.       |
| `physicalAddress`| String   | Yes      | Physical address of the recycler company.     |
| `lat`            | Float    | Yes      | Latitude of the company's location.           |
| `lon`            | Float    | Yes      | Longitude of the company's location.          |
| `licenseDocument`| String   | Yes      | Link to the license document stored on IPFS.  |
| `companyLogo`    | String   | No       | URL for the company logo (optional).          |
| `wasteTypeId`    | String   | Yes      | Identifier for the primary waste type handled.|
| `min_weight`     | Integer  | Yes       | Minimum weight (in kg) accepted for recycling.|
| `amount`         | Integer  | Yes       | Compensation per unit weight.                 |
| `description`    | String   | No       | Additional description about the waste category. |

---

## Response Payload

### Success Response

```json
{
    "success": true,
    "message": "Company Registration successful.",
    "data": {
        "company": {
            "companyId": 105,
            "companyName": "Reliableii Cycle",
            "email": "company6@gmail.com",
            "phoneNumber": "08155319081",
            "physicalAddress": "Bayeiku Road",
            "companyLogo": null,
            "licenseDocument": "http://gateway.cloud/ipfs/xxxx",
            "location": {
                "type": "Point",
                "coordinates": [
                    3.5308016142074226,
                    6.571665072719812
                ]
            },
            "_id": "673f0749a7f15222cae6404f",
            "createdAt": "2024-11-21T10:11:21.036Z",
            "updatedAt": "2024-11-21T10:11:21.036Z",
            "__v": 0
        },
        "primary_waste_type": {
            "companyId": "673f0749a7f15222cae6404f",
            "wasteTypeId": "673ca09b7db821b0bfa13778",
            "min_weight": 50,
            "amount": 10,
            "description": "This is my category One.",
            "wasteName": "Steel"
        }
    }
}
```

### Response Fields

#### Root Fields

| Field    | Type    | Description                               |
|----------|---------|-------------------------------------------|
| `success`| Boolean | Indicates if the request was successful.  |
| `message`| String  | Describes the result of the operation.    |
| `data`   | Object  | Contains the details of the newly created recycler. |

#### Company Object

| Field              | Type     | Description                            |
|---------------------|----------|----------------------------------------|
| `companyId`        | Integer  | ID of the registered company.          |
| `companyName`      | String   | Name of the company.                   |
| `email`            | String   | Email address of the company.          |
| `phoneNumber`      | String   | Contact number of the company.         |
| `physicalAddress`  | String   | Physical address of the company.       |
| `companyLogo`      | String   | URL for the company logo.              |
| `licenseDocument`  | String   | IPFS link to the license document.     |
| `location`         | Object   | Geographical location (latitude, longitude). |
| `_id`              | String   | Unique ID assigned to the company.     |
| `createdAt`        | DateTime | Timestamp of when the company was registered.|
| `updatedAt`        | DateTime | Timestamp of the last update.          |

#### Primary Waste Type Object

| Field           | Type     | Description                              |
|------------------|----------|------------------------------------------|
| `companyId`     | String   | Unique ID of the company.                |
| `wasteTypeId`   | String   | ID of the waste type handled.            |
| `min_weight`    | Integer  | Minimum weight accepted (in kg).         |
| `amount`        | Integer  | Compensation per unit weight.            |
| `description`   | String   | Description of the waste type.           |
| `wasteName`     | String   | Name of the waste type (e.g., "Steel").  |

---

## Error Responses

| Code | Message                     | Description                                  |
|------|-----------------------------|----------------------------------------------|
| 422  | Unprocessable Entity        | Validation error.                            |
| 400  | Invalid payload             | An unexpected error occurred on the server.  |
| 500  | Internal server error       | An unexpected error occurred on the server.  |

--- 

This endpoint ensures recyclers are properly registered with critical details like location, waste type, and regulatory compliance.