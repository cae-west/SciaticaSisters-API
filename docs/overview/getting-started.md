# Getting started

---

## About the API

- **Base URL**: `http://localhost:3000` or your own `{base_url}` server.
- **Data format**: JSON for all requests and responses
- **Server**: This API runs on your local machine or your chosen server environment

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

## Test with curl

Open a new terminal window and run:

```bash
curl http://localhost:3000/users
```

You should see a list of users in JSON format.

---

## Test with Postman

1. Open the Postman desktop app
2. Create a new request
3. Set method to `GET`
4. Enter URL: `http://localhost:3000/users`
5. Click **Send**

You should see a list of users in the response.
