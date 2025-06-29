# NexiPM Development Environment

![Docker Compose](https://img.shields.io/badge/docker--compose-ready-blue?logo=docker)
![Git Submodules](https://img.shields.io/badge/git-submodules-blue?logo=git)
![Maintained](https://img.shields.io/badge/maintained-yes-brightgreen)
![License](https://img.shields.io/badge/license-AGPLv3%20%2F%20Commercial-blue)

This repository provides the complete development environment for the NexiPM software, including all required services and tools.

---

## Getting Started

1. **Clone this repository with submodules:**
    ```bash
    git clone --recurse-submodules git@github.com:bengeek06/pm-staging.git
    cd pm-staging
    ```

2. **Build and start the environment with Docker Compose:**
    ```bash
    docker compose up -d --build
    # For the Next.js frontend, install the dependencies inside the container:
    docker compose exec nexi-pm npm install
    ```
    > **Note :** This command is required on first launch or if you remove the `nexi_pm_node_modules`

3. **Access the main services:**

| Service         | URL / Port                | Notes                                  |
|-----------------|--------------------------|----------------------------------------|
| NexiPM Frontend | http://localhost:3000     | Next.js frontend                       |
| Identity API    | http://localhost:5002     | Flask API                              |
| Auth API        | http://localhost:5001     | Flask API                              |
| Identity DB     | localhost:5434            | PostgreSQL                             |
| Auth DB         | localhost:5433            | PostgreSQL                             |
| pgAdmin         | http://localhost:5050     | login: `admin@admin.com` / `admin`     |
| Swagger UI      | http://localhost:8081     | API documentation (multi-OpenAPI)      |

*Other services (Grafana, Prometheus, Redis, MinIO, Loki, etc.) are present in the compose file but commented out by default. Uncomment them if you need monitoring, logging, or additional functionality.*

4. **Stop the environment:**
    ```bash
    docker compose down
    ```

---

## Notes

- Each service is configured via Docker Compose and may have its own environment variables.
- To update submodules, run:
    ```bash
    git submodule update --remote
    ```
- For more details, see the documentation of each submodule.

---

## License

This project is distributed under a **dual license**:  
- [GNU AGPLv3](https://www.gnu.org/licenses/agpl-3.0.html) for open source/community use  
- [Commercial License](./COMMERCIAL-LICENCE.txt) for professional/commercial use  
See [LICENCE.md](./LICENCE.md) for details.
