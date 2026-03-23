---
layout: default
---

# Release notes

---

## Version 1.0.0

**Release date:** March 23, 2026

The first release of the SciaticaSisters API. This version supports full create, read, update, and
delete operations for two core resources: users and exercise logs.

---

## User endpoints

| Method | Endpoint | Description |
| --- | --- | --- |
| Get | `/users/{id}` | Get a user by ID |
| Post | `/users` | Create a new user |
| Patch | `/users/{id}` | Update select fields on a user |
| Put | `/users/{id}` | Replace a user record |
| Delete | `/users/{id}` | Delete a user |

---

## Exercise log endpoints

| Method | Endpoint | Description |
| --- | --- | --- |
| Get | `/exerciseLogs/{id}` | Get an exercise log by ID |
| Post | `/exerciseLogs` | Create a new exercise log |
| Patch | `/exerciseLogs/{id}` | Update select fields on an exercise log |
| Put | `/exerciseLogs/{id}` | Replace an exercise log record |
| Delete | `/exerciseLogs/{id}` | Delete an exercise log |

---

## Resources

- [Users resource](../api/users.md)
- [Exercise logs resource](../api/user-exercise-logs.md)

---

## Known limitations

- No authentication required in this version.
- This version runs on a local JSON server.
