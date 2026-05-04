# FrontendGPT-CICD-Project 🚀

This repository contains the Frontend application built with **React (Vite)**. It serves as the user interface for our GPT-based platform, communicating with the backend API hosted on AWS EC2.

## 🛠 Tech Stack
- **Framework:** React + Vite
- **Deployment:** AWS EC2 (Single Instance)
- **Web Server:** Nginx (Reverse Proxy)
- **CI/CD:** GitHub Actions (Self-Hosted Runner)

## 🏗 Architecture
The frontend is built as a static asset during the CI/CD process and served through Nginx. The automation is handled by a self-hosted runner directly on the EC2 instance to ensure fast deployment.


## 🤖 CI/CD Pipeline
The deployment is triggered automatically on every push to the `main` branch.

**Workflow Steps:**
1. **Checkout:** Pulls latest code.
2. **Environment Setup:** Configures Node.js v22.x.
3. **Install:** Executes `npm ci` for clean dependencies.
4. **Build:** Runs `npm run build` to generate production assets.

## ⚙️ Local Setup
1. Clone the repo: `git clone [repo-url]`
2. Install dependencies: `npm install`
3. Start dev server: `npm run dev`

## 📋 Troubleshooting
- **Build Failures:** Ensure the `self-hosted` runner is active on EC2.
- **Nginx Issues:** Check `/etc/nginx/sites-available/` for correct root path mapping to the `dist` folder.
