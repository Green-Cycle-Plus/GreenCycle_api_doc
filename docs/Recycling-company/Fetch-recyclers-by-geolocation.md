---
sidebar_position: 5
---
# Get Nearby Recycling Companies

This endpoint retrieves a list of recycling companies within a specified radius of a given geolocation.

---

## URL

`{{base_url}}/company/nearby`

## Method

`GET`

## Headers

| Header        | Value                                 | Description                      |
|---------------|---------------------------------------|----------------------------------|
| `x-api-key`   | `your-api-key`                       | API key for authentication.     |

---

## Query Parameters

| Parameter       | Type    | Required | Description                                    |
|------------------|---------|----------|------------------------------------------------|
| `latitude`      | Float   | Yes      | Latitude of the center point.                 |
| `longitude`     | Float   | Yes      | Longitude of the center point.                |
| `radius`        | Integer | Yes      | Radius (in kilometers) to search within.      |

### Example Query String

```
latitude=6.585584356880885&longitude=3.5276854039759784&radius=10
```

**Example Request:**

```bash
curl --location '{{base_url}}/company/nearby?latitude=6.585584356880885&longitude=3.5276854039759784&radius=10' \
--header 'x-api-key: c144fca11d1c9453d319eb71a823fca1a6facffa9b534cd6b825c36e57346c40'
```

---

## Response

### Success Response

```json
{
    "success": true,
    "message": "Nearby companies fetched successfully.",
    "data": [
        {
            "_id": "673e86f20d815c1bdc4d218c",
            "companyId": 104,
            "companyName": "Reliable4 Cycle",
            "email": "company4@gmail.com",
            "phoneNumber": "08155319087",
            "physicalAddress": "Bayeiku Road",
            "companyLogo": null,
            "licenseDocument": "http://gateway.cloud/ipfs/xxxx",
            "distance": 2.5,
            "location": {
                "type": "Point",
                "coordinates": [
                    3.5308016142074226,
                    6.571665072719812
                ]
            },
            "createdAt": "2024-11-21T01:03:46.781Z",
            "updatedAt": "2024-11-21T01:03:46.781Z"
        },
        {
            "_id": "673e86f20d815c1bdc4d218d",
            "companyId": 105,
            "companyName": "EcoGreen Recyclers",
            "email": "ecogreen@gmail.com",
            "phoneNumber": "08155319100",
            "physicalAddress": "Lekki Phase 1",
            "companyLogo": "http://gateway.cloud/ipfs/xyz",
            "licenseDocument": "http://gateway.cloud/ipfs/abcd",
            "distance": 9.8,
            "location": {
                "type": "Point",
                "coordinates": [
                    3.421123456789,
                    6.601234567890
                ]
            },
            "createdAt": "2024-11-20T12:45:30.123Z",
            "updatedAt": "2024-11-20T12:45:30.123Z"
        }
    ]
}
```

### Response Fields

#### Root Fields

| Field           | Type     | Description                                    |
|------------------|----------|------------------------------------------------|
| `success`       | Boolean  | Indicates if the request was successful.       |
| `message`       | String   | A message indicating the result of the request. |
| `data`          | Array    | An array of nearby company objects.            |

#### Company Object

| Field              | Type     | Description                                    |
|---------------------|----------|------------------------------------------------|
| `_id`              | String   | Unique identifier for the company in the database. |
| `companyId`        | Integer  | Unique identifier for the company (from contract). |
| `companyName`      | String   | Name of the recycler company.                 |
| `email`            | String   | Email address of the recycler company.        |
| `phoneNumber`      | String   | Contact number of the recycler company.       |
| `physicalAddress`  | String   | Physical address of the recycler company.     |
| `companyLogo`      | String   | URL of the company logo (or `null` if not provided). |
| `licenseDocument`  | String   | URL of the license document stored on IPFS.   |
| `distance`         | Float    | Distance (in kilometers) from the search center point. |
| `location`         | Object   | Geographical location of the company.         |
| `location.type`    | String   | Always `"Point"`.                             |
| `location.coordinates`| Array | `[longitude, latitude]` format coordinates.   |
| `createdAt`        | DateTime | Timestamp when the company was created.       |
| `updatedAt`        | DateTime | Timestamp of the last update to the company.  |

---

## Error Responses

| Status Code | Message                     | Description                                   |
|-------------|-----------------------------|-----------------------------------------------|
| **400**     | Invalid Query Parameters    | Missing or invalid `latitude`, `longitude`, or `radius`. |
| **401**     | Unauthorized                | Missing or invalid `x-api-key` header.        |
| **500**     | Internal Server Error       | An unexpected error occurred on the server.   |

---

## Example Usage

### Request

```bash
curl --location '{{base_url}}/company/nearby?latitude=6.585584356880885&longitude=3.5276854039759784&radius=10' \
--header 'x-api-key: c144fca11d1c9453d319eb71a823fca1a6facffa9b534cd6b825c36e57346c40'
```

### Response

```json
{
    "success": true,
    "message": "Nearby companies fetched successfully.",
    "data": [
        {
            "_id": "673e86f20d815c1bdc4d218c",
            "companyId": 104,
            "companyName": "Reliable4 Cycle",
            "email": "company4@gmail.com",
            "phoneNumber": "08155319087",
            "physicalAddress": "Bayeiku Road",
            "companyLogo": null,
            "licenseDocument": "http://gateway.cloud/ipfs/xxxx",
            "distance": 2.5,
            "location": {
                "type": "Point",
                "coordinates": [
                    3.5308016142074226,
                    6.571665072719812
                ]
            },
            "createdAt": "2024-11-21T01:03:46.781Z",
            "updatedAt": "2024-11-21T01:03:46.781Z"
        }
    ]
}
```

--- 

This endpoint helps in locating recycling companies near a specific geolocation within a defined radius, enhancing the ease of connecting with nearby recyclers.