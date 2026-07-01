# 🛡️ SOC DevSecOps

A Flask-based Security Operations Center (SOC) simulation project demonstrating DevSecOps practices using Python, Docker, Docker Compose, and Jenkins CI/CD.

> **Team Project:** This project was developed collaboratively as part of an academic project. This repository is maintained as my personal portfolio copy.
## ✨ Features

- 🔐 Simulates a basic Security Operations Center (SOC) environment.
- 🌐 Web application built using Flask.
- 🐳 Containerized using Docker for consistent deployment.
- 📦 Docker Compose support for simplified application management.
- 🔄 CI/CD pipeline integration using Jenkins.
- 📁 Centralized log management through Docker volumes.
- 👥 Team-based development using Git and GitHub.
- ⚡ Lightweight and easy to deploy.


## 🛠️ Tech Stack

| Category | Technologies |
|----------|--------------|
| Programming Language | Python |
| Backend Framework | Flask |
| Containerization | Docker, Docker Compose |
| CI/CD | Jenkins |
| Version Control | Git, GitHub |
| Web Technologies | HTML, CSS, Jinja2 |


## 🏗️ Project Architecture

```text
                   +----------------------+
                   |      GitHub Repo     |
                   +----------+-----------+
                              |
                              | Source Code
                              v
                   +----------------------+
                   |      Jenkins CI      |
                   +----------+-----------+
                              |
                              | Build Pipeline
                              v
                   +----------------------+
                   | Docker & Docker Compose |
                   +----------+-----------+
                              |
                              | Containerized Deployment
                              v
                   +----------------------+
                   |   Flask Web App      |
                   +----------+-----------+
                              |
                              | HTTP Requests
                              v
                   +----------------------+
                   |      End User        |
                   +----------------------+
```


## 📂 Project Structure

```text
soc-devsecops/
│
├── app/
│   ├── app.py
│   ├── requirements.txt
│   └── templates/
│
├── attacker/
│   └── attacker.py
│
├── Dockerfile
├── docker-compose.yml
├── Jenkinsfile
├── README.md
└── .gitignore
```