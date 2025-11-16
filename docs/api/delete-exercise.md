---
layout: default
---

# Delete an exercise log by ID

This operation deletes an exercise log by ID.

---

## Endpoint structure

```shell
DELETE /userExerciseLogs/{id}
```

---

## Path parameters

| Parameter | Type | Required | Description |
|---|---|---|---|
| `id` | integer | Yes | Unique identifier of exercise log to delete |

---

## Request headers

| Header | Value | Required |
|---|---|---|
| `Content-Type` | `application/json` | No |

---

## Request body

This operation doesn't require a request body.

---

## Curl request

```bash
curl -X DELETE http://localhost:3000/userExerciseLogs/1
```

---

## Example request

**Request:**

```bash
curl -X DELETE http://localhost:3000/userExerciseLogs/1
```

**Response - Success:**

Returns an empty JSON object `{}`.

```json
{}
```

---

## Related topics

- [Exercise logs resource page](user-exercise-logs.md)
- [Get exercise log by ID](get-exercise-by-id.md)
- [Update exercise by ID](put-exercise.md)
