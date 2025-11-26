---
layout: default
---

# Getting started

---

## About the API

- **HTTP method**: Local service at `http://localhost:3000` is accessible at your configured `{base_url}`
- **Data format**: JSON for all requests and responses
- **Server**: This API runs on your local machine or your chosen server environment
- **Authentication**: See [Authentication](authentication.md) for more information

---

## Prerequisites

To use the Sciatica Sisters API, you need:

- A [GitHub](https://github.com/) account
- [Git](https://git-scm.com/downloads)
- [node.js](https://nodejs.org/en/download)
- [json-server](https://www.npmjs.com/package/json-server)
- [curl](https://curl.se/download.html) or [Postman desktop app](https://www.postman.com/downloads/)

---

## Set up the API

1. Fork the [Sciatica Sisters API repository](https://github.com/cae-west/SciaticaSisters-API)
2. Clone your fork to your local machine
3. Open your terminal and navigate to the repository:

   ```bash
   cd SciaticaSisters-API/api
   ```

4. Start the JSON server:

   ```bash
   json-server -w sciatica-sisters-db-source.json
   ```

5. You should see the server running at `http://localhost:3000`

---

## Curl testing

Open a new terminal window and run:

```bash
curl {base_url}/users
```

For local development, use:

```bash
curl http://localhost:3000/users
```

You should see a list of users in JSON format.

---

## Postman testing

1. Open the Postman desktop app
2. Create a new request
3. Set method to `GET`
4. Enter URL: `{base_url}/users` or `http://localhost:3000/users` for local testing
5. Click **Send**

You should see a list of users in the response.
