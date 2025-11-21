---

layout: default
---
# Authentication

## Development environment

This guide describes a local test version of the Sciatica Sisters API. It runs on json-server.

**No login needed** for local testing and learning.

All endpoints work without login at `http://localhost:3000`.

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
curl -X GET http://api.sciaticasisters.com/users/1 \
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

A production version of this API would need:

- **Health Insurance Portability and Accountability Act** - Meeting healthcare data privacy rules
- **HTTPS/Transport Layer Security encryption** - All data sent securely
- **API rate limiting** - Stopping abuse
- **Audit logging** - Tracking all data access
- **Token expiring** - Sessions that end after no activity

---

## For this guide

This is a local test setup for learning. All examples in tutorials and reference pages show requests
without login.

In production use, every request would include the `Authorization` header shown prior.
