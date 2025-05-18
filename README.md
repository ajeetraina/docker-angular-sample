# Docker Angular Sample


A production-grade, developer-focused Docker setup for Angular applications, built to ensure secure, high-performance, and scalable front-end deployments.



## 🚀 Features

- **Security-Focused**: Uses nginx-unprivileged with non-root user for enhanced security
- **Multi-Stage Build**: Optimized for fast builds and minimal image size
- **Development-Ready**: Configured for efficient developer experience with hot reload
- **Production-Optimized**: Performance tuned Nginx configuration for serving Angular SPA
- **Kubernetes-Ready**: Sample manifests for deploying to Kubernetes included
- **DevOps-Friendly**: Includes GitHub Actions workflow example
- **Follows Best Practices**: Implements Docker and Angular best practices

## 📚 Table of Contents

- [Prerequisites](#prerequisites)
- [Getting Started](#getting-started)
- [Development Workflow](#development-workflow)
- [Production Deployment](#production-deployment)
- [Docker Configuration](#docker-configuration)
- [Kubernetes Deployment](#kubernetes-deployment)
- [Security Features](#security-features)
- [CI/CD Integration](#cicd-integration)
- [Contributing](#contributing)
- [License](#license)

## 📋 Prerequisites

- Docker and Docker Compose installed on your machine
- Node.js and npm (for local development outside containers)
- Kubernetes cluster (optional, for Kubernetes deployment)

## 🏁 Getting Started

## Clone the repository

```bash
git clone https://github.com/ajeetraina/docker-angular-sample.git
cd docker-angular-sample
```


### Build the Docker image

```
docker build -t docker-angular-sample .
```

### Run the container

```
docker run -p 8080:8080 docker-angular-sample
Run with Docker Compose
```

### Start the application

```
docker compose up -d
```

Visit http://localhost:8080 in your browser

## 💻 Development Workflow

This project supports an efficient development workflow with hot-reload capabilities:

### Start the development environment

```
docker compose -f docker-compose.dev.yml up
```

The app will be available at http://localhost:4200 with hot-reload enabled

## 🚢 Production Deployment

The production Docker image is optimized for security and performance:

- Multi-stage build process minimizes image size
- Uses nginx-unprivileged for enhanced security
- Optimized Nginx configuration for Angular applications
- Content compression and caching enabled


### Build production image

```
docker build -t docker-angular-sample:prod .
```

### Run production container

```
docker run -p 8080:8080 docker-angular-sample:prod
```

## 🔧 Docker Configuration

### Dockerfile Details

The project uses a multi-stage Dockerfile:

- Builder Stage: Uses Node.js to build the Angular application
- Production Stage: Uses nginx-unprivileged to serve the built application

## Key security and performance features:

- Non-root user execution
- Optimized layer caching
- Minimized image size
- Custom Nginx configuration for Angular



## ☸️ Kubernetes Deployment

The repository includes a sample Kubernetes manifest for deploying the application:

### Apply the Kubernetes manifest

```
kubectl apply -f angular-sample-kubernetes.yaml
```

Make sure to update the image reference in the manifest with your own Docker image.

## 🔒 Security Features

This project implements several security best practices:

- Non-Root Execution: Uses nginx-unprivileged image to run as non-root
- Minimal Dependencies: Reduces attack surface with minimal base images
- Regular Security Scanning: Docker Scout integration to identify vulnerabilities
- Proper Port Configuration: Uses non-privileged ports (8080 instead of 80)
- Optimized Configuration: Custom Nginx settings to enhance security

## 🔄 CI/CD Integration

The repository includes a GitHub Actions workflow for continuous integration and deployment:

- Automated building and testing
- Security scanning with Docker Scout
- Deployment to Docker Hub or your container registry
- Kubernetes deployment options

## 👥 Contributing

Contributions are welcome! Please feel free to submit a Pull Request.

- Fork the repository
- Create your feature branch (git checkout -b feature/amazing-feature)
- Commit your changes (git commit -m 'Add some amazing feature')
- Push to the branch (git push origin feature/amazing-feature)
- Open a Pull Request

## 📄 License

This project is licensed under the MIT License - see the LICENSE file for details.
