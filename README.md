# Roboshop Shipping Microservice CICD

This repository contains the **Shipping** microservice for the **Roboshop Application**, a cloud-native, microservices-based e-commerce platform for selling robots. The Shipping service is responsible for managing all shipping-related operations within the Roboshop ecosystem.

---

## Table of Contents

- [Overview](#overview)
- [Architecture](#architecture)
- [Tech Stack](#tech-stack)
- [CI/CD Pipeline](#cicd-pipeline)
- [Deployment](#deployment)
- [Getting Started](#getting-started)
- [Repository Structure](#repository-structure)
- [Contributing](#contributing)
- [License](#license)

---

## Overview

The **Shipping microservice** is a core component of the Roboshop platform, handling all tasks related to shipment processing, tracking, and integration with order and inventory services. It is designed to be lightweight, scalable, and robust, supporting seamless order fulfillment workflows.

---

## Architecture

- **Microservices**: Follows a microservices architecture for modularity and scalability.
- **Containerized**: Packaged as a Docker container for consistent deployment across environments.
- **Cloud Native**: Deployed on Amazon EKS (Elastic Kubernetes Service) for high availability and scalability.
- **CI/CD**: Automated build, test, and deployment pipeline using Jenkins and a [shared Jenkins library](https://github.com/BharathKumarReddy2103/jenkins-shared-library).

---

## Tech Stack

- **Language**:Java
- **Containerization**: Docker
- **Orchestration**: Kubernetes (EKS on AWS)
- **CI/CD**: Jenkins (with shared library)
- **Version Control**: GitHub

---

## CI/CD Pipeline

This repository uses a robust CI/CD pipeline powered by Jenkins and a shared library for reusable steps and best practices.

- **Jenkinsfile**: Defines the pipeline steps for build, test, and deployment.
- **Jenkins Shared Library**: Common pipeline logic is reused from [jenkins-shared-library](https://github.com/BharathKumarReddy2103/jenkins-shared-library).
- **Docker Integration**: Builds Docker images for the shipping service.
- **Kubernetes Deployment**: Automated deployment to EKS.

---

## Deployment

The service is deployed on AWS EKS using Kubernetes manifests. The pipeline automates:

1. **Docker Image Build**: Builds and pushes the Docker image to a container registry.
2. **Kubernetes Deployment**: Deploys the latest image to EKS.
3. **Rolling Updates**: Ensures zero-downtime deployments.

> **Note:** You need appropriate AWS and Kubernetes credentials for deployment.

---

## Getting Started

1. **Clone the repository**
   ```bash
   git clone https://github.com/BharathKumarReddy2103/shipping.git
   cd shipping
   ```

2. **Build Docker Image**
   ```bash
   docker build -t roboshop-shipping:latest .
   ```

3. **Run Locally**
   ```bash
   docker run -p 8080:8080 roboshop-shipping:latest
   ```

4. **CI/CD Pipeline**
   - Update code and push to GitHub.
   - Jenkins will automatically trigger the pipeline.

---

## Repository Structure

```
shipping/
├── src/             # Source code for the shipping service
├── Jenkinsfile      # CI/CD pipeline definition
├── Dockerfile       # Docker build instructions
├── README.md        # Project documentation
└── ...              # Other configs and supporting files
```

---

## Contributing

Contributions are welcome. Please open issues or submit pull requests for any improvements or bug fixes.

1. Fork the repository.
2. Create a feature branch.
3. Commit your changes.
4. Open a pull request.

---

## License

This project is licensed under the [MIT License](LICENSE).
