# Tutorial: Create your first user profile

In this tutorial, you'll learn how to create a new user profile using the `POST` method to add a new
user to the Sciatica Sisters API.

Expect this tutorial to take about 10 minutes to complete.

## Before you start

Make sure you've completed the [Getting Started](../overview/getting-started.md) guide on the development
system you'll use for the tutorial.

## Create a new user profile

Creating a new user profile requires using the `POST` method to add a new [user](../api/users.md) resource
to the service. The `POST` method creates a new user with all required information.

This example creates a profile for a new user named Emma Davis.

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
      http://localhost:3000/users
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
        "firstName": "Emma",
        "lastName": "Davis",
        "email": "e.davis@example.com",
        "age": 45,
        "painLocation": "glute-right",
        "painLevel": 6,
        "diagnosisDate": "2025-01-15"
      }
      ```

5. Click **Send** to make the request.

6. The system returns the complete new user object with an assigned ID. Note that the system automatically
generates the `id` field.

    ```json
    {
      "id": 5,
      "firstName": "Emma",
      "lastName": "Davis",
      "email": "e.davis@example.com",
      "age": 45,
      "painLocation": "glute-right",
      "painLevel": 6,
      "diagnosisDate": "2025-01-15"
    }
    ```

## Verify your results

1. To confirm you created the user, retrieve all users:
   1. Create a new request in Postman.
   2. Set the request method to `GET`.
   3. In the request URL field, enter:

      ```shell
      http://localhost:3000/users
      ```

   4. Click **Send**.

2. You should see Emma Davis in the list of users with her assigned ID. The new user appears at the
end of the user list.

## What you learned

After completing this tutorial, you now know how to create a new user profile using the `POST` method
with Postman. This is the first step for any user who wants to track their sciatica pain and recovery
journey.

## Next steps

- **[Update a user's pain level](update-pain-level.md)** when pain changes.
- **[Log your first activity](log-first-activity.md)** to start tracking exercises.
- **[Compare exercises](compare-exercises.md)** to see which activities are effective.

## Related topics

- **[Get a user by ID](../api/get-user-by-id.md)**
- **[Update a user by ID](../api/patch-user-by-id.md)**
