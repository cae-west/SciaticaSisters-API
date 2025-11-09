# User exercise logs resource

**Base endpoint:**

```shell
{base_url}/userExerciseLogs
```

Contains information about exercise activities and pain tracking for users.

A user exercise logs resource describes exercise sessions recorded by users, including pain levels
before and after the activity. Each log must link to an existing user resource.

Learn more about the [users resource](users.md).

---

## Endpoints

- `GET /userExerciseLogs` - Get all exercise logs
- `GET /userExerciseLogs/{id}` - Get an exercise log by ID
- `GET /userExerciseLogs?userId={userId}` - Get exercise logs for a specific user
- `POST /userExerciseLogs` - Create a new exercise log
- `PUT /userExerciseLogs/{id}` - Update an exercise log by ID
- `PATCH /userExerciseLogs/{id}` - Update specific exercise log properties
- `DELETE /userExerciseLogs/{id}` - Delete an exercise log by ID

---

## Resource properties

**Sample user exercise logs resource:**

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

| Property name | Type | Description |
|---|---|---|
| `id` | number | The log's unique record ID |
| `userId` | number | The ID of the user who recorded this exercise |
| `exerciseType` | string | Exercise performed |
| `exerciseName` | string | Name of the exercise performed |
| `date` | string | Date of exercise - Year-Month-Day format |
| `painBefore` | number | Pain level before exercise on a scale of 1-10 |
| `painAfter` | number | Pain level after exercise on a scale of 1-10 |
| `effective` | boolean | Whether the exercise was effective - true/false |
| `notes` | string | More notes about the exercise session |

---

## Exercise type values

| Value | Description |
|---|---|
| `stretch` | Stretching exercise |
| `strengthening` | Strengthening exercise |
