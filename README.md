# SciaticaSisters API

**Documentation site →** [cae-west.github.io/SciaticaSisters-API](https://cae-west.github.io/SciaticaSisters-API)

---

The SciaticaSisters API helps developers build apps for patients with chronic pain. Patients can log
pain levels and track exercises over time. They can spot patterns in how they heal.

This API supports create, read, update, and delete operations for user profiles and exercise logs.

This is a portfolio project for the UW API Documentation program.

---

## Features

- **User profile management**: Create, read, update, and delete patient profiles
- **Exercise log tracking**: Log activities with pain level data
- **Pattern analysis support**: Structured data for trend tracking over time
- **10 documented endpoints** across two resource types
- **6 step-by-step tutorials** for common workflows

---

## Documentation

Full docs are at:
**[cae-west.github.io/SciaticaSisters-API](https://cae-west.github.io/SciaticaSisters-API)**

Includes:

- Getting started and setup
- Tutorials
- Full API Reference for all 10 endpoints
- Resource schemas with request and response examples

---

## Local setup

The API runs on a local JSON server. Follow these steps to run it on your machine.

### Prerequisites

- A [GitHub](https://github.com/) account
- [Git](https://git-scm.com/downloads)
- [Node.js](https://nodejs.org/en/download)
- [json-server](https://www.npmjs.com/package/json-server)
- [curl](https://curl.se/download.html) or [Postman](https://www.postman.com/downloads/)

### Installation

1. **Fork the [SciaticaSisters-API repository](https://github.com/cae-west/SciaticaSisters-API)**
2. **Clone your fork to your local machine**
3. **Open your terminal and go to the API folder**

    ```bash
    cd SciaticaSisters-API/api
    ```

4. **Start the JSON server**

    ```bash
    json-server -w sciatica-sisters-db-source.json
    ```

5. **Confirm it's running**

Open your browser or API client and go to:

```text
http://localhost:3000/users
```

   You should see a list of users in JSON format.

### Making requests

Use a REST client such as curl, Postman, or Insomnia. Example:

```bash
curl http://localhost:3000/users
```

See the [API Reference](https://cae-west.github.io/SciaticaSisters-API) for endpoint details and response
examples.

---

## Project structure

```text
SciaticaSisters-API/
├── api/
│   └── sciatica-sisters-db-source.json          # Local JSON database
├── docs/                                        # Jekyll documentation site
└── README.md
```

---

## Built with

- **JSON Server**: Lightweight REST API simulation
- **Jekyll**: Static site generator for the documentation site
- **GitHub Pages**: Documentation hosting

---

## About this project

This project is part of the UW API Documentation program. The effort included:

- Full API docs with overview, tutorials, reference, and resource pages
- Working with an expert to turn a technical vision into clear content
- Creating a custom theme setup and sidebar layout
- Writing for a health-focused audience

---

## Contact and links

- **Docs site:** [cae-west.github.io/SciaticaSisters-API](https://cae-west.github.io/SciaticaSisters-API)
- **Repository:** [github.com/cae-west/SciaticaSisters-API](https://github.com/cae-west/SciaticaSisters-API)
