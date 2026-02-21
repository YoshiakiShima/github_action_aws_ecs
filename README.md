# ECS Auto-Deploy Project

This repository automates the build and deployment of a web application to **Amazon ECS (Fargate)** using **GitHub Actions**.

## Workflow Overview
Every time you push to the `main` branch, the following steps are performed automatically:
1. **Build**: Creates a Docker image from the `Dockerfile`.
2. **Push**: Uploads the image to **Amazon ECR**.
3. **Deploy**: Updates the **Amazon ECS** service with the new image.

##  Project Structure
* `.github/workflows/aws.yml`: GitHub Actions configuration.
* `task-definition.json`: ECS task definition.
* `Dockerfile`: Container configuration.
* `index.html`: Web application content.

##  Setup Requirements
To use this workflow, the following **GitHub Secrets** must be configured:
* `AWS_ACCESS_KEY_ID`
* `AWS_SECRET_ACCESS_KEY`

##  Key Achievements
* Resolved file path issues by moving `task-definition.json` to the root directory.
* Optimized the task definition by removing unnecessary keys like `enableFaultInjection`.
* Successfully aligned the container name to `my-web-app` for seamless deployment.
