# EMart Microservices Application Deployment

## Overview
EMart is a microservices-based e-commerce application designed to showcase the deployment and management of a scalable architecture using DevOps tools and practices. This repository highlights the use of **Docker**, **Docker Compose**, and **Vagrant** to containerize, orchestrate, and automate the deployment process.

## DevOps Features
- **Containerization**: Each component of the application is encapsulated in Docker containers, ensuring consistency across environments.
- **Orchestration**: Docker Compose is used to manage multi-container applications, automating the build and deployment process.
- **Scalability**: The architecture is designed to support additional microservices, showcasing the scalability aspect of microservices deployment.
- **Automation**: Vagrant is used for provisioning a virtual machine environment to simulate a production-like setup.
- **Monitoring & Resilience**: Docker Compose configurations ensure that services are restarted automatically if they fail.

## Application Architecture
The EMart application consists of:
- **API Gateway**: Nginx-based routing, managing traffic to various endpoints.
- **Frontend (Client App)**: Angular application served via the API Gateway.
- **Backend Services**:
  - Node.js (`/api`): Core application logic.
  - Java (`/webapi`): Book management service.
- **Databases**:
  - MongoDB: For the Node.js API.
  - MySQL: For the Java API.

## Deployment Workflow
### Prerequisites
- [Docker](https://www.docker.com/)
- [Docker Compose](https://docs.docker.com/compose/)
- [Vagrant](https://www.vagrantup.com/) (optional for local VM setup)
- Git

### Step 1: Clone the Repository
```bash
git clone <repository-url>
cd EMart-app
```
### Step 2: Setup the Virtual Environment
1. Ensure no conflicting virtual machines are running:
```bash
vagrant global-status --prune
```
2. Start the virtual machine:
```bash
vagrant up
```
3. SSH into the VM and switch to the root user:
```bash
vagrant ssh
sudo -i
```

### Step 3: Build and Deploy the Application
1. Navigate to the project directory:
```bash
cd /path/to/EMart-app
```
2. Build and run the containers:
```bash
docker-compose up -d
```
3. Verify the containers are running:
```bash
docker-compose ps
```

### Step 4: Access the Application
1. Find the VM's IP address:
```bash
ip addr show
```
2. Open the browser and visit:
```arduino
http://<VM-IP>
```

### DevOps Practices Demonstrated
1. Environment Consistency: Using Docker and Vagrant ensures a consistent setup across development, staging, and production environments.
2. Automated Builds: Docker Compose automates building images and running containers.
3. Fault Tolerance: Compose configurations restart failed services automatically.
4. Scalability: The microservices architecture allows easy addition of services.
5.Code as Infrastructure: The repository provides all configurations and scripts necessary to replicate the deployment environment.

### Cleanup
1. To stop and remove containers:
```bash
docker-compose down -v
```
2. To halt the VM:
```bash
vagrant halt
```

### Acknowledgments
This project was developed as part of a DevOps training series to demonstrate the deployment of a microservices application.
