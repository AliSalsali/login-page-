

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
   git clone https://github.com/YourUsername/YourRepository.git
   cd YourRepository
   ```

2. Build and run the Docker containers:
   ```bash
   sudo docker-compose up --build -d
   ```

---

### 📘 Gitea Runner Installation Guide

To enable the execution of CI/CD workflows with Gitea, you need to install and configure the **Gitea Runner** on your operating system. Follow these steps to install the runner:

#### 1. Download the Gitea Runner Binary
Download the latest Gitea Runner binary for your OS from the official Gitea releases page:  
👉 [Gitea Releases - Runner](https://docs.gitea.com/installation/install-from-binary)

#### 2. Install the Runner
Extract the binary and move it to a directory in your system's `PATH` (e.g., `/usr/local/bin`):
```bash
wget https://github.com/go-gitea/runner/releases/download/<version>/gitea-runner-linux-amd64
chmod +x gitea-runner-linux-amd64
sudo mv gitea-runner-linux-amd64 /usr/local/bin/gitea-runner
```
Replace `<version>` with the latest release version (e.g., `v0.4.0`).

#### 3. Register the Runner
Run the following command to register the runner with your Gitea instance:
```bash
gitea-runner register
```
You will be prompted to enter the following details:
- **Gitea Server URL**: The URL of your Gitea server (e.g., `http://localhost:3000`).
- **Token**: You can generate this token from the Gitea web interface under **Admin Panel > Runners > Generate Token**.
- **Runner Tags**: Add tags to specify the runner's purpose. 

⚠️ **Important**: Ensure that the tag you specify here matches the `runs-on` field in your workflow YAML file. For example:
```yaml
runs-on: [your-runner-tag]
```

#### 4. Start the Runner
After registration, start the runner:
```bash
gitea-runner daemon
```
To set up the runner as a system service, refer to the [official Gitea Runner documentation](https://docs.gitea.com/usage/actions/act-runner) for additional instructions.

---

## 🛠️ CI/CD Workflow

The CI/CD pipeline is defined in `gitea cicd/workflows/cicd.yaml`. It includes the following steps:

1. **Build**  
   Builds the Docker image for the application.

2. **Test**  
   Runs the tests from the `test/` directory.

3. **Push**  
   Pushes the built Docker image to Docker Hub (or any other registry).

---

## 🐳 Docker Services

- **Gitea**  
  A lightweight self-hosted Git service available on `http://localhost:3000`.

- **Gitea Runner**  
  A runner for executing CI/CD workflows, integrated with Gitea.
