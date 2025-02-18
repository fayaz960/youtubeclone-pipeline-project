# YouTube Clone Pipeline Project

## Project Structure
- `youtubeclone-backend/`: Contains backend source code and Dockerfile.
- `youtubeclone-frontend/`: Contains frontend source code and Dockerfile.
- `docker-compose.yml`: Orchestrates PostgreSQL, backend, and frontend.
- `Jenkinsfile`: Defines the CI/CD pipeline.

## How to Run Locally
1. Clone this repository.
2. Run `docker-compose up -d --build` from the project root.
3. Access the frontend at `http://<your_machine_ip>:80` and the backend at `http://<your_machine_ip>:5000`.

## Jenkins Pipeline
- The Jenkinsfile defines the stages:
  1. Checkout (if using SCM)
  2. Build Docker images
  3. Run tests (if defined)
  4. Deploy via Docker Compose
