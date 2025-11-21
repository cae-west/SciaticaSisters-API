---
layout: default
---

# Create a new user

This operation creates a new user profile in the service.

---

## Endpoint structure

```shell
POST /users
```

---

## Request headers

| Header | Value | Required |
|---|---|---|
| `Content-Type` | `application/json` | Yes |

---

## Request body

All fields required unless marked as optional.

| Property | Type | Required | Description |
|---|---|---|---|
| `firstName` | string | Yes | User's first name |
| `lastName` | string | Yes | User's last name |
| `email` | string | Yes | User's email address |
| `age` | number | Yes | User's age |
| `painLocation` | string | Yes | Location of sciatica pain |
| `painLevel` | number | Yes | Current pain level on a 1-10 scale |
| `diagnosisDate` | string | Yes | Date of diagnosis - Year-Month-Day format |

---

## Curl request

```bash
curl -X POST http://localhost:3000/users \
  -H "Content-Type: application/json" \
  -d '{
    "firstName": "Emma",
    "lastName": "Davis",
    "email": "e.davis@example.com",
    "age": 45,
    "painLocation": "glute-right",
    "painLevel": 6,
    "diagnosisDate": "2025-01-15"
  }'
```

---

## Example request

**Request:**

```bash
curl -X POST http://localhost:3000/users \
  -H "Content-Type: application/json" \
  -d '{
    "firstName": "Emma",
    "lastName": "Davis",
    "email": "e.davis@example.com",
    "age": 45,
    "painLocation": "glute-right",
    "painLevel": 6,
    "diagnosisDate": "2025-01-15"
  }'
```

**Response - Success:**

Returns the newly created user object with all properties including the assigned ID.

```json
{
  "id": 5,
  "firstName": "Emma",
  "lastName": "Davis",
  "email": "e.davis@example.com",
  "age": 45,
  "painLocation": "glute-right",
  "painLevel": 6,
  "diagnosisDate": "2025-01-15"
}
```

**Successful response includes:**

- `id` - Newly assigned unique user identifier
- `firstName` - User's first name
- `lastName` - User's last name
- `email` - User's email address
- `age` - User's age
- `painLocation` - Location of sciatica pain
- `painLevel` - Current pain level on a 1-10 scale
- `diagnosisDate` - Date of sciatica diagnosis

---

## More examples

### Create user with lower back pain

```json
{
  "firstName": "John",
  "lastName": "Martinez",
  "email": "j.martinez@example.com",
  "age": 38,
  "painLocation": "lower-back-right",
  "painLevel": 8,
  "diagnosisDate": "2024-12-01"
}
```

### Create user with calf pain

```json
{
  "firstName": "Lisa",
  "lastName": "Chen",
  "email": "l.chen@example.com",
  "age": 29,
  "painLocation": "calf-left",
  "painLevel": 4,
  "diagnosisDate": "2025-02-10"
}
```

---

## Related topics

- [Users resource](users.md)
- [Get user by ID](get-user-by-id.md)
- [Update user by ID](patch-user-by-id.md)
