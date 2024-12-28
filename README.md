# Movie Picture Pipeline

This repository demonstrates the end-to-end pipeline for a Movie Picture catalog web application. As a DevOps engineer, my role was to design and implement the CI/CD workflows for automating testing, building, and deployment of both the frontend (React) and backend (Flask) applications.

## Project Overview

The Movie Picture Pipeline application is built to allow users to catalog movie pictures, providing detailed information about each movie, such as the title, description, and the associated image. This pipeline automates the deployment of the application on AWS infrastructure using Kubernetes, Docker, and GitHub Actions.

### Key Features:
- Automated CI/CD workflows for frontend and backend.
- Dockerized applications for seamless deployment.
- AWS ECR for storing Docker images.
- Kubernetes deployment on AWS EKS.
- Frontend workflow includes linting, testing, building, and deployment.
- Backend workflow involves linting, testing, building Docker images, and deployment to EKS.

## Tech Stack

- **Frontend**: React
- **Backend**: Flask
- **Containerization**: Docker
- **Cloud Infrastructure**: AWS (ECR, EKS)
- **CI/CD**: GitHub Actions
- **Infrastructure as Code**: Kubernetes (EKS)

## My Role (DevOps Engineer)

As the DevOps engineer on this project, my primary responsibilities included:

- Creating the CI/CD pipeline by configuring GitHub Actions workflows to automate testing, building, and deployment.
- Setting up Docker images for both the frontend and backend applications.
- Integrating AWS ECR for storing Docker images and deploying the applications to an AWS EKS cluster.
- Ensuring proper automation and deployment to Kubernetes environments.
- Optimizing the pipeline for performance and security.

## Workflows

This project includes the following key workflows:

- **Frontend Workflow**:
    - Linting using ESLint.
    - Running unit tests.
    - Building Docker images and pushing them to AWS ECR.
    - Deploying to AWS EKS.

- **Backend Workflow**:
    - Linting Python code.
    - Running backend tests with pytest.
    - Dockerizing the Flask application and pushing images to AWS ECR.
    - Deploying the backend service to AWS EKS.

## Setup & Installation

To run the project locally, follow these steps:

### Prerequisites
- Docker
- AWS CLI configured with access to AWS account
- Kubernetes (kubectl) configured with EKS access
- Node.js and npm for frontend (React)
- Python and pip for backend (Flask)

### Clone the Repository
```bash
git clone https://github.com/EsraaKamel11/Movie-Picture-Pipeline.git
cd Movie-Picture-Pipeline
