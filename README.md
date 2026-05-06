Secure DevSecOps Pipeline using Azure DevOps
📌 Project Overview

This project demonstrates how to implement a secure DevSecOps CI/CD pipeline using Azure DevOps. The pipeline automates the process of building, scanning, storing, and deploying a Dockerized application while following security best practices.

The project integrates Azure Key Vault for secret management, Trivy for vulnerability scanning, Azure Container Registry (ACR) for image storage, and Azure App Service for deployment.

🎯 Project Objectives
Implement secure CI/CD practices
Store secrets securely using Azure Key Vault
Build Docker images automatically in Azure DevOps
Scan Docker images for vulnerabilities using Trivy
Push images to Azure Container Registry
Deploy the application securely to Azure App Service
Learn DevSecOps fundamentals and security integration in pipelines
🛠️ Tools & Technologies Used
Tool	Purpose
Azure DevOps	CI/CD Pipeline
Azure Key Vault	Secret Management
Docker	Containerization
Trivy	Vulnerability Scanning
Azure Container Registry (ACR)	Docker Image Storage
Azure App Service	Application Hosting
Azure CLI	Resource Management
Git & GitHub	Source Code Management
YAML	Pipeline Configuration
🏗️ Architecture Flow
GitHub Repository
        ↓
Azure DevOps Pipeline
        ↓
Fetch Secrets from Azure Key Vault
        ↓
Build Docker Image
        ↓
Scan Image using Trivy
        ↓
Push Image to Azure Container Registry
        ↓
Deploy to Azure App Service
        ↓
Application Running Securely
📁 Project Structure
secure-devsecops-pipeline/
│
├── Dockerfile
├── index.html
├── azure-pipelines.yml
├── .gitignore
└── README.md
☁️ Azure Resources Created
Resource	Name
Resource Group	rg-security-sejal
Azure Key Vault	sejal-sec-kv
Azure Container Registry	sejalsecurityacr
App Service Plan	sejal-security-plan
Azure Web App	sejal-secure-app
🔐 Azure Key Vault Configuration

A secret named:

APP-SECRET

was stored securely inside Azure Key Vault.

The Azure DevOps Service Principal was granted:

Key Vault Secrets User

role access to retrieve secrets during pipeline execution.

🐳 Docker Configuration
Dockerfile
FROM nginx:alpine
COPY index.html /usr/share/nginx/html/index.html
EXPOSE 80

This creates a lightweight NGINX-based container image.

🔎 Trivy Vulnerability Scanning

Trivy was installed inside the Azure DevOps pipeline and used to scan the Docker image for:

Critical vulnerabilities
High severity vulnerabilities

Command used:

trivy image --severity HIGH,CRITICAL image-name

This ensures images are scanned before deployment.

🚀 CI/CD Pipeline Stages
Stage 1 – Build & Security Scan

Pipeline performs:

Fetch secrets from Azure Key Vault
Build Docker image
Install Trivy
Scan Docker image
Push image to Azure Container Registry
Stage 2 – Deployment

Pipeline performs:

Configure Azure Web App
Pull latest image from ACR
Deploy containerized application
Restart Web App
📄 Azure Pipeline YAML Features

The pipeline includes:

AzureKeyVault task
AzureCLI task
Docker build & push
Trivy security scanning
Automated deployment
🔥 Security Best Practices Implemented

✔ Secrets stored securely in Azure Key Vault
✔ No hardcoded credentials in code
✔ Docker image vulnerability scanning
✔ Service principal authentication
✔ Secure CI/CD workflow
✔ Automated deployments

🌐 Application Deployment

Application deployed successfully to:

http://sejal-secure-app.azurewebsites.net
🧠 Challenges Faced & Solutions
Issue	Solution
Key Vault access denied	Assigned Key Vault Secrets User role
Dockerfile empty error	Updated Dockerfile correctly
Service connection issue	Created Azure Resource Manager service connection
Secret access failure	Configured RBAC permissions properly
📚 Key Learnings
Azure DevOps YAML pipelines
Secure secret management
Docker containerization
Vulnerability scanning with Trivy
Azure RBAC permissions
Azure App Service container deployment
DevSecOps workflow implementation
🎯 Project Outcome

Successfully implemented a secure DevSecOps pipeline capable of:

Securely handling secrets
Scanning images before deployment
Automating CI/CD
Deploying Dockerized applications to Azure

This project demonstrates practical knowledge of DevSecOps and cloud-native CI/CD practices.

👩‍💻 Author

Sejal Sakhala
Azure & DevOps Enthusiast
