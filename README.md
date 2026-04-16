# 💱 Currency Converter

A modern, real-time currency conversion application built with React, Vite, and Tailwind CSS.

## 🚀 Features

- Real-time currency conversion
- Support for 150+ currencies
- Clean and responsive UI
- Fast performance with Vite
- Styled with Tailwind CSS
- Containerized deployment ready

## 🛠️ Tech Stack

- **Frontend:** React 18
- **Build Tool:** Vite 6
- **Styling:** Tailwind CSS 3
- **Container:** Docker
- **CI/CD:** Jenkins
- **Web Server:** Nginx

## 📦 Prerequisites

- Node.js 20+ (for local development)
- Docker & Docker Compose (for containerized deployment)
- Git

## 🔧 Local Development

### 1. Clone the repository
```bash
git clone https://github.com/yourusername/currency-converter.git
cd currency-converter

2. Install dependencies
bash
npm install
3. Start development server
bash
npm run dev
The app will be available at http://localhost:5173

4. Build for production
bash
npm run build
🐳 Docker Deployment
Using Docker Compose (Recommended)
bash
# Build and start the container
docker-compose up -d --build

# View logs
docker-compose logs -f

# Stop the container
docker-compose down
Using Docker Only
bash
# Build image
docker build -t currency-converter .

# Run container
docker run -d -p 8080:80 --name currency-converter-app currency-converter
The app will be available at http://localhost:8080

📁 Project Structure
text
currency-converter/
├── src/
│   ├── components/     # React components
│   ├── hooks/          # Custom React hooks
│   ├── utils/          # Utility functions
│   ├── App.jsx         # Main App component
│   └── main.jsx        # Entry point
├── public/             # Static assets
├── Dockerfile          # Docker configuration
├── docker-compose.yml  # Docker Compose configuration
├── nginx.conf          # Nginx server configuration
├── Jenkinsfile         # CI/CD pipeline configuration
├── package.json        # Dependencies and scripts
└── README.md          # Project documentation
🔄 CI/CD Pipeline
This project uses Jenkins for automated deployment:

Clone - Pulls latest code from repository

Build - Creates Docker image

Push - Uploads image to DockerHub

Deploy - Updates container on production server

Verify - Runs health checks

Pipeline Setup
Configure Jenkins credentials:

DockerHub credentials (ID: dockerhub-credentials)

SSH key for server access (ID: ssh-credentials-id)

Update variables in Jenkinsfile:

DOCKER_IMAGE - Your DockerHub repository

DEPLOY_SERVER - Your server IP/domain

DEPLOY_USER - SSH username

Run the pipeline from Jenkins dashboard

🌐 API Configuration
This app uses a currency exchange API. To configure:

Get an API key from your preferred provider

Create a .env file in the project root:

text
VITE_API_KEY=your_api_key_here
VITE_API_URL=https://api.exchangerate-api.com/v4
📝 Available Scripts
Script	Description
npm run dev	Start development server
npm run build	Build for production
npm run preview	Preview production build locally
npm run lint	Run ESLint
🚢 Environment Variables
Variable	Description	Default
PORT	Host port for Docker container	8080
DEV_PORT	Port for development container	3000
NODE_ENV	Environment mode	production
🛡️ Security
Nginx configured with security headers

Gzip compression enabled

Static assets cached efficiently

No sensitive data exposed in client

🐛 Troubleshooting
Build fails with permission error
bash
# Clean rebuild
docker-compose down
docker system prune -f
docker-compose build --no-cache
docker-compose up -d
Container not starting
bash
# Check logs
docker logs currency-converter-app

# Verify port is available
netstat -tulpn | grep 8080
Changes not reflecting
bash
# Force rebuild and restart
docker-compose down
docker-compose up -d --build --force-recreate
📊 Performance
Build Time: ~15 seconds

Image Size: ~25MB (compressed)

First Load: < 1 second

Time to Interactive: < 2 seconds
