# Containerized Shortest Path Visualizer With CI/CD Automation

## Project Overview
This project demonstrates a DevOps-enabled deployment pipeline for a frontend-based Shortest Path Visualizer. The key objective was not just to build an algorithmic visualizer but to containerize the application using Docker, serve it using Nginx, and automate the deployment process via GitHub Actions to Render. It highlights a practical use case of applying modern DevOps principles such as Infrastructure as Code, CI/CD, and scalable deployments—even for static web apps.


## Key Features
1. **CI/CD Pipeline:** Automated build and deployment using GitHub Actions.
2. **Dockerized Frontend:** Multi-stage Docker setup to optimize image size and deploy with Nginx.
3. **Cloud Deployment:** Hosted seamlessly using Render’s static site infrastructure.
4. **Dijkstra’s Pathfinding:** An interactive visualizer showing the working of Dijkstra’s algorithm on a 2D grid.
5. **Fast and Lightweight:** Designed using vanilla HTML, CSS, and JavaScript with minimal dependencies.


## Tech Stacks Used
* **Frontend UI:** HTML, CSS, JavaScript
* **Algorithm:** Dijkstra’s Algorithm (for shortest path)
* **Containerization:** Docker, Nginx
* **CI/CD Automation:** GitHub Actions
* **Deployment:** Render (Cloud Hosting for Static Sites)
* **Version Control:** Git & GitHub


## Steps to Replicate the Setup

### 1. Prerequisites

* Install Docker
* Install Git
* Create an account on Render
* Fork or clone this repository
  - git clone https://github.com/Anshu202122/Containerized-Visualizer-with-CI-CD.git
  - cd Containerized-Visualizer-with-CI-CD

### 2. Build & Run Locally (Using Docker)

* Navigate to the project directory containing the Docker file.
* Build the Docker image:
  - docker build -t visualizer-app .
* Run the Docker container:
  - docker run -p 8080:80 visualizer-app
* Plan the infrastructure:
  - terraform plan

 ### 3. CI/CD Pipeline

The GitHub Actions workflow automates the entire deployment lifecycle as follows:
**Pipeline Steps**
1. **Trigger**
   - Activated on every push to the main branch.
2. **Checkout and Build:**
  - The repository is checked out.
  - A Docker image of the application is built using the Dockerfile.
3. **Push to Docker Hub:**
  - The image is tagged and pushed to your Docker Hub registry.
  - This ensures the image is versioned, portable, and reusable across platforms.
4. **Deploy to Render:**
  - The Render platform fetches the latest image or repository code.
  - The deployment is automatically triggered to update the live environment.

**What Happens on Each Commit to main**
* Source code is checked out and built.
* Docker image is built locally.
* Docker image is pushed to Docker Hub.
* Render pulls latest version from GitHub and updates the cloud deployment.


## How to Test the Deployed Application

1. **Get the Live URL**
  - Go to your Render Dashboard.
  - Select your deployed service (e.g., shortest-path-visualizer).
  - Copy the public Render URL of the application.
2. **Open the Application in Your Browser**
  - Paste the URL into your browser.
  - The deployed frontend should load successfully.
3. **Visualize the Shortest Path**

To confirm the latest version is live, make a visual or text change in the code, push it to main, and watch the deployment update automatically via GitHub Actions.
