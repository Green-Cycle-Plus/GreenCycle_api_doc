---
sidebar_position: 2
---

---

# Fetch All Waste Types

This endpoint retrieves a list of all waste types available in the system.

---

## URL

`{{base_url}}/waste-type`

## Method

`GET`

---

## Headers

| Header        | Value                                 | Description                      |
|---------------|---------------------------------------|----------------------------------|
| `x-api-key`   | `your-api-key`                       | API key for authentication.     |

---

## Example Request

```bash
curl --location '{{base_url}}/waste-type' \
--header 'x-api-key: c144fca11d1c9453d319eb71a823fca1a6facffa9b534cd6b825c36e57346c40'
```

---

## Response

### Success Response

```json
{
    "success": true,
    "message": "All Waste Type",
    "data": [
        {
            "_id": "673c9ea875382bd0d3adeb27",
            "name": "Plastic",
            "image": "https://yesstraws.com/cdn/shop/articles/1_plastic_bottles_3600x.jpg?v=1579268178",
            "createdAt": "2024-11-19T14:20:24.654Z",
            "updatedAt": "2024-11-19T14:20:24.654Z",
            "__v": 0
        },
        {
            "_id": "673c9ed575382bd0d3adeb29",
            "name": "Glass",
            "image": "https://encrypted-tbn0.gstatic.com/images?q=tbn:ANd9GcSqhTdP_bPMCIW4kVwVhMrkUnnl4AT2ilu05w&s",
            "createdAt": "2024-11-19T14:21:09.944Z",
            "updatedAt": "2024-11-19T14:21:09.944Z",
            "__v": 0
        },
        {
            "_id": "673ca09b7db821b0bfa13778",
            "name": "Steel",
            "image": "https://cdn11.bigcommerce.com/s-lq1r9s/images/stencil/500x659/products/3968728/4400281/e062e5c0-6d5c-4b52-bd57-4c07aa3bed4c__17806.1721308167.jpg?c=2",
            "createdAt": "2024-11-19T14:28:43.852Z",
            "updatedAt": "2024-11-19T14:28:43.852Z",
            "__v": 0
        },
        {
            "_id": "673d578ba61925577ace6b79",
            "name": "Tyres",
            "image": "https://media.istockphoto.com/id/172453002/photo/tower-of-three-car-wheels-and-1-wheel-on-the-side.jpg?s=612x612&w=0&k=20&c=EjrOpAW2O1lrURRKSbBMtc9Vwi_P9Q1qh_w4Ja7XaZQ=",
            "createdAt": "2024-11-20T03:29:15.496Z",
            "updatedAt": "2024-11-20T03:29:15.496Z",
            "__v": 0
        },
        {
            "_id": "673f248d15ca024123e977d9",
            "name": "Metals",
            "image": "https://media.istockphoto.com/id/172453002/photo/tower-of-three-car-wheels-and-1-wheel-on-the-side.jpg?s=612x612&w=0&k=20&c=EjrOpAW2O1lrURRKSbBMtc9Vwi_P9Q1qh_w4Ja7XaZQ=",
            "createdAt": "2024-11-21T12:16:13.084Z",
            "updatedAt": "2024-11-21T12:16:13.084Z",
            "__v": 0
        },
        {
            "_id": "673f24a715ca024123e977e1",
            "name": "Metalss",
            "image": "https://media.istockphoto.com/id/172453002/photo/tower-of-three-car-wheels-and-1-wheel-on-the-side.jpg?s=612x612&w=0&k=20&c=EjrOpAW2O1lrURRKSbBMtc9Vwi_P9Q1qh_w4Ja7XaZQ=",
            "createdAt": "2024-11-21T12:16:39.705Z",
            "updatedAt": "2024-11-21T12:16:39.705Z",
            "__v": 0
        }
    ]
}
```

### Response Fields

#### Root Fields

| Field       | Type     | Description                                    |
|-------------|----------|------------------------------------------------|
| `success`   | Boolean  | Indicates if the request was successful.       |
| `message`   | String   | Message describing the result of the request.  |
| `data`      | Array    | A list of waste types.                         |

#### Waste Type Object Fields

| Field       | Type     | Description                                  |
|-------------|----------|----------------------------------------------|
| `_id`       | String   | Unique identifier for the waste type.        |
| `name`      | String   | Name of the waste type (e.g., "Plastic").     |
| `image`     | String   | URL to an image representing the waste type. |
| `createdAt` | DateTime | Timestamp when the waste type was created.   |
| `updatedAt` | DateTime | Timestamp when the waste type was last updated.|

---

This endpoint is used to view all the waste types available in the decentralized waste management system.