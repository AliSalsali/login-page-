# Gitea CI/CD with Docker

This repository provides a basic setup to implement a CI/CD pipeline using **Gitea**. It includes a Docker-based configuration for running Gitea, a Gitea Runner, and an example Python project to demonstrate automated build and deployment workflows.

---

## 📂 Repository Structure

- **`gitea cicd/workflows/cicd.yaml`**  
  Contains the CI/CD workflow configuration file for Gitea Runner.

- **`test/`**  
  Directory for testing purposes. Place your unit and integration tests here.

- **`Dockerfile`**  
  The Dockerfile for creating a containerized environment for the project.

- **`docker-compose.yml`**  
  Docker Compose file to set up Gitea and its runner as containers.

- **`main.py`**  
  The main Python application file for this project.

- **`requirements.txt`**  
  A file listing the Python dependencies for the project.

---

## 🚀 Getting Started

Follow these steps to set up the project on your local environment:

### Prerequisites

- Docker & Docker Compose installed on your machine.
- Python 3.8+ installed.
- A Gitea Runner set up and registered with Gitea.

### Setup Instructions

1. Clone the repository:
   ```bash
   https://github.com/AliSalsali/login-page-.git
   cd login-page-
