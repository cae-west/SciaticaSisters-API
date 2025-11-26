---
layout: default
---

# Tutorial: Update a user profile

In this tutorial, you'll learn how to update a complete user profile using the `PUT` method to reflect
major changes in a user's condition.

Expect this tutorial to take about 10 minutes to complete.

## Before you start

Make sure you've completed the [Getting Started](../overview/getting-started.md) guide on the development
system you'll use for the tutorial.

## Update a complete user profile

Updating a complete user profile requires using the `PUT` method to replace all fields in a [user](../api/users.md)
resource. The `PUT` method replaces the entire user profile with new information.

This example updates the profile for Sarah Johnson, user ID 1, after most of her information changed.
She has gotten married and needs to update her last name and email. She also needs to revise her
age and current pain information.

1. Make sure your local service is running, or start it by using this command in the terminal:

    ```shell
    cd <your-github-workspace>/SciaticaSisters-API/api
    json-server -w sciatica-sisters-db-source.json
    ```

2. Open Postman and create a new request:
   1. Click **New** > **HTTP** or the **+** icon in the header.
   2. Set the request method to `PUT` using the corresponding dropdown menu.
   3. In the request URL field, enter:

      ```shell
      {base_url}/users/1
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
        "firstName": "Sarah",
        "lastName": "Martinez",
        "email": "s.martinez@example.com",
        "age": 43,
        "painLocation": "lower-lumbar",
        "painLevel": 4,
        "diagnosisDate": "2025-10-15"
      }
      ```

5. Click **Send** to make the request.

6. The system returns the complete updated user profile. Note that many fields have changed to the
new values, while the `id` remains the same.

    ```json
    {
      "id": 1,
      "firstName": "Sarah",
      "lastName": "Martinez",
      "email": "s.martinez@example.com",
      "age": 43,
      "painLocation": "lower-lumbar",
      "painLevel": 4,
      "diagnosisDate": "2025-10-15"
    }
    ```

## Verify your results

1. To confirm the user profile changed successfully, retrieve the user's current information:
   1. Create a new request in Postman.
   2. Set the request method to `GET`.
   3. In the request URL field, enter:

      ```shell
      {base_url}/users/1
      ```

   4. Click **Send**.

2. You should see the user profile with Sarah's updated last name, email address, age, pain location,
and pain level.

## What you learned

After completing this tutorial, you now know how to update a complete user profile using the `PUT`
method with Postman. This is useful when many user details change at once, such as after a medical
checkup or major life event. For updating just one field, like pain level only, use the `PATCH`
method instead.

## Next steps

- **[Update a user's pain level](update-pain-level.md)** when pain changes.
- **[Create a user profile](create-user-profile.md)** to add a patient.
- **[Compare exercises](compare-exercises.md)** to see which activities are effective.

## Related topics

- **[Get user by ID](../api/get-user-by-id.md)**
- **[Patch user by ID](../api/patch-user-by-id.md)**

## Security note

In a production environment, this operation would require proper authentication to ensure only
authorized users can change patient data. See [Authentication](../overview/authentication.md) for details.
  