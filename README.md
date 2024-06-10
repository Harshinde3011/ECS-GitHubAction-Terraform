# ECS-GitHubAction-Terraform
Here I create ECS cluster using terrafrom(IaC), after that I create simple nodejs application and deploy on ECS using GitHub Action

# Build Infra using Terraform and Deploy using GitHub action

## Prerequisites

- AWS account
- Terraform installed
- GitHub account
- Docker installed
- Node.js installed

## Project Structure

- `.github/workflows/deploy.yml`: GitHub Actions workflow for CI/CD.
- `index.js`: Simple Node.js application.
- `Dockerfile`: Dockerfile for building the Node.js application.
- `terraform-ecs-fargate/main.tf`: Terraform configuration file.

## Setup Instructions

### 1. Clone the Repository

```bash
git clone https://github.com/Harshinde3011/ECS-GitHubAction-Terraform.git
cd ECS-GitHubAction-Terraform
```
### 2. Set Up Terraform

```bash
terraform init
terraform plan
terraform apply
```

### 3. Set Up GitHub Secrets

Go to your GitHub repository, then Settings > Secrets and variables > Actions > New repository secret. Add the following secrets:
```bash
DOCKER_HUB_USERNAME: Your Docker Hub username.
DOCKER_HUB_ACCESS_TOKEN: Your Docker Hub access token.
AWS_ACCESS_KEY_ID: Your AWS access key ID.
AWS_SECRET_ACCESS_KEY: Your AWS secret access key.
```
### 4. GitHub Actions Workflow
##### The workflow defined in .github/workflows/deploy.yml will build and push the Docker image to Docker Hub and update the ECS service on each push to the main branch.

### 5. Access the Application
##### After deployment, you can access the application using the public IP of the ECS Fargate task.

- Go to the Amazon ECS Console.
- Select the hello-world-cluster.
- Under the Tasks tab, select the running task.
- Find the ENI ID and click to view details.
- The public IP address will be listed there. Access the application using http://PUBLIC_IP:3000.

### 6. Edit Security Group 
![Security Group]()
### 
This README file provides detailed instructions on setting up and running the project. Make sure to replace placeholders like `YOUR_USERNAME`, `YOUR_REPOSITORY`, and `YOUR_DOCKERHUB_USERNAME` with your actual values.


# Conclusion
This project sets up a basic CI/CD pipeline using GitHub Actions to deploy a Node.js application to AWS ECS Fargate using Terraform.
