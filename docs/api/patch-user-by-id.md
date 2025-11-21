---
layout: default
---

# Update a user by ID

This operation updates or patches one or more properties of an existing user by ID.

---

## Endpoint structure

```shell
PATCH /users/{id}
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

Include only the properties you want to update. All fields are optional.

| Property | Type | Description |
|---|---|---|
| `firstName` | string | User's first name |
| `lastName` | string | User's last name |
| `email` | string | User's email address |
| `age` | number | User's age |
| `painLocation` | string | Location of sciatica pain |
| `painLevel` | number | Current pain level on a 1-10 scale |
| `diagnosisDate` | string | Date of diagnosis - Year-Month-Day format |

---

## Curl request

```bash
curl -X PATCH http://localhost:3000/users/1 \
  -H "Content-Type: application/json" \
  -d '{
    "painLevel": 5
  }'
```

---

## Example: Update pain level

**Request:**

```bash
curl -X PATCH http://localhost:3000/users/1 \
  -H "Content-Type: application/json" \
  -d '{
    "painLevel": 5
  }'
```

**Response - Success:**

Returns the complete updated user object with all properties.

```json
{
  "id": 1,
  "firstName": "Sarah",
  "lastName": "Johnson",
  "email": "s.johnson@example.com",
  "age": 42,
  "painLocation": "lower-back-left",
  "painLevel": 5,
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

## More examples

### Update pain location and level

```json
{
  "painLocation": "glute-left",
  "painLevel": 6
}
```

### Update email address

```json
{
  "email": "sarah.j@newemail.com"
}
```

### Update many properties at once

```json
{
  "age": 43,
  "painLevel": 4,
  "painLocation": "lower-back-left"
}
```

---

## Related topics

- [Users resource](users.md)
- [Create new user](post-user.md)
- [Get user by ID](get-user-by-id.md)
