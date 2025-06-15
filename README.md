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
    git clone git@github.com:bengeek06/pm-staging.git
    cd pm-staging
    git submodule update --init --recursive
    ```

2. **Build and start the environment with Docker Compose:**
    ```bash
    docker compose up --build
    ```

3. **Access the main services:**
    - **NexiPM backend(s):** http://localhost:8000 (or other ports as configured)
    - **Swagger UI:** http://localhost:8081
    - **pgAdmin:** http://localhost:5050 (default login: `admin@admin.com` / `admin`)
    - **Grafana:** http://localhost:3000 (default login: `admin` / `admin`)
    - **Prometheus:** http://localhost:9090
    - **MinIO Console:** http://localhost:9001 (`minioadmin` / `minioadmin`)
    - **Redis:** localhost:6379

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
