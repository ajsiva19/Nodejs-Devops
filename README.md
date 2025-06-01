# 🚀 Node.js Docker CI/CD with GitHub Actions

This project demonstrates how to build and push a Docker image for a Node.js application using **GitHub Actions**.

---

## 📦 Features

- Automatically builds Docker image on every push to `main`
- Pushes image to **Docker Hub**
- Simple and reusable GitHub Actions workflow

---

## 🛠️ Requirements

- Node.js app with a `Dockerfile`
- GitHub repository
- Docker Hub account
- GitHub repository secrets:
  - `DOCKER_USERNAME`
  - `DOCKER_PASSWORD` (or access token)

---

## 🐳 Dockerfile

Create a `Dockerfile` in the root of your project:

```Dockerfile
# Use the official Node.js LTS image
FROM node:18

# Set the working directory
WORKDIR /usr/src/app

# Install dependencies
COPY package*.json ./
RUN npm install

# Copy application code
COPY . .

# Expose application port
EXPOSE 3000

# Start the application
CMD ["node", "app.js"]
