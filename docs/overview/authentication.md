---
layout: default
---
# Authentication

## Development environment

This guide uses a test version of the Sciatica Sisters API that runs on json-server.

**No login needed** for local testing and learning.

All endpoints work without login on your local server at `{base_url}`.

---

## Real-world implementation

In a real-world setup, the Sciatica Sisters API would need login checks. This protects sensitive
patient health data.

### Recommended login method

This API would use **Basic Authentication**.

You can learn more in the [Mozilla Web Docs Authentication Guide](https://developer.mozilla.org/en-US/docs/Web/HTTP/Guides/Authentication).

**How it works:**

1. Users need a username and password to use the API.
2. Coded login details go in the request header.
3. The server checks login details before doing any work.

**Example request with authorization:**

```bash
curl -X GET {base_url}/users/1 \
  -H "Authorization: Basic dXNlcm5hbWU6cGFzc3dvcmQ="
```

### User permission levels

In production, different user types have different access rights:

**Patient Users:**

- Can view and update their own profile
- Can create, view, update, and delete their own exercise logs
- Can't see other users' data

**Healthcare Providers:**

- Can view patient profiles they work with
- Can view patient exercise logs
- Can't change patient data

**System Administrators:**

- Full access to all resources
- Can manage user accounts

### Security needs

A production version of this API would need to account for the following:

- **Health Insurance Portability and Accountability Act** - Meeting healthcare data privacy rules
- **HTTPS/Transport Layer Security encryption** - All data sent securely
- **API rate limiting** - Stopping abuse
- **Audit logging** - Tracking all data access
- **Token expiring** - Sessions that end after no activity

---

## For this guide

The tutorials and examples in this guide show requests without login for simplicity and learning purposes.
In production use, every request would include the `Authorization` header shown prior.
