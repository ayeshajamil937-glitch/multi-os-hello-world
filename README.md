# 🚀 Multi-OS Hello World – Advanced Docker CI/CD Pipeline

## 📌 Project Overview

This project demonstrates a Multi-OS CI/CD pipeline using **GitHub Actions and Docker**. It automatically tests the application on three different operating systems: Ubuntu, macOS, and Windows.

After successful testing, the pipeline builds a Docker image and performs a security scan using **Trivy**.

The purpose of this project is to understand CI/CD automation, cross-platform testing, Docker image building, and container security scanning.

## 🎯 Project Objectives

- Build a basic Hello World web application.
- Create a Docker image using a Dockerfile.
- Automate workflows using GitHub Actions.
- Test the pipeline on multiple operating systems.
- Build and scan Docker images.
- Generate a Docker security scan report.

## 🛠️ Technology Stack

| Technology | Purpose |
|---|---|
| Git & GitHub | Source code management |
| GitHub Actions | CI/CD automation |
| Docker | Containerization |
| Nginx | Web server |
| Trivy | Docker image security scanning |
| Ubuntu | Linux testing environment |
| macOS | macOS testing environment |
| Windows | Windows testing environment |
| YAML | Workflow configuration |

## 📂 Project Structure

```text
multi-os-hello-world/
│
├── .github/
│   └── workflows/
│       └── multi-os-hello-world.yml
│
├── app/
│   └── index.html
│
├── Dockerfile
│
└── README.md
```

## ⚙️ Application Details

The application is a simple HTML-based Hello World web page served through Nginx.

**Application features:**
- Hello World message
- Docker CI/CD information
- Nginx web server

## 🐳 Docker Configuration

The Dockerfile uses the lightweight Nginx Alpine image.

```dockerfile
FROM nginx:alpine

COPY app/index.html /usr/share/nginx/html/index.html

EXPOSE 80

CMD ["nginx", "-g", "daemon off;"]
```

### Build Docker Image

```bash
docker build -t multi-os-hello-world:latest .
```

### Run Docker Container

```bash
docker run -d -p 8081:80 --name multi-os-app multi-os-hello-world:latest
```

### Access Application

Open your browser:

http://localhost:8081

## 🔄 CI/CD Pipeline Workflow

The GitHub Actions workflow performs these steps:

1. Developer pushes code to the GitHub repository.
2. GitHub Actions automatically starts the workflow.
3. Application tests run on Ubuntu.
4. Application tests run on macOS.
5. Application tests run on Windows.
6. Docker image is built on Ubuntu.
7. Trivy scans the Docker image for security vulnerabilities.
8. Security scan report is uploaded as a GitHub Actions artifact.

## 🔐 Security Scanning

This project uses Trivy to scan Docker images for vulnerabilities.

The scan checks for:
- Critical vulnerabilities
- High vulnerabilities

The workflow generates a security report that can be downloaded from the GitHub Actions run.

**Note:** The current pipeline uses report-only scanning (`exit-code: '0'`), so detected vulnerabilities do not automatically fail the workflow.

## ✅ Completed Work

- [x] GitHub repository created
- [x] Hello World HTML application created
- [x] Dockerfile configured
- [x] Docker image built locally
- [x] Docker container successfully running
- [x] Application tested at `http://localhost:8081`
- [x] Git# multi-os-hello-world
Multi OS Hello World using GitHub Actions
