<p align="center">
  <a href="http://nestjs.com/" target="blank"><img src="https://nestjs.com/img/logo-small.svg" width="120" alt="Nest Logo" /></a>
</p>

# Pokedex Backend

A robust backend service built with **NestJS**, designed to manage Pokémon data. This project demonstrates modular architecture, dependency injection, and containerized database management.

🚀 **Live URL:** [https://nest-pokedex-f39d.onrender.com](https://nest-pokedex-f39d.onrender.com)

## 🚀 Getting Started

### Prerequisites

*   [Node.js](https://nodejs.org/) (LTS recommended)
*   [Nest CLI](https://docs.nestjs.com/cli/overview) (`npm i -g @nestjs/cli`)
*   [Docker](https://www.docker.com/) & [Docker Compose](https://docs.docker.com/compose/)

### Installation & Execution

1.  **Clone the repository:**
    ```bash
    git clone <your-repository-url>
    cd 03-pokedex
    ```

2.  **Install dependencies:**
    ```bash
    yarn install
    ```

3.  **Clone the `.env.template` file and rename the copy to `.env`:**
    ```bash
    cp .env.template .env
    ```

4.  **Fill in the environment variables defined in `.env`.**
    See `.env.template` for the full list of required keys.

5.  **Launch the database container:**
    ```bash
    docker compose up -d
    ```

6.  **Run the application in development mode:**
    ```bash
    yarn start:dev
    ```

7.  **Rebuild the database with the seed:**
    ```text
    http://localhost:3000/api/v2/seed
    ```

## 🏗 Production Build

1.  **Create the `.env.prod` file:**
    ```bash
    cp .env.template .env.prod
    ```

2.  **Fill in the production environment variables in `.env.prod`.**
    Inside a container, `MONGODB` must point to the database **service name** defined in
    `docker-compose.prod.yaml`, not to `localhost`.

3.  **Build the image and start the containers:**
    ```bash
    docker compose -f docker-compose.prod.yaml --env-file .env.prod up -d --build
    ```

4.  **Seed the database:**
    ```text
    http://localhost:3000/api/v2/seed
    ```

### Notes

*   `--env-file .env.prod` is **required**. Compose interpolates `${MONGODB}`, `${PORT}` and
    `${DEFAULT_LIMIT}`; without the flag it falls back to `.env`, which points to `localhost` and
    fails inside the container.
*   The image has no bind mount for source code, so **any change under `src/` requires a rebuild**.
    Re-run the same `up -d --build` command.
*   To stop the stack:
    ```bash
    docker compose -f docker-compose.prod.yaml --env-file .env.prod down
    ```
    Never use `down -v` — it would wipe the MongoDB data.

## ☁️ Deployment

This project is deployed on [Render](https://render.com) with auto-deploy enabled: every push to
`main` on `origin` triggers a new build.

### Force a redeploy without code changes

Useful after changing environment variables in the Render dashboard, or when a build failed for a
transient reason:

```bash
git commit --allow-empty -m "Trigger redeploy"
git push origin main
```

The `--allow-empty` flag creates a commit with no file changes, which is enough for Render to pick
up a new deploy.

## 🛠 Tech Stack

*   **Framework:** NestJS
*   **Language:** TypeScript
*   **Database:** MongoDB
*   **Containerization:** Docker & Docker Compose

---
*Built with professional architecture standards, focusing on modularity and maintainability.*
