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
```

### **2️⃣ Create a Volume for Persistent Storage**
```sh
docker volume create jenkins_data
```

### **3️⃣ Run Jenkins in a Container**
```sh
docker run -d \
  --name jenkins \
  -p 8080:8080 \
  -p 50000:50000 \
  -v jenkins_data:/var/jenkins_home \
  jenkins/jenkins:lts
```
- **Port 8080**  → Access Jenkins UI
- **Port 50000** → Communication with build agents

### **4️⃣ Access Jenkins**
Open your browser and go to:
👉 http://localhost:8080

To get the initial admin password, run:
```sh
docker exec -it jenkins cat /var/jenkins_home/secrets/initialAdminPassword
```

## 📂 Persistent Data Storage

- The volume (jenkins_data) ensures that Jenkins data, plugins, and jobs are retained even if the container is stopped or removed.
- No need to reinstall plugins every time you restart the container! 🚀

## 🛠️ Manage Jenkins Container

### Stop Jenkins
```sh
docker stop jenkins
```

### Start Jenkins
```sh
docker start jenkins
```

### Remove Jenkins (without losing data)
```sh
docker rm jenkins
```

## 📌 Useful Commands

### Check Running Containers
```sh
docker ps
```

## List Volumes
```sh
docker volume ls
```

### Remove Volume (if needed)
```sh
docker volume rm jenkins_data
```

## 🏗️ Tech Stack
### **✅ Docker** – Containerized Jenkins instance
### **✅ Jenkins** – CI/CD automation tool
### **✅ Volumes** – Persistent storage

## 💡 Conclusion
This setup ensures Jenkins runs smoothly inside a Docker container with all configurations and plugins intact. 🚀

Let me know if you have any questions or improvements! 💬

## 🔗 Connect with Me
🔹 LinkedIn: www.linkedin.com/in/sanket-pawade
🔹 GitHub: https://github.com/ps9824/Docker_jenkins.git

#DevOps #Jenkins #Docker #CI/CD #Automation
