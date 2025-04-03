# 🚀 Nginx Website Deployment with Docker  

## 🌟 **Project Overview**  
This project demonstrates how to containerize and deploy a static website using **Nginx** with **Docker**. You'll learn to:  
- Build a custom Docker image  
- Run an Nginx web server in a container  
- Push the image to **Docker Hub**  
- Redeploy the website from the cloud
  
![Screenshot_1](https://github.com/user-attachments/assets/c8c7c714-e1ab-4831-a46e-df71cad7d14c)

---

## 🎯 **Objectives**  
✅ **Containerize a static website** using Nginx  
✅ **Build and run a Docker container** with port mapping  
✅ **Push the Docker image** to Docker Hub for cloud storage  
✅ **Pull and redeploy** the website from Docker Hub  

---

## 🛠 **Tools & Technologies Used**  

| Category       | Tools/Technologies |  
|---------------|-------------------|  
| **Web Server**  | Nginx |  
| **Containerization** | Docker |  
| **Version Control** | Git |  
| **Cloud Registry** | Docker Hub |  
| **CLI** | Bash, Linux commands |  

---

## 📝 **Step-by-Step Guide**  

### **1️⃣ Clone the Repository**  
```bash
git clone https://github.com/MenaMagdyHalem/Course-Docker.git
cd Course-Docker
```

### **2️⃣ Create the Dockerfile**  
```bash
vim Dockerfile
```
**Add this configuration:**  

![Screenshot_3](https://github.com/user-attachments/assets/b1736eda-6081-44ff-a03f-1c949d2ff5fc)


### **3️⃣ Build the Docker Image**  
```bash
docker build -t website .
```


4![Screenshot_4](https://github.com/user-attachments/assets/19d48144-5f10-4c58-bf4d-d9f0c9dd943e)

### **4️⃣ Run the Container**  
```bash
docker run -it --rm -d -p 3000:80 --name web1 website
```

![Screenshot_5](https://github.com/user-attachments/assets/5a4f069e-1955-4b21-9756-6ff37b74674b)

**🌐 Access website:**  
👉 [http://localhost:3000](http://localhost:3000)  

![Screenshot_6](https://github.com/user-attachments/assets/e8508fc7-6ab0-4ec5-84b3-20a74bf0788d)


### **5️⃣ Push to Docker Hub**  
```bash
docker commit web1 moahmedmousa/new-web
docker login
docker push moahmedmousa/new-web
```

![Screenshot_7](https://github.com/user-attachments/assets/91b347fb-6f0b-4086-9e77-12d0f67d7815)

![Screenshot_8](https://github.com/user-attachments/assets/37d17e3d-6718-4c69-9ef5-f3263ba5661a)

![Screenshot_9](https://github.com/user-attachments/assets/44a6fe73-232b-4084-82ac-21ed633ef35e)


### **6️⃣ Pull & Redeploy**  
```bash
docker pull menamagdyhalem/new-web
docker run -it --rm -d -p 4000:80 --name new-hub moahmedmousa/new-web
```

![Screenshot_10](https://github.com/user-attachments/assets/a5eb4db0-f079-4202-a293-439d7d0a723f)

**🌐 Access redeployed site:**  
👉 [http://localhost:4000](http://localhost:4000)  


![Screenshot_11](https://github.com/user-attachments/assets/328806ae-34a8-4b87-9ba4-7253891fb0b9)

---

## 🧠 **Knowledge & Skills Gained**  

### **🖥 Hands-On Experience**  
✔ **Docker Basics** – Images, Containers, Dockerfile  
✔ **Nginx Configuration** – Serving static websites  
✔ **Port Mapping** – Linking host and container ports  
✔ **Docker Hub** – Pushing/Pulling images  
✔ **CLI Proficiency** – Git, Docker, Linux commands  

### **📚 Key Learnings**  
🔹 How to containerize web applications  
🔹 Managing Docker images & containers  
🔹 Cloud-based container deployment  
🔹 Best practices for Dockerfile creation  

---

## 🧹 **Cleanup Commands**  
```bash
# Stop & remove containers
docker stop web new-hub
docker rm web new-hub

# Remove images (optional)
docker rmi website menamagdyhalem/new-web

# Full system cleanup (optional)
docker system prune -a
```

---

## ❓ **Troubleshooting**  
🔸 **Permission Issues?** Run Docker with `sudo` or add user to the `docker` group:  
```bash
sudo usermod -aG docker $USER
```
🔸 **Port in use?** Change `3000`/`4000` to another port.  
🔸 **Website not loading?** Check container logs:  
```bash
docker logs web
```

---

## 🏁 **Conclusion**  
By completing this project, you’ve successfully:  
- **Deployed a website using Docker & Nginx**  
- **Shared your containerized app via Docker Hub**  
- **Gained essential DevOps skills**  


---

🎉 **Happy Dockerizing!** 🐳

---
