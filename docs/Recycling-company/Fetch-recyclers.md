---
sidebar_position: 4
---

# Fetch Recyclers

This endpoint retrieves a list of all registered recycling companies, along with their details.

---

## URL

`{{base_url}}/company`

## Method

`GET`

## Headers

| Header        | Value                                 | Description                      |
|---------------|---------------------------------------|----------------------------------|
| `x-api-key`   | `your-api-key`                       | API key for authentication.     |

---

## Request Parameters

This endpoint does not require any request body or query parameters.

**Example Request:**

```bash
curl --location '{{base_url}}/company' \
--header 'x-api-key: c144fca11d1c9453d319eb71a823fca1a6facffa9b534cd6b825c36e57346c40'
```

---

## Response

### Success Response

```json
{
    "success": true,
    "message": "Companies",
    "data": [
        {
            "location": {
                "type": "Point",
                "coordinates": [
                    3.3795833587646484,
                    6.541319662928253
                ]
            },
            "_id": "673db788b42772f4b600fbec",
            "companyId": 2,
            "companyName": "CCMI",
            "email": "layintondeveloper@gmail.com",
            "phoneNumber": "08168075718",
            "physicalAddress": "1 Bawala St, Pedro, Lagos 102216, Lagos, Nigeria",
            "companyLogo": "http://res.cloudinary.com/dydpvzju9/image/upload/v1732097925/fknkzoi2leb3zsdmyst6.png",
            "licenseDocument": "http://res.cloudinary.com/dydpvzju9/image/upload/v1732097926/ndmebihqnc9jz4sk58xh.png",
            "createdAt": "2024-11-20T10:18:48.607Z",
            "updatedAt": "2024-11-20T10:18:48.607Z",
            "__v": 0
        },
        {
            "location": {
                "type": "Point",
                "coordinates": [
                    3.5299573838710785,
                    6.584318842686981
                ]
            },
            "_id": "673dcd34af9dae5366a81862",
            "companyId": 0,
            "companyName": "Green Cycle Plus",
            "email": "michojekunle1@gmail.com",
            "phoneNumber": "09045156850",
            "physicalAddress": "HGMJ+M9G, Ikorodu, 104102, Lagos, Nigeria",
            "companyLogo": "http://res.cloudinary.com/dydpvzju9/image/upload/v1732103469/zauvyuk1sqswxxzo6vzi.png",
            "licenseDocument": "http://res.cloudinary.com/dydpvzju9/image/upload/v1732103474/jvnwy72qusemqzqqirmq.png",
            "createdAt": "2024-11-20T11:51:16.625Z",
            "updatedAt": "2024-11-20T11:51:16.625Z",
            "__v": 0
        },
        {
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
        {
            "location": {
                "type": "Point",
                "coordinates": [
                    3.5308016142074226,
                    6.571665072719812
                ]
            },
            "_id": "673f0749a7f15222cae6404f",
            "companyId": 105,
            "companyName": "Reliableii Cycle",
            "email": "company6@gmail.com",
            "phoneNumber": "08155319081",
            "physicalAddress": "Bayeiku Road",
            "companyLogo": null,
            "licenseDocument": "http://gateway.cloud/ipfs/xxxx",
            "createdAt": "2024-11-21T10:11:21.036Z",
            "updatedAt": "2024-11-21T10:11:21.036Z",
            "__v": 0
        },
        {
            "location": {
                "type": "Point",
                "coordinates": [
                    3.3764290809631348,
                    6.536693639469109
                ]
            },
            "_id": "673f1d5fb0f57446f5c64aef",
            "companyId": 1,
            "companyName": "CCMI2",
            "email": "layintondev12@gmail.com",
            "phoneNumber": "07048027285",
            "physicalAddress": "12 Odubanjo St, Somolu, Lagos 102216, Lagos, Nigeria",
            "companyLogo": "http://res.cloudinary.com/dydpvzju9/image/upload/v1732189531/bptnvucjmcitvq4riaul.png",
            "licenseDocument": "http://res.cloudinary.com/dydpvzju9/image/upload/v1732189534/ers3m3atk0pk6jjsl3qm.png",
            "createdAt": "2024-11-21T11:45:35.588Z",
            "updatedAt": "2024-11-21T11:45:35.588Z",
            "__v": 0
        }
    ]
}
```

--- 

This endpoint provides a comprehensive list of all registered recycling companies with relevant details for each.