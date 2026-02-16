# abbas-k8s-portfoli
Kubernetes NGINX Portfolio Deployment

This project demonstrates my hands-on experience with Docker, Kubernetes and Git by deploying a personal portfolio web page inside a Kubernetes cluster.

The goal of this project was to understand real DevOps workflow:

• Create a containerized application
• Deploy it inside Kubernetes
• Expose it to the internet
• Push complete infrastructure code to GitHub

## Step 1 — Application Creation

I created a custom HTML portfolio page containing my name, skills and experience.

Then I containerized it using Docker by writing a Dockerfile based on the nginx image.

This allowed my web app to run consistently inside any environment.

## Step 2 — Kubernetes Deployment

I created a Deployment manifest:

3 replicas of my app

## Runs inside Pods

Managed by Kubernetes scheduler

This ensures high availability — if one pod crashes, Kubernetes automatically recreates it.

## Step 3 — Service Exposure

I created a NodePort Service to expose my application outside the cluster.

Using the public VM IP + NodePort, the website became accessible from the browser.

This simulates how real production apps are exposed.

## Step 4 — Git Version Control

I initialized a Git repository and pushed the infrastructure code to GitHub using SSH authentication.

SSH keys were configured to enable secure and professional Git operations without passwords.

Outcome

# Successfully deployed a scalable web application using:

Docker → Containerization
Kubernetes → Orchestration
GitHub → Version Control

This project demonstrates practical understanding of DevOps fundamentals and cluster networking.

## COMMANDS USED ##

# Create Docker Image
docker build -t abbas-portfolio .

# Create Kubernetes Deployment
kubectl apply -f nginx-deployment.yaml

# Create Service
kubectl apply -f nginx-service.yaml

# Verify Pods
kubectl get pods -o wide

# Verify Service
kubectl get svc

# Access Application
curl http://<NODE-IP>:<NODE-PORT>

# Git Setup
git init
git add .
git commit -m "Initial commit"

# Add Remote
git remote add origin git@github.com:daniyaalabbas/abbas-k8s-portfolio.git

# Push Code
git push -u origin main

# SSH Authentication Test
ssh -T git@github.com

