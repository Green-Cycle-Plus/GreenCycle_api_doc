---
sidebar_position: 3
---

# Fetch Recycler Details By CompanyID(Object)

This endpoint retrieves detailed information about a specific recycling company, including its location, contact details, and the waste categories it handles.

---

## URL

`{{ base_url }}company/show/{companyId}`

## Method

`GET`

## Headers

| Header        | Value                                 | Description                      |
|---------------|---------------------------------------|----------------------------------|
| `x-api-key`   | `your-api-key`                       | API key for authentication.     |

---

## Request Parameters

| Parameter    | Type     | Required | Description                         |
|--------------|----------|----------|-------------------------------------|
| `companyId`  | String   | Yes      | The unique ID of the recycling company. |

**Example Request:**

```bash
curl --location '{{base_url}}/company/show/673e86f20d815c1bdc4d218c' \
--header 'x-api-key: c144fca11d1c9453d319eb71a823fca1a6facffa9b534cd6b825c36e57346c40'
```

---

## Response

### Success Response

```json
{
    "success": true,
    "company": {
        "location": {
            "type": "Point",
            "coordinates": [
                3.5308016142074226,
                6.571665072719812
            ]
        },
        "_id": "673e86f20d815c1bdc4d218c",
        "companyId": 104,
        "companyName": "Reliable4 Cycle",
        "email": "company4@gmail.com",
        "phoneNumber": "08155319087",
        "physicalAddress": "Bayeiku Road",
        "companyLogo": null,
        "licenseDocument": "http://gateway.cloud/ipfs/xxxx",
        "createdAt": "2024-11-21T01:03:46.781Z",
        "updatedAt": "2024-11-21T01:03:46.781Z",
        "__v": 0
    },
    "wastes_categories": [
        {
            "id": "673e86f30d815c1bdc4d218e",
            "wasteTypeId": "673ca09b7db821b0bfa13778",
            "wasteName": "Steel",
            "min_weight": 50,
            "amount": 10,
            "description": "This is my category One."
        }
    ]
}
```

### Response Fields

#### Root Fields

| Field             | Type     | Description                                |
|--------------------|----------|--------------------------------------------|
| `success`         | Boolean  | Indicates if the request was successful.   |
| `company`         | Object   | Details of the recycling company.          |
| `wastes_categories`| Array   | List of waste categories handled.          |

#### Company Object

| Field              | Type     | Description                                    |
|---------------------|----------|------------------------------------------------|
| `location`         | Object   | Geographical location of the company.         |
| `location.type`    | String   | Always `"Point"`.                             |
| `location.coordinates`| Array | `[longitude, latitude]` format coordinates.   |
| `_id`              | String   | Unique identifier for the company in the database. |
| `companyId`        | Integer  | Unique identifier for the company (from contract). |
| `companyName`      | String   | Name of the recycler company.                 |
| `email`            | String   | Email address of the recycler company.        |
| `phoneNumber`      | String   | Contact number of the recycler company.       |
| `physicalAddress`  | String   | Physical address of the recycler company.     |
| `companyLogo`      | String   | URL of the company logo (or `null` if not provided). |
| `licenseDocument`  | String   | URL of the license document stored on IPFS.   |
| `createdAt`        | DateTime | Timestamp when the company was created.       |
| `updatedAt`        | DateTime | Timestamp of the last update to the company.  |

#### Waste Categories Object

| Field           | Type     | Description                                   |
|------------------|----------|-----------------------------------------------|
| `id`            | String   | Unique identifier for the waste category.     |
| `wasteTypeId`   | String   | Identifier of the waste type.                 |
| `wasteName`     | String   | Name of the waste type (e.g., "Steel").       |
| `min_weight`    | Integer  | Minimum weight (in kg) accepted for recycling.|
| `amount`        | Integer  | Compensation per unit weight (e.g., per kg).  |
| `description`   | String   | Additional details about the waste category.  |

---