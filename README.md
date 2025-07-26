
# Full DevOps Workflow: Git → Jenkins → Ansible → Docker → Kubernetes (Minikube)

This project demonstrates a complete **CI/CD pipeline** using **Git**, **Jenkins**, **Ansible**, **Docker Hub**, and **Kubernetes (Minikube)**. It automates the process of building, pushing, and deploying a Flask application using Jenkins and Ansible.

---

## 🚀 Project Workflow

1. **Code Commit:** Source code is pushed to GitHub.
2. **Jenkins Build Trigger:** Jenkins automatically pulls the latest code.
3. **Ansible Playbook Execution:** Jenkins triggers Ansible playbook to:
   - Copy Flask app to the remote server.
   - Build Docker image.
   - Push Docker image to Docker Hub.
   - Deploy Kubernetes manifests to Minikube.
4. **Minikube Deployment:** Minikube pulls the image from Docker Hub and deploys the Flask application.
5. **Kubernetes Service Exposure:** The Flask app is exposed via NodePort and is accessible externally.

---

## 🗂 Project Structure
├── ansible 
│ ├── deploy.yaml # Ansible Playbook
│ ├── inventory.ini # Inventory file with target server IP
│ └── vars.yaml # Variables (Docker Hub credentials)
├── flask-app
│ ├── app.py # Flask Application
│ ├── Dockerfile # Dockerfile for Flask App
│ ├── requirements.txt # Python Dependencies
│ └── k8s.yaml # Kubernetes Deployment & Service


---


---

## 🛠️ Prerequisites

- Two EC2 Instances (Ubuntu):
  - Jenkins + Ansible Server
  - Minikube Server
- Docker and Minikube installed on the Minikube server.
- SSH Key-based Authentication between Jenkins and Minikube server.
- Docker Hub account.

---

## 🔐 SSH Configuration

Follow the detailed SSH setup steps to enable password-less SSH between Jenkins and Minikube:  
✔️ SSH key generation  
✔️ Proper permission setup  
✔️ Adding remote host to known_hosts

*(Refer to the Medium blog for complete steps.)*

---

