# 🚀 Flask App Deployment using Jenkins CI/CD & Docker 🐳

![CI/CD](https://img.shields.io/badge/Automated%20with-Jenkins-blue?logo=Jenkins)
![Docker](https://img.shields.io/badge/Built%20with-Docker-blue?logo=Docker)
![Made with Python](https://img.shields.io/badge/Python-3.9-blue?logo=python)

---

## 📌 Project Overview

This project demonstrates a complete CI/CD pipeline using **Jenkins**, **Docker**, and a simple **Flask** web application — all set up from scratch on a local machine using **WSL2** (Ubuntu) 🐧💻.

> ✅ **Automated Deployment** from build → container → localhost test  
> ❌ No pre-built Docker images  
> 🔧 Real-time debugging with container health checks

---

## 🧱 Tech Stack

| Tool        | Purpose                            |
|-------------|------------------------------------|
| 🧱 Jenkins  | Automates CI/CD pipeline            |
| 🐳 Docker   | Containerizes the Flask application |
| 🐍 Python   | Web application (Flask)             |
| 🐧 WSL2     | Ubuntu environment for DevOps setup |

---

## 🚀 Features

- ✅ Jenkinsfile to automate Docker build and deployment
- ✅ Flask app exposed on `http://localhost:5000`
- ✅ Container cleanup to avoid port conflicts
- ✅ Real error debugging (port conflicts, Jenkins setup, etc.)
- ✅ Optional Docker Registry setup (localhost:5000)

---

## 🗂️ Project Structure

📦 flask-docker-jenkins/
┣ 📂 app/
┃ ┗ 📄 app.py
┣ 📄 Dockerfile
┣ 📄 Jenkinsfile
┣ 📄 requirements.txt

🎯 Final Result
🎉 App is successfully deployed and running at:
🔗 http://localhost:5000 via Docker container, built & deployed by Jenkins CI/CD pipeline 🚀


📚 Lessons Learned
🧠 Jenkins won't check if your app inside the container is alive — add health checks

🔄 Always clean up containers before redeployment

🧼 Use separate ports for registry and app containers

💡 Real debugging builds real confidence in DevOps


🙋‍♀️ Author
Harshitha G M
📫 Aspiring DevOps Engineer
