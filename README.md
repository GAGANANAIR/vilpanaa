<p align="center">
  <img src="banner.svg" alt="Odoo Development Environment" width="100%"/>
</p>

<p align="center">
  <img src="https://img.shields.io/badge/odoo-dev%20environment-8b5a1a" alt="Odoo Dev Environment"/>
  <img src="https://img.shields.io/badge/docker-compose-2496ed?logo=docker&logoColor=white" alt="Docker Compose"/>
  <img src="https://img.shields.io/badge/postgres-16-336791?logo=postgresql&logoColor=white" alt="Postgres 16"/>
  <img src="https://img.shields.io/badge/vscode-devcontainer-007acc?logo=visualstudiocode&logoColor=white" alt="VS Code Devcontainer"/>
</p>

# vilpanaa

A ready-to-run **Odoo development environment** using Docker Compose and Postgres, with VS Code Devcontainer support for a one-click setup.

## What's inside

- **Odoo** — built from a wrapper Dockerfile (`.devcontainer/Dockerfile`), running with `--dev=reload,qweb,xml` for live-reloading during development
- **Postgres 16** — as the backing database, with a healthcheck so Odoo waits for the DB to be ready
- **`.devcontainer`** — VS Code Dev Containers config so you can open this folder in a container with everything pre-wired
- **`odoo.conf`** — Odoo server configuration (addons path, DB connection, logging)

## Getting Started

### Option A — VS Code Dev Containers
1. Open this folder in VS Code
2. Install the [Dev Containers extension](https://marketplace.visualstudio.com/items?itemName=ms-vscode-remote.remote-containers)
3. Run **"Reopen in Container"**

### Option B — Docker Compose directly
```bash
docker compose up
```
Odoo will be available at [http://localhost:8069](http://localhost:8069).

## Adding custom modules

Drop your custom Odoo addons into the `addons/` folder — it's mounted to `/mnt/extra-addons` inside the container and picked up automatically via `odoo.conf`.

## Security note

The default `docker-compose.yml` uses simple credentials (`odoo` / `odoo`) for local development convenience. **Do not use these defaults in production** — swap in strong, unique credentials and environment-based secrets before deploying anywhere beyond your local machine.
