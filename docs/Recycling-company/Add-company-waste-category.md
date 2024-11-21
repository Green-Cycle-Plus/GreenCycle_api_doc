---
sidebar_position: 2
---

# Company Add Waste Category

This endpoint allows adding a new waste category to an existing recycling company.

---

## URL

`{{ base_url }}/api/company/add-category`

## Method

`POST`

## Headers

| Header        | Value                                 | Description                      |
|---------------|---------------------------------------|----------------------------------|
| `x-api-key`   | `your-api-key`                       | API key for authentication.     |

---

## Request Body

| Field           | Type     | Required | Description                                    |
|------------------|----------|----------|------------------------------------------------|
| `companyId`     | String   | Yes      | The `_id` of the company from the companies collection. |
| `wasteTypeId`   | String   | Yes      | The unique identifier of the waste type.      |
| `min_weight`    | Integer  | Yes      | Minimum weight (in kilograms) for this category. |
| `amount`        | Integer  | Yes      | Compensation amount for this category (e.g., per kg). |
| `description`   | String   | No       | Optional description for the category.        |

### Example Request Body

```json
{
    "companyId": "673e86f20d815c1bdc4d218c",
    "wasteTypeId": "673c9ed575382bd0d3adeb29",
    "min_weight": 50,
    "amount": 10,
    "description": "This is my category One."
}
```

---

## Response

### Success Response

```json
{
    "success": true,
    "message": "Category addeded",
    "data": {
        "companyId": "673e86f20d815c1bdc4d218c",
        "wasteTypeId": "673c9ed575382bd0d3adeb29",
        "min_weight": 50,
        "amount": 10,
        "description": "This is my category One.",
        "_id": "673f1872c7138a7e146dae89",
        "createdAt": "2024-11-21T11:24:34.799Z",
        "updatedAt": "2024-11-21T11:24:34.799Z",
        "__v": 0
    }
}
```

### Response Fields

#### Root Fields

| Field           | Type     | Description                                    |
|------------------|----------|------------------------------------------------|
| `success`       | Boolean  | Indicates if the request was successful.       |
| `message`       | String   | A message indicating the result of the request. |
| `data`          | Object   | Contains the details of the added waste category. |

#### Data Object Fields

| Field           | Type     | Description                                    |
|------------------|----------|------------------------------------------------|
| `companyId`     | String   | The `_id` of the company this category was added to. |
| `wasteTypeId`   | String   | The unique identifier of the waste type.      |
| `min_weight`    | Integer  | Minimum weight for this category.             |
| `amount`        | Integer  | Compensation amount for this category.        |
| `description`   | String   | Description of the category.                  |
| `_id`           | String   | Unique identifier for this waste category entry. |
| `createdAt`     | DateTime | Timestamp when the category was created.       |
| `updatedAt`     | DateTime | Timestamp of the last update.                  |
| `__v`           | Integer  | Internal versioning field.                    |

---


This endpoint allows you to efficiently manage waste categories for a recycling company by specifying required parameters and optional descriptions.