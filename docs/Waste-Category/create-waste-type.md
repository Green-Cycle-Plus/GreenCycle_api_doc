---
sidebar_position: 1
---
# Create Waste Type

This endpoint allows you to create a new waste type.

---

## URL

`{{base_url}}/waste-type/create`

## Method

`POST`

---

## Headers

| Header        | Value                                 | Description                      |
|---------------|---------------------------------------|----------------------------------|
| `x-api-key`   | `your-api-key`                       | API key for authentication.     |

---

## Request Body

### Fields

| Field       | Type     | Required | Description                                  |
|-------------|----------|----------|----------------------------------------------|
| `name`      | String   | Yes      | Name of the waste type (e.g., `Metals`).    |
| `image`     | String   | No       | URL to an image representing the waste type.|

**Example Request Payload:**

```json
{
    "name": "Metals",
    "image": "https://media.istockphoto.com/id/172453002/photo/tower-of-three-car-wheels-and-1-wheel-on-the-side.jpg?s=612x612&w=0&k=20&c=EjrOpAW2O1lrURRKSbBMtc9Vwi_P9Q1qh_w4Ja7XaZQ="
}
```

---

## Example Request

```bash
curl --location '{{base_url}}/waste-type/create' \
--header 'Content-Type: application/json' \
--header 'x-api-key: c144fca11d1c9453d319eb71a823fca1a6facffa9b534cd6b825c36e57346c40' \
--data-raw '{
    "name": "Metals",
    "image": "https://media.istockphoto.com/id/172453002/photo/tower-of-three-car-wheels-and-1-wheel-on-the-side.jpg?s=612x612&w=0&k=20&c=EjrOpAW2O1lrURRKSbBMtc9Vwi_P9Q1qh_w4Ja7XaZQ="
}'
```

---

## Response

### Success Response

```json
{
    "success": true,
    "message": "New waste added successfully",
    "data": {
        "name": "Metalss",
        "image": "https://media.istockphoto.com/id/172453002/photo/tower-of-three-car-wheels-and-1-wheel-on-the-side.jpg?s=612x612&w=0&k=20&c=EjrOpAW2O1lrURRKSbBMtc9Vwi_P9Q1qh_w4Ja7XaZQ=",
        "_id": "673f24a715ca024123e977e1",
        "createdAt": "2024-11-21T12:16:39.705Z",
        "updatedAt": "2024-11-21T12:16:39.705Z",
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
| `data`          | Object   | The details of the created waste type.         |

#### Data Object Fields

| Field       | Type     | Description                                  |
|-------------|----------|----------------------------------------------|
| `name`      | String   | The name of the created waste type.          |
| `image`     | String   | URL of the image representing the waste type.|
| `_id`       | String   | Unique identifier for the waste type.        |
| `createdAt` | DateTime | Timestamp when the waste type was created.   |
| `updatedAt` | DateTime | Timestamp of the last update to the waste type. |

---

## Error Responses

| Status Code | Message                     | Description                                   |
|-------------|-----------------------------|-----------------------------------------------|
| **400**     | Invalid Request Body        | The `name` field is missing or invalid.       |
| **401**     | Unauthorized                | Missing or invalid `x-api-key` header.        |
| **500**     | Internal Server Error       | An unexpected error occurred on the server.   |

---

## Example Usage

### Request

```bash
curl --location '{{base_url}}/waste-type/create' \
--header 'Content-Type: application/json' \
--header 'x-api-key: c144fca11d1c9453d319eb71a823fca1a6facffa9b534cd6b825c36e57346c40' \
--data-raw '{
    "name": "Metals",
    "image": "https://media.istockphoto.com/id/172453002/photo/tower-of-three-car-wheels-and-1-wheel-on-the-side.jpg?s=612x612&w=0&k=20&c=EjrOpAW2O1lrURRKSbBMtc9Vwi_P9Q1qh_w4Ja7XaZQ="
}'
```

### Response

```json
{
    "success": true,
    "message": "New waste added successfully",
    "data": {
        "name": "Metalss",
        "image": "https://media.istockphoto.com/id/172453002/photo/tower-of-three-car-wheels-and-1-wheel-on-the-side.jpg?s=612x612&w=0&k=20&c=EjrOpAW2O1lrURRKSbBMtc9Vwi_P9Q1qh_w4Ja7XaZQ=",
        "_id": "673f24a715ca024123e977e1",
        "createdAt": "2024-11-21T12:16:39.705Z",
        "updatedAt": "2024-11-21T12:16:39.705Z",
        "__v": 0
    }
}
```

---

This endpoint is used to expand the system by adding new types of waste categories, enhancing flexibility and usability.