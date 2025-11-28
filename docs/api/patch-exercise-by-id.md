---
layout: default
---

# Patch exercise log by ID

This operation updates or patches one or more properties of an existing exercise log by ID.

---

## Endpoint structure

```shell
PATCH /userExerciseLogs/{id}
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

Include only the properties you want to update. All fields are optional.

| Property | Type | Description |
|---|---|---|
| `userId` | integer | ID of the user who recorded this exercise |
| `exerciseType` | string | Exercise type - stretch or strengthening |
| `exerciseName` | string | Name of the exercise performed |
| `date` | string | Date performed - Year-Month-Day format |
| `painBefore` | integer | Pain level before exercise on a 1-10 scale |
| `painAfter` | integer | Pain level after exercise on a 1-10 scale |
| `effective` | boolean | Whether the exercise was effective |
| `notes` | string | More notes about the session |

---

## Example: Update effectiveness and notes

**Request:**

```bash
curl -X PATCH {base_url}/userExerciseLogs/1 \
  -H "Content-Type: application/json" \
  -d '{
    "effective": false,
    "notes": "Exercise caused discomfort. Will try alternative."
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
  "painAfter": 5,
  "effective": false,
  "notes": "Exercise caused discomfort. Will try alternative."
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

### Update pain levels only

```json
{
  "painBefore": 8,
  "painAfter": 6
}
```

### Update exercise name

```json
{
  "exerciseName": "Modified Piriformis Stretch"
}
```

---

## Related topics

- [Exercise logs resource page](user-exercise-logs.md)
- [Get exercise by ID](get-exercise-by-id.md)
- [Put exercise log by ID](put-exercise.md)
