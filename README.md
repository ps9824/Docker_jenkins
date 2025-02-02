# 🛠️ Jenkins in a Docker Container with Persistent Storage  

## 📌 Overview  
This project sets up **Jenkins inside a Docker container** with **persistent storage**, ensuring that plugins and configurations are retained even after restarting the container.  

## 🚀 Features  
- **Containerized Jenkins** for easy deployment  
- **Persistent volumes** to save Jenkins data  
- **Automatic plugin retention** to avoid reinstalling after container restarts  
- **Port mapping** for external access  

## 🏗️ Setup Instructions  

### **1️⃣ Pull the Jenkins Docker Image**
```sh
docker pull jenkins/jenkins:lts
