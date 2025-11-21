---
layout: default
---

# Put exercise log by ID

This operation replaces all properties of an existing exercise log by ID.

---

## Endpoint structure

```shell
PUT /userExerciseLogs/{id}
```

---

## Path parameters

| Parameter | Type | Required | Description |
|---|---|---|---|
| `id` | integer | Yes | The unique identifier of the exercise log to update |

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
| `userId` | number | Yes | ID of the user who recorded this exercise |
| `exerciseType` | string | Yes | Exercise type - stretch or strengthening |
| `exerciseName` | string | Yes | Name of the exercise performed |
| `date` | string | Yes | Date performed - Year-Month-Day format |
| `painBefore` | number | Yes | Pain level before exercise on a 1-10 scale |
| `painAfter` | number | Yes | Pain level after exercise on a 1-10 scale |
| `effective` | boolean | Yes | Whether the exercise was effective |
| `notes` | string | Yes | More notes about the session |

---

## Example: Update complete exercise log

**Request:**

```bash
curl -X PUT {base_url}/userExerciseLogs/1 \
  -H "Content-Type: application/json" \
  -d '{
    "userId": 1,
    "exerciseType": "stretch",
    "exerciseName": "Piriformis Stretch",
    "date": "2025-10-24",
    "painBefore": 7,
    "painAfter": 4,
    "effective": true,
    "notes": "Felt immediate relief in glute area. Held stretch for 45 seconds."
  }'
```

**Response - Success:**

Returns the complete updated exercise log object with all properties.

```json
{
  "id": 1,
  "userId": 1,
  "exerciseType": "stretch",
  "exerciseName": "Piriformis Stretch",
  "date": "2025-10-24",
  "painBefore": 7,
  "painAfter": 4,
  "effective": true,
  "notes": "Felt immediate relief in glute area. Held stretch for 45 seconds."
}
```

**Successful response includes:**

- `id` - Exercise log identifier - unchanged
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

### Update log with different exercise type

```json
{
  "userId": 2,
  "exerciseType": "strengthening",
  "exerciseName": "Pelvic Tilts",
  "date": "2025-10-28",
  "painBefore": 6,
  "painAfter": 5,
  "effective": true,
  "notes": "Completed 3 sets of 15 reps"
}
```

### Update log marking exercise as not effective

```json
{
  "userId": 3,
  "exerciseType": "stretch",
  "exerciseName": "Cobra Stretch",
  "date": "2025-10-29",
  "painBefore": 8,
  "painAfter": 8,
  "effective": false,
  "notes": "No change in pain level. Will try different stretch tomorrow."
}
```

---

## Related topics

- [Exercise logs resource page](user-exercise-logs.md)
- [Get exercise log by ID](get-exercise-by-id.md)
- [Delete exercise log by ID](delete-exercise.md)
