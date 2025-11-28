---
layout: default
---

# Delete user by ID

This operation deletes a user profile by ID.

---

## Endpoint structure

```shell
DELETE /users/{id}
```

---

## Path parameters

| Parameter | Type | Required | Description |
|---|---|---|---|
| `id` | integer | Yes | The unique identifier of the user to delete |

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
curl -X DELETE {base_url}/users/1
```

**Response - Success:**

Returns an empty JSON object `{}`.

```json
{}
```

---

## Related topics

- [Users resource](users.md)
- [Get user by ID](get-user-by-id.md)
- [Create new user](post-user.md)
