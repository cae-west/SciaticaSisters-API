---
layout: default
---

# Put user by ID

This operation replaces all properties of an existing user by ID.

---

## Endpoint structure

```shell
PUT /users/{id}
```

---

## Path parameters

| Parameter | Type | Required | Description |
|---|---|---|---|
| `id` | integer | Yes | The unique identifier of the user to update |

---

## Request headers

| Header | Value | Required |
|---|---|---|
| `Content-Type` | `application/json` | Yes |

---

## Request body

All fields required for a `PUT` operation.

| Property | Type | Required | Description |
|---|---|---|---|
| `firstName` | string | Yes | User's first name |
| `lastName` | string | Yes | User's last name |
| `email` | string | Yes | User's email address |
| `age` | integer | Yes | User's age |
| `painLocation` | string | Yes | Location of sciatica pain |
| `painLevel` | integer | Yes | Current pain level on a 1-10 scale |
| `diagnosisDate` | string | Yes | Date of diagnosis - Year-Month-Day format |

---

## Example request

**Request:**

```bash
curl -X PUT {base_url}/users/1 \
  -H "Content-Type: application/json" \
  -d '{
    "firstName": "Sarah",
    "lastName": "Martinez",
    "email": "s.martinez@example.com",
    "age": 43,
    "painLocation": "glute-left",
    "painLevel": 4,
    "diagnosisDate": "2024-03-15"
  }'
```

**Response - Success:**

Returns the complete updated user object with all properties.

```json
{
  "id": 1,
  "firstName": "Sarah",
  "lastName": "Martinez",
  "email": "s.martinez@example.com",
  "age": 43,
  "painLocation": "glute-left",
  "painLevel": 4,
  "diagnosisDate": "2024-03-15"
}
```

**Successful response includes:**

- `id` - User identifier - unchanged
- `firstName` - User's first name
- `lastName` - User's last name
- `email` - User's email address
- `age` - User's age
- `painLocation` - Location of sciatica pain
- `painLevel` - Current pain level on a 1-10 scale
- `diagnosisDate` - Date of sciatica diagnosis

---

## Related topics

- [Users resource](users.md)
- [Get user by ID](get-user-by-id.md)
- [Patch user by ID](patch-user-by-id.md)
