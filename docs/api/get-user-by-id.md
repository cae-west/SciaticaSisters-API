---
layout: default
---

# Get user by ID

This operation retrieves a specific user profile by its ID.

---

## Endpoint structure

```shell
GET /users/{id}
```

---

## Path parameters

| Parameter | Type | Required | Description |
|---|---|---|---|
| `id` | integer | Yes | The unique identifier of the user to retrieve |

---

## Request headers

| Header | Value | Required |
|---|---|---|
| `Content-Type` | `application/json` | No |

---

## Request body

This operation doesn't require a request body.

---

## Example request

**Request:**

```bash
curl -X GET {base_url}/users/1
```

**Response - Success:**

Returns the user object with the specified ID.

```json
{
  "id": 1,
  "firstName": "Sarah",
  "lastName": "Johnson",
  "email": "s.johnson@example.com",
  "age": 42,
  "painLocation": "lower-back-left",
  "painLevel": 7,
  "diagnosisDate": "2024-03-15"
}
```

**Successful response includes:**

- `id` - Unique user identifier
- `firstName` - User's first name
- `lastName` - User's last name
- `email` - User's email address
- `age` - User's age
- `painLocation` - Location of sciatica pain
- `painLevel` - Current pain level on a 1-10 scale
- `diagnosisDate` - Date of sciatica diagnosis - Year-Month-Day format

---

## Related topics

- [Users resource](users.md)
- [Post a new user](post-user.md)
- [Patch user by ID](patch-user-by-id.md)
