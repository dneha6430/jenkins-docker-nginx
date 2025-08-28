# Jenkins + Docker + Nginx Demo

This project demonstrates a CI/CD pipeline using Jenkins to build and run a Dockerized Nginx web server.

## Project Files
- **Dockerfile** – Builds a Docker image with Nginx and a static HTML page.
- **index.html** – Sample web page.
- **Jenkinsfile** – Jenkins pipeline for build & deployment.

## Jenkins Pipeline Stages
1. **Checkout** – Pull code from GitHub.
2. **Build Docker Image** – Create Docker image `my-nginx-site`.
3. **Run Container** – Run Nginx container on port `8080`.

## Run Locally
```bash
docker build -t my-nginx-site .
docker run -d --name my-nginx -p 8080:80 my-nginx-site
