<p align="center">
  <a href="http://nestjs.com/" target="blank"><img src="https://nestjs.com/img/logo-small.svg" width="120" alt="Nest Logo" /></a>
</p>

# Pokedex Backend

A robust backend service built with **NestJS**, designed to manage Pokémon data. This project demonstrates modular architecture, dependency injection, and containerized database management.

🚀 **Live URL:** [https://nest-pokedex-f39d.onrender.com](https://nest-pokedex-f39d.onrender.com)

## 🚀 Getting Started
## 🚀 Getting Started

### Prerequisites

*   [Node.js](https://nodejs.org/) (LTS recommended)
*   [Nest CLI](https://docs.nestjs.com/cli/overview) (`npm i -g @nestjs/cli`)
*   [Docker](https://www.docker.com/) & [Docker Compose](https://docs.docker.com/compose/)

### Installation & Execution

1.  **Clone the repository:**
    ```bash
    git clone <your-repository-url>
    03-pokedex
    ```

2.  **Install dependencies:**
    ```bash
    yarn install
    ```

3.  **Launch the database container:**
    ```bash
    docker-compose up -d
    ```

4.  **Run the application (Development Mode):**
    ```bash
    npm run start:dev
    ```

5. **Clone the `.env.template` file and rename the copy to `.env`**

6. **Fill in the environment variables defined in the `.env` file**

7. **Run the application in dev:**
   ```bash
   yarn start:dev

8. **Rebuild the database with the seed:**
    ```text
    http://localhost:3000/api/v2/seed
    ```

## 🛠 Tech Stack

*   **Framework:** NestJS
*   **Language:** TypeScript
*   **Database:** MongoDB
*   **Containerization:** Docker & Docker Compose

---
*Built with professional architecture standards, focusing on modularity and maintainability.*
