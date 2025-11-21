---
layout: default
---

# Tutorial: Compare exercises

In this tutorial, you'll learn how to retrieve and view exercise logs to see which activities helped
reduce pain.

Expect this tutorial to take about 10 minutes to complete.

## Before you start

Make sure you've completed the [Getting Started](../overview/getting-started.md) guide on the development
system you'll use for the tutorial.

## View exercise history

Viewing exercise history requires using the `GET` method to retrieve [user exercise logs](../api/user-exercise-logs.md)
for a specific user. By reviewing the logs, you can see the pain levels before and after each exercise.

This example retrieves all exercise logs for Sarah Johnson, user ID 1.

1. Make sure your local service is running, or start it by using this command in the terminal:

    ```shell
    cd <your-github-workspace>/SciaticaSisters-API/api
    json-server -w sciatica-sisters-db-source.json
    ```

2. Open Postman and create a new request:
   1. Click **New** > **HTTP** or the **+** icon in the header.
   2. Set the request method to `GET` using the corresponding dropdown menu.
   3. In the request URL field, enter:

      ```shell
      http://localhost:3000/userExerciseLogs
      ```

3. Filter by user ID:
   1. Click the **Params** tab below the URL field.
   2. Add a query parameter:
      - **Key:** `userId`
      - **Value:** `1`

   The query parameter filters the results by appending `?userId=1` to the URL. This returns only
   exercise logs for Sarah Johnson.

4. Click **Send** to make the request.

5. The system returns all exercise logs for Sarah Johnson. Review each log to see the `painBefore` and
`painAfter` values, along with the exercise `notes` and whether it's `effective`.

    ```json
    [
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
      },
      {
        "id": 2,
        "userId": 1,
        "exerciseType": "strengthening",
        "exerciseName": "Glute Bridges",
        "date": "2025-10-26",
        "painBefore": 6,
        "painAfter": 6,
        "effective": false,
        "notes": "No significant change"
      }
    ]
    ```

## Review the results

Looking at the exercise logs, you can see:

- **Piriformis Stretch**: Pain went from 7 to 5, marked as effective
- **Glute Bridges**: Pain stayed at 6, marked as not effective

The `painBefore` and `painAfter` fields show how pain levels changed with each exercise. The `effective`
field indicates whether the user felt the exercise helped. The `notes` field provides more context
about the experience.

## Filter by exercise type

You can also view only stretches or only strengthening exercises:

1. In the same Postman request, add a second query parameter:
   1. Click the **Params** tab.
   2. Add another parameter:
      - **Key:** `exerciseType`
      - **Value:** `stretch`
   3. Click **Send**.

2. This returns only stretch exercises for Sarah. You can change the value to `strengthening` to see
strengthening exercises instead.

## What you learned

After completing this tutorial, you now know how to retrieve and view exercise logs to see pain levels
before and after each activity. This helps users identify which exercises are working well for them.

## Next steps

- **[Log your first activity](log-first-activity.md)** to start tracking exercises.
- **[Update a user's pain level](update-pain-level.md)** when pain changes.
- **[Delete an exercise](delete-exercise.md)** to remove ineffective activities.

## Related topics

- **[Get exercise by ID](../api/get-exercise-by-id.md)**
- **[Update exercise by ID](../api/put-exercise.md)**
