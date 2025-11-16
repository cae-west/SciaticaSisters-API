---
layout: default
---

# Tutorial: Update a user's pain level

In this tutorial, you'll learn how to update a user's pain level using the `PATCH` method to
change a specific field in the user resource.

Expect this tutorial to take about 10 minutes to complete.

## Before you start

Make sure you've completed the [Getting Started](../overview/getting-started.md) guide on the
development system you'll use for the tutorial.

## Update a user's pain level

Updating a user's pain level requires using the `PATCH` method to change the [`user`](../api/users.md)
resource in the service. The `PATCH` method allows you to update specific fields without sending the
entire user object.

This example updates the pain level for a user from 7 to 4.

1. Make sure your local service is running, or start it by using this command in the terminal:

    ```shell
    cd <your-github-workspace>/SciaticaSisters-API/api
    json-server -w sciatica-sisters-db-source.json
    ```

2. Open Postman and create a new request:
   1. Click **New** > **HTTP** or the **+** icon in the header.
   2. Set the request method to `PATCH` using the corresponding dropdown menu.
   3. In the request URL field, enter:

      ```shell
      http://localhost:3000/users/1
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
        "painLevel": 4
      }
      ```

5. Click **Send** to make the request.

6. The system returns the complete updated user object with the new pain level. Note that only the `painLevel`
field changed, while all other fields remained the same.

    ```json
    {
      "id": 1,
      "firstName": "Sarah",
      "lastName": "Johnson",
      "email": "s.johnson@example.com",
      "age": 42,
      "painLocation": "lower-back-left",
      "painLevel": 4,
      "diagnosisDate": "2024-03-15"
    }
    ```

## Verify your results

1. To confirm the update was successful, retrieve the user's current information:
   1. Create a new request in Postman.
   2. Set the request method to `GET`.
   3. In the request URL field, enter:

      ```shell
      http://localhost:3000/users/1
      ```

   4. Click **Send**.

2. You should see that the `painLevel` is now 4 instead of the original value of 7. All other user
information remains unchanged.

## What you learned

After completing this tutorial, you now know how to update a specific field in a user resource using
the `PATCH` method with Postman. This is useful when a user reports changes to their pain level without
needing to update their entire profile.

## Next steps

- **[Log your first activity](log-first-activity.md)** to start tracking exercises.
- **[Compare exercises](compare-exercises.md)** to see which activities are effective.
- **[Create a user profile](create-user-profile.md)** to add a patient.

## Related topics

- **[Update exercise by ID](../api/put-exercise.md)**
- **[Delete an exercise](../api/delete-exercise.md)**
