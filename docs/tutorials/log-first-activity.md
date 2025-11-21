---
layout: default
---

# Tutorial: Log your first activity

In this tutorial, you'll learn how to create an exercise log using the `POST` method to track your pain
levels before and after an activity.

Expect this tutorial to take about 10 minutes to complete.

## Before you start

Make sure you've completed the [Getting Started](../overview/getting-started.md) guide on the development
system you'll use for the tutorial.

## Log an exercise activity

Logging an exercise activity requires using the `POST` method to add a new [user exercise log](../api/user-exercise-logs.md)
resource to the service. The `POST` method creates a new log entry with pain levels, exercise details,
and notes.

This example logs a Piriformis Stretch performed by Sarah Johnson, user ID 1.

1. Make sure your local service is running, or start it by using this command in the terminal:

    ```shell
    cd <your-github-workspace>/SciaticaSisters-API/api
    json-server -w sciatica-sisters-db-source.json
    ```

2. Open Postman and create a new request:
   1. Click **New** > **HTTP** or the **+** icon in the header.
   2. Set the request method to `POST` using the corresponding dropdown menu.
   3. In the request URL field, enter:

      ```shell
      http://localhost:3000/userExerciseLogs
      ```

3. Set up the request headers:
   1. Click the **Headers** tab below the URL field.
   2. Add a header:
      - **Key:** `Content-Type`
      - **Value:** `application/json`

4. Set up the request body:
   1. Click the **Body** tab below the URL field.
   2. Select **raw** from the radio button options.
   3. Select **JSON** from the dropdown menu on the right.
   4. In the text area, enter:

      ```json
      {
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

5. Click **Send** to make the request.

6. The system returns the complete new exercise log with an assigned ID. Note that the system automatically
generates the `id` field.

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

## Verify your results

1. To confirm you successfully created the exercise log, retrieve all logs for the user:
   1. Create a new request in Postman.
   2. Set the request method to `GET`.
   3. In the request URL field, enter:

      ```shell
      http://localhost:3000/userExerciseLogs?userId=1
      ```

   4. Click **Send**.

2. You should see the new exercise log in the list for Sarah Johnson. The log shows the pain reduction
from 7 to 5.

## What you learned

After completing this tutorial, you now know how to log an exercise activity using the `POST` method
with Postman. This allows users to track which exercises help reduce their pain over time.

## Next steps

- **[Update a user's pain level](update-pain-level.md)** when pain changes.
- **[Compare exercises](compare-exercises.md)** to see which activities are effective.
- **[Remove an exercise](remove-exercise.md)** to remove ineffective activities.

## Related topics

- **[Get exercise by ID](../api/get-exercise-by-id.md)**
- **[Update exercise by ID](../api/put-exercise.md)**
