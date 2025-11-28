---
layout: default
---

# Post a new exercise log

This operation creates a new exercise log in the service.

---

## Endpoint structure

```shell
POST /userExerciseLogs
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
| `userId` | integer | Yes | ID of the user who recorded this exercise |
| `exerciseType` | string | Yes | Exercise type - stretch or strengthening |
| `exerciseName` | string | Yes | Name of the exercise performed |
| `date` | string | Yes | Date performed - Year-Month-Day format |
| `painBefore` | integer | Yes | Pain level before exercise on a 1-10 scale |
| `painAfter` | integer | Yes | Pain level after exercise on a 1-10 scale |
| `effective` | boolean | Yes | Whether the exercise was effective |
| `notes` | string | Yes | More notes about the session |

---

## Example request

**Request:**

```bash
curl -X POST {base_url}/userExerciseLogs \
  -H "Content-Type: application/json" \
  -d '{
    "userId": 1,
    "exerciseType": "stretch",
    "exerciseName": "Piriformis Stretch",
    "date": "2025-11-14",
    "painBefore": 7,
    "painAfter": 5,
    "effective": true,
    "notes": "Felt immediate relief in glute area"
  }'
```

**Response - Success:**

Returns the newly created exercise log object with all properties including the assigned ID.

```json
{
  "id": 5,
  "userId": 1,
  "exerciseType": "stretch",
  "exerciseName": "Piriformis Stretch",
  "date": "2025-11-14",
  "painBefore": 7,
  "painAfter": 5,
  "effective": true,
  "notes": "Felt immediate relief in glute area"
}
```

**Successful response includes:**

- `id` - Newly assigned unique exercise log identifier
- `userId` - ID of the user who recorded this exercise
- `exerciseType` - Exercise type performed
- `exerciseName` - Name of the exercise performed
- `date` - Date of exercise
- `painBefore` - Pain level before exercise on a 1-10 scale
- `painAfter` - Pain level after exercise on a 1-10 scale
- `effective` - Whether the exercise was effective
- `notes` - More notes about the session

---

## More examples

### Log strengthening exercise

```json
{
  "userId": 2,
  "exerciseType": "strengthening",
  "exerciseName": "Glute Bridges",
  "date": "2025-11-15",
  "painBefore": 6,
  "painAfter": 4,
  "effective": true,
  "notes": "Completed 3 sets of 12 reps"
}
```

### Log ineffective exercise

```json
{
  "userId": 3,
  "exerciseType": "stretch",
  "exerciseName": "Cobra Stretch",
  "date": "2025-11-16",
  "painBefore": 8,
  "painAfter": 8,
  "effective": false,
  "notes": "No change in pain level"
}
```

---

## Related topics

- [Exercise logs resource page](user-exercise-logs.md)
- [Get exercise by ID](get-exercise-by-id.md)
- [Patch exercise log by ID](patch-exercise-by-id.md)
