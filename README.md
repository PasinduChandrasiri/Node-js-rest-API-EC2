# 🚀 Node.js REST API Auto-Deploy on AWS EC2 with CI/CD

Welcome to the ultimate template for deploying your Node.js REST API on AWS EC2 with a fully automated CI/CD pipeline using GitHub Actions! This project is designed for rapid, reliable, and secure deployments—so you can focus on building features, not fighting servers.

## 🌟 Features

- **End-to-End Automation:** Push code, and watch it deploy automatically to your AWS EC2 instance.
- **Robust CI/CD:** Integrated GitHub Actions workflows for testing, building, and deploying.
- **Cloud-Native:** Runs on scalable AWS infrastructure with secure access.
- **Production-Ready:** Nginx reverse proxy, PM2 process manager, and environment variable management.
- **Easy Customization:** Modify workflows and scripts to fit your project’s needs.

## 🛠️ Quick Start

### 1. Create an EC2 Instance

- Launch a new EC2 instance in your AWS account (or use an existing one).
- Generate or use an existing SSH key pair for secure access.

### 2. Git Repository Setup

- Create a new Git repository.
- Push your Node.js code to the repository.

### 3. GitHub Actions Setup

- Go to your repository’s **Settings > Actions**.
- Add a self-hosted runner (your EC2 instance) and follow the setup instructions.

### 4. Environment Setup for GitHub Actions

- Create a `.env` file with all required environment variables.
- Add these variables as **secrets** in your GitHub repository settings.

### 5. CI/CD Workflows

- Define workflows in the `.github/workflows` directory.
- Customize workflows as needed for your project.

### 6. Environment Setup in EC2 Instance

- Install **Node.js** and **Nginx**:
- sudo apt update
- curl -fsSL https://deb.nodesource.com/setup_lts.x | sudo -E bash -
- sudo apt-get install -y nodejs nginx

- Configure Nginx as a reverse proxy for your Node.js app.
- Install **PM2** for process management:
- sudo npm install -g pm2
- pm2 start server.js --name=apiServer


## 🔄 Workflow Explanation

- **CI Process:**  On every push to the `main` branch:
- Checks out the latest code
- Sets up Node.js environment
- Installs dependencies
- Runs tests (if configured)

- **CD Process:**  On successful CI:
- SSH into the EC2 instance
- Pulls the latest changes
- Restarts the Node.js application with PM2
- Verifies deployment

## 📁 Directory Structure

| Path                | Description                                      |
|---------------------|--------------------------------------------------|
| `src/`              | Source code for the Node.js application          |
| `.github/workflows/`| CI/CD workflow configuration files               |
| `.env`              | Environment variables for the application        |
| `server.js`         | Entry point for the Node.js application          |
| `package.json`      | Dependency configuration for npm                 |

## 🧩 Tech Stack

- Node.js
- AWS EC2
- GitHub Actions
- Nginx
- PM2
- Ubuntu
- Shell scripting

## 💡 Why Use This Template?

- **Save time:** Automate deployment and reduce manual work.
- **Increase reliability:** Automated tests and deployments catch issues early.
- **Scale easily:** Cloud-native setup built for growth.
- **Stay secure:** Secrets management and SSL support.

*Happy coding and seamless shipping!*
