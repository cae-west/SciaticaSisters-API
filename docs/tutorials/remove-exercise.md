# Tutorial: Remove an exercise log

In this tutorial, you'll learn how to remove an exercise log using the `DELETE` method to remove entries
that are no longer needed.

Expect this tutorial to take about 10 minutes to complete.

## Before you start

Make sure you've completed the [Getting Started](../overview/getting-started.md) guide on the development
system you'll use for the tutorial.

## Remove an exercise log

Deleting an exercise log requires using the `DELETE` method to remove a [user exercise log](../api/user-exercise-logs.md)
resource from the service. This is useful when you want to remove entries that weren't effective.

This example removes the Glute Bridges exercise log, ID 2, which wasn't effective for Sarah Johnson.

1. Make sure your local service is running, or start it by using this command in the terminal:

    ```shell
    cd <your-github-workspace>/SciaticaSisters-API/api
    json-server -w sciatica-sisters-db-source.json
    ```

2. Open Postman and create a new request:
   1. Click **New** > **HTTP** or the **+** icon in the header.
   2. Set the request method to `DELETE` using the corresponding dropdown menu.
   3. In the request URL field, enter:

      ```shell
      http://localhost:3000/userExerciseLogs/2
      ```

3. Click **Send** to make the request.

4. The system returns an empty object, confirming the deletion was successful.

    ```json
    {}
    ```

## Verify your results

1. To confirm you removed the exercise log, retrieve all logs for Sarah Johnson:
   1. Create a new request in Postman.
   2. Set the request method to `GET`.
   3. In the request URL field, enter:

      ```shell
      http://localhost:3000/userExerciseLogs?userId=1
      ```

   4. Click **Send**.

2. You should see that the Glute Bridges exercise log, ID 2, no longer appears in the list. You should
only see the remaining exercise logs returned for Sarah Johnson.

## What you learned

After completing this tutorial, you now know how to remove an exercise log using the `DELETE` method
with Postman. This is useful for removing exercises that didn't help or for cleaning up incorrect entries.

## Next steps

- **[Log your first activity](log-first-activity.md)** to start tracking exercises.
- **[Compare exercises](compare-exercises.md)** to see which activities are effective.
- **[Update a user's pain level](update-pain-level.md)** when pain changes.

## Related topics

- **[Get exercise by ID](../api/get-exercise-by-id.md)**
- **[Update exercise by ID](../api/put-exercise.md)**
