---
layout: default
---

# Tutorial: Remove an exercise log

In this tutorial, you'll learn how to remove an exercise log using the `DELETE` method to remove entries
that are no longer needed. By eliminating logs of ineffective exercises, you can maintain a clear picture
of what's actually helping a user's recovery.

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

### Postman request

1. Open Postman and create a new request:
   1. Click **New** > **HTTP** or the **+** icon in the header.
   2. Set the request method to `DELETE` using the corresponding dropdown menu.
   3. In the request URL field, enter:

      ```shell
      {base_url}/userExerciseLogs/2
      ```

2. Click **Send** to make the request.

3. The system returns an empty object, confirming the deletion was successful.

    ```json
    {}
    ```

### cURL request

1. Open your terminal and run this command:

   ```bash
   curl -X DELETE {base_url}/userExerciseLogs/2
   ```

2. The system returns an empty object, confirming the deletion was successful.

    ```json
    {}
    ```

## Check your results

### Postman verification

1. Create a new request in Postman.
2. Set the request method to `GET`.
3. In the request URL field, enter:

   ```shell
   {base_url}/userExerciseLogs?userId=1
   ```

4. Click **Send**.

5. You should see that the Glute Bridges exercise log, ID 2, no longer appears in the list. You should
only see the remaining exercise logs returned for Sarah Johnson.

### Using cURL

1. Run this command:

   ```bash
   curl -X GET "{base_url}/userExerciseLogs?userId=1"
   ```

2. You should see that the Glute Bridges exercise log, ID 2, no longer appears in the list. You should
only see the remaining exercise logs returned for Sarah Johnson.

## Common errors and troubleshooting

### 404 not found error

If you receive this error, the exercise log ID you're trying to delete doesn't exist. Check for the
correct log ID by calling `GET` on `/userExerciseLogs` first to see all available logs.

### Wrong log deleted

Double-check the ID in your `DELETE` request URL. If you accidentally delete the wrong log, you'll need
to recreate it using the `POST` method, as deletions can't be undone.

### Log still appears after deletion

If the log still appears when you retrieve the list, your `GET` request may be returning cached data.
Try adding a timestamp query parameter like `?_t=123456` to force a fresh request.

## What you learned

After completing this tutorial, you now know how to remove an exercise log using the `DELETE` method
with Postman or cURL. This is useful for removing exercises that didn't help or for cleaning up incorrect
entries. You're maintaining a focused, accurate record of a user's healing journey.

## Next steps

- **[Log your first activity](log-first-activity.md)** to start tracking exercises.
- **[Compare exercises](compare-exercises.md)** to see which activities are effective.
- **[Update a user's pain level](update-pain-level.md)** when pain changes.

## Related topics

- **[Get exercise log by ID](../api/get-exercise-by-id.md)**
- **[Put exercise log by ID](../api/put-exercise.md)**

## Security note

In a production environment, this operation would require proper authentication to ensure only
authorized users can change patient data. See [Authentication](../overview/authentication.md) for details.
