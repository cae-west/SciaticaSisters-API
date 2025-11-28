---
layout: default
---

# Tutorial: Update a user's pain level

In this tutorial, you'll learn how to update a user's pain level using the `PATCH` method to change
a specific field in the user resource. Whether a user's pain increases or decreases, keeping this
information current helps them track and change their recovery approach, if necessary.

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

### Postman request

1. Open Postman and create a new request:
   1. Click **New** > **HTTP** or the **+** icon in the header.
   2. Set the request method to `PATCH` using the corresponding dropdown menu.
   3. In the request URL field, enter:

      ```shell
      {base_url}/users/1
      ```

2. Set up the request headers:
   1. Click the **Headers** tab below the URL field.
   2. Add a header:
      - **Key:** `Content-Type`
      - **Value:** `application/json`

3. Set up the request body:
   1. Click the **Body** tab below the URL field.
   2. Select **raw** from the radio button options.
   3. Select **JSON** from the dropdown menu on the right.
   4. In the text area, enter:

      ```json
      {
        "painLevel": 4
      }
      ```

4. Click **Send** to make the request.

5. The system returns the complete updated user object with the new pain level. Note that only the `painLevel`
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

### cURL request

1. Open your terminal and run this command:

   ```bash
   curl -X PATCH {base_url}/users/1 \
     -H "Content-Type: application/json" \
     -d '{"painLevel": 4}'
   ```

2. The system returns the complete updated user object with the new pain level. Note that only the `painLevel`
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

## Check your results

### Postman verification

1. Create a new request in Postman.
2. Set the request method to `GET`.
3. In the request URL field, enter:

   ```shell
   {base_url}/users/1
   ```

4. Click **Send**.

5. You should see that the `painLevel` is now 4 instead of the original value of 7. All other user
information remains unchanged.

### cURL verification

1. Run this command:

   ```bash
   curl -X GET {base_url}/users/1
   ```

2. You should see that the `painLevel` is now 4 instead of the original value of 7. All other user
information remains unchanged.

## Common errors and troubleshooting

### Pain level not updating

If the pain level doesn't change, verify you're using the correct field name `painLevel` in camelCase.
Using `pain_level`, `PainLevel`, or other variations won't work.

### Invalid pain level value

The pain level must be a number between 1 and 10. Values outside this range or non-numeric values
may cause errors or unexpected behavior.

### 404 not found error

If you receive this error, the user ID in your request URL doesn't exist. Verify the correct user ID
by calling `GET` on `/users` first to see all available users.

## What you learned

After completing this tutorial, you now know how to update a specific field in a user resource using
the `PATCH` method with Postman or cURL. This is useful when a user reports changes to their pain level
without needing to update their entire profile. You're now able to accurately track user progress.

## Next steps

- **[Log your first activity](log-first-activity.md)** to start tracking exercises.
- **[Compare exercises](compare-exercises.md)** to see which activities are effective.
- **[Create a user profile](create-user-profile.md)** to add a patient.

## Related topics

- **[Put exercise log by ID](../api/put-exercise.md)**
- **[Delete exercise log by ID](../api/delete-exercise.md)**

## Security note

In a production environment, this operation would require proper authentication to ensure only
authorized users can change patient data. See [Authentication](../overview/authentication.md) for details.
