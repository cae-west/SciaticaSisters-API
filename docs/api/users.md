---
layout: default
---

# Users resource

**Base endpoint:**

```shell
{base_url}/users
```

Contains information about users of the Sciatica Sisters API.

A user resource describes individuals tracking their sciatica pain and recovery. Before you can create
exercise logs in the service, you must create a user resource to assign to the logs.

Learn more about the [user exercise logs resource](user-exercise-logs.md).

---

## Endpoints

- `GET /users` - Get all users
- `GET /users/{id}` - Get a user by ID
- `POST /users` - Create a new user
- `PUT /users/{id}` - Update a user by ID
- `PATCH /users/{id}` - Update specific user properties
- `DELETE /users/{id}` - Delete a user by ID

---

## Resource properties

**Sample user resource:**

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

| Property name | Type | Description |
|---|---|---|
| `id` | integer | The user's unique record ID |
| `firstName` | string | The user's first name |
| `lastName` | string | The user's last name |
| `email` | string | The user's email address |
| `age` | integer | The user's age |
| `painLocation` | string | Location of the user's sciatica pain |
| `painLevel` | integer | Current pain level on a scale of 1-10 |
| `diagnosisDate` | string | Date of sciatica diagnosis - Year-Month-Day format |

---

## Pain location values

| Value | Description |
|---|---|
| `lower-back-left` | Lower left back |
| `lower-back-right` | Lower right back |
| `glute-left` | Left glute area |
| `glute-right` | Right glute area |
| `calf-left` | Left calf |
| `calf-right` | Right calf |
