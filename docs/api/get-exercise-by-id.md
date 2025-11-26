---
layout: default
---

# Get exercise log by ID

This operation retrieves a specific exercise log by its ID.

---

## Endpoint structure

```shell
GET /users/{id}
```

---

## Path parameters

| Parameter | Type | Required | Description |
|---|---|---|---|
| `id` | integer | Yes | The unique identifier of the exercise log to retrieve |

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
curl -X GET {base_url}/userExerciseLogs/1
```

**Response - Success:**

Returns the exercise log object with the specified ID.

```json
{
  "id": 1,
  "userId": 1,
  "exerciseType": "stretch",
  "exerciseName": "Piriformis Stretch",
  "date": "2025-10-24",
  "painBefore": 7,
  "painAfter": 5,
  "effective": true,
  "notes": "Felt immediate relief in glute area"
}
```

**Successful response includes:**

- `id` - Unique exercise log identifier
- `userId` - ID of the user who recorded this exercise
- `exerciseType` - Exercise type - stretch or strengthening
- `exerciseName` - Name of the exercise performed
- `date` - Date of exercise - Year-Month-Day format
- `painBefore` - Pain level before exercise on a 1-10 scale
- `painAfter` - Pain level after exercise on a 1-10 scale
- `effective` - Whether the exercise was effective - true/false
- `notes` - More notes about the exercise session

---

## Related topics

- [Exercise logs resource page](user-exercise-logs.md)
- [Put exercise log by ID](put-exercise.md)
- [Delete exercise log by ID](delete-exercise.md)
