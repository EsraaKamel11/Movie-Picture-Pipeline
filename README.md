# CI-CD-MoviePicture-Pipeline

## Table of Contents
- [Overview](#overview)
- [Features](#features)
- [Technologies Used](#technologies-used)
- [CI/CD Pipeline](#cicd-pipeline)
  - [CI/CD Workflow](#cicd-workflow)
- [Cloud Infrastructure](#cloud-infrastructure)
- [Kubernetes Integration](#kubernetes-integration)
  - [Kubernetes Workflow](#kubernetes-workflow)
- [Getting Started](#getting-started)
  - [Prerequisites](#prerequisites)
  - [Installation](#installation)
- [Usage](#usage)
- [Contributing](#contributing)
- [License](#license)
- [Contact](#contact)

## Overview
The CI-CD-MoviePicture-Pipeline is a comprehensive data processing pipeline designed to handle and analyze movie-related images. It automates the ingestion, processing, and storage of movie pictures, enabling efficient data management and insightful analytics. Leveraging advanced CI/CD practices, Kubernetes orchestration, and AWS cloud services, the pipeline ensures scalability, reliability, and continuous improvement.

## Features
- **Automated Data Ingestion:** Seamlessly collect movie images from various sources.
- **Data Processing:** Clean, transform, and prepare images for analysis.
- **Scalable Storage:** Store processed images in a reliable and scalable cloud storage solution.
- **Real-time Analytics:** Generate insights and visualizations from the processed data.
- **Robust CI/CD Pipeline:** Ensure continuous integration and deployment with automated testing and deployments.
- **Container Orchestration with Kubernetes:** Manage and scale containerized applications efficiently.

## Technologies Used
- **Programming Languages:** Python, Bash
- **CI/CD Tools:** GitHub Actions
- **Cloud Platforms:** AWS (S3, EC2, EKS, IAM, ELB), Docker
- **Container Orchestration:** Kubernetes (AWS EKS)
- **Infrastructure Management:** AWS CLI, kubectl
- **Data Processing:** Apache Airflow, Pandas, OpenCV
- **Version Control:** Git, GitHub

## CI/CD Pipeline
As the DevOps Engineer for this project, I implemented a robust and efficient pipeline that ensures seamless integration and continuous deployment of the application. Key components include:

- **Automated Testing:** Leveraging GitHub Actions to run unit tests, integration tests, and linting on every commit and pull request.
- **Build Automation:** Using Docker to containerize the application, ensuring consistency across development, staging, and production environments.
- **Continuous Deployment:** Automated deployments to AWS EKS clusters using GitHub Actions, minimizing manual intervention and reducing deployment time.
- **Infrastructure Management:** Managing Kubernetes resources directly with `kubectl` for streamlined deployments.

### CI/CD Workflow
1. **Code Commit:** Developer pushes code to GitHub repository.
2. **Trigger Pipeline:** GitHub Actions workflow is triggered on push or pull request.
3. **Run Tests:** Execute automated tests to ensure code quality.
4. **Build Docker Image:** Containerize the application using Docker.
5. **Push to Registry:** Upload the Docker image to GitHub Container Registry.
6. **Deploy to Kubernetes:** Automatically deploy the latest Docker image to AWS EKS clusters using `kubectl`.
7. **Post-Deployment Testing:** Run smoke tests to verify the deployment.

## Cloud Infrastructure
My expertise in cloud computing was pivotal in designing and managing the cloud infrastructure for this project:

- **AWS S3:** Utilized for scalable and secure storage of movie images.
- **AWS EC2:** Deployed auxiliary application instances ensuring high availability and scalability.
- **AWS Lambda:** Implemented serverless functions for event-driven processing tasks.
- **AWS EKS (Elastic Kubernetes Service):** Managed Kubernetes clusters for container orchestration, ensuring efficient deployment, scaling, and management of containerized applications.
- **AWS IAM:** Configured roles and permissions to secure access to AWS resources.
- **AWS ELB (Elastic Load Balancer):** Distributed incoming traffic across multiple Kubernetes pods for high availability.
- **Security Best Practices:** Configured IAM roles, security groups, and encryption to ensure data security and compliance.

## Kubernetes Integration
Integrating Kubernetes into the CI/CD pipeline has enhanced the scalability and reliability of the application. Key aspects include:

- **Container Orchestration:** Managed container deployment, scaling, and networking using Kubernetes on AWS EKS.
- **kubectl:** Used `kubectl` for managing Kubernetes resources, such as deployments, services, and pods.
- **Auto-scaling:** Configured Horizontal Pod Autoscalers (HPA) to automatically scale application pods based on CPU and memory usage.
- **CI/CD Integration:** Automated Kubernetes deployments through GitHub Actions, ensuring seamless integration with the CI/CD pipeline.

### Kubernetes Workflow
1. **Build & Push Docker Images:** Automated by the CI pipeline.
2. **Configure AWS EKS Access:** Set up `kubectl` to interact with the AWS EKS cluster.
3. **Deploy to Kubernetes:** Use `kubectl` to deploy the latest Docker images to the Kubernetes cluster.
4. **Monitor & Scale:** Continuously monitor application performance and scale resources as needed using Kubernetes native features.

## Getting Started
### Prerequisites
- **Git:** Installed on your local machine. [Download Git](https://git-scm.com/)
- **Docker:** Installed for containerization. [Download Docker](https://www.docker.com/)
- **AWS Account:** For deploying the application. [Sign Up for AWS](https://aws.amazon.com/)
- **Kubernetes CLI (kubectl):** For interacting with Kubernetes clusters. [Install kubectl](https://kubernetes.io/docs/tasks/tools/install-kubectl/)
- **AWS CLI:** For managing AWS services. [Install AWS CLI](https://aws.amazon.com/cli/)
- **GitHub Account:** For accessing GitHub Actions and repository.

### Installation
1. **Clone the Repository**
   ```bash
   git clone https://github.com/EsraaKamel11/CI-CD-MoviePicture-Pipeline.git
   cd CI-CD-MoviePicture-Pipeline
   ```

2. **Set Up Environment Variables**
   Create a `.env` file in the root directory and add the necessary environment variables:
   ```env
   AWS_ACCESS_KEY_ID=your_access_key
   AWS_SECRET_ACCESS_KEY=your_secret_key
   AWS_REGION=your_region
   EKS_CLUSTER_NAME=your_eks_cluster_name
   KUBECONFIG=path_to_kubeconfig
   ```

3. **Configure AWS CLI**
   ```bash
   aws configure
   ```
   Enter your AWS Access Key ID, Secret Access Key, region, and output format when prompted.

4. **Build the Docker Image**
   ```bash
   docker build -t movie-picture-pipeline .
   ```

5. **Run the Application Locally**
   ```bash
   docker run -d -p 8000:8000 --env-file .env movie-picture-pipeline
   ```

6. **Set Up Kubernetes Cluster**
   Ensure you have an AWS EKS cluster set up. If not, you can create one via the AWS Management Console or using AWS CLI commands:
   ```bash
   aws eks create-cluster --name your_eks_cluster_name --region your_region --kubernetes-version 1.21 --role-arn your_role_arn --resources-vpc-config subnetIds=subnet-xxxxxx,subnet-yyyyyy,securityGroupIds=sg-xxxxxx
   ```
   _Note: Replace placeholders with your actual AWS configurations._

7. **Configure kubectl for EKS**
   ```bash
   aws eks update-kubeconfig --region your_region --name your_eks_cluster_name
   ```

8. **Deploy to Kubernetes**
   ```bash
   kubectl apply -f k8s/deployment.yaml
   kubectl apply -f k8s/service.yaml
   ```

## Usage
Once the application is running, you can access it via [http://localhost:8000](http://localhost:8000). The pipeline will automatically ingest, process, and store movie images as per the configured workflows.

### API Endpoints
- **GET /images:** Retrieve a list of processed movie images.
- **POST /images:** Upload new movie images for processing.
- **GET /analytics:** View analytics and insights generated from the processed data.

## Contributing
Contributions are welcome! If you'd like to contribute to this project, please follow these steps:

1. **Fork the Repository**

2. **Create a Feature Branch**
   ```bash
   git checkout -b feature/YourFeature
   ```

3. **Commit Your Changes**
   ```bash
   git commit -m "Add some feature"
   ```

4. **Push to the Branch**
   ```bash
   git push origin feature/YourFeature
   ```

5. **Open a Pull Request**

Please ensure that your contributions adhere to the project's coding standards and include appropriate tests.

## License
This project is licensed under the MIT License.
