
# CRUD-DD Task – MEAN Application

This repository contains the full-stack MEAN application (MongoDB, Express, Angular, Node.js) deployed using **Docker** and **Docker Compose** on an Ubuntu server.

This documentation explains **exactly the steps we performed**, so anyone can deploy the project in the same way.

---

# 📁 Project Structure

```
crud-dd-task-mean-app/
│
├── backend/                 # Node.js Express API
│├── Dockerfile
│
├── frontend/                # Angular application
│├── Dockerfile
│
├── nginx/
│├── default.conf            # Nginx reverse proxy configuration
│
└── docker-compose.yml       # Multi-container setup
```

---

# 🐳 Technologies Used

* Angular (Frontend)
* Node.js + Express (Backend)
* MongoDB (Database)
* Docker
* Docker Compose
* Nginx (Reverse Proxy)
* Ubuntu 24.04 (AWS EC2 VM)

---

# 🚀 **Setup on Ubuntu Server (We Actually Did This)**

### Update system

```
sudo apt update
```

### Install Docker

```
sudo apt install docker.io -y
```

### Install Docker Compose

```
sudo apt install docker-compose -y
```

### Verify installations

```
docker --version
docker-compose --version
```

---

# 🚀 **Upload Project to Server**

We uploaded the entire project folder to:

```
/home/ubuntu/project
```

Verify:

```
cd ~/project
ls
```

Expected output:

```
backend  frontend  nginx  docker-compose.yml
```

---

# 🚀 **Start Application Using Docker Compose**

From inside project directory:

```
cd ~/project
docker-compose up --build -d
```

This command automatically:

* Builds backend image
* Builds frontend image
* Starts MongoDB container
* Starts backend service
* Starts Nginx serving Angular
* Links containers together


---

# 🧪 **Checking Container Status**

```
docker ps
```

Expected to see:

```
frontend
backend
mongo
```

Accessible UI should load at:

```
http://<your-ec2-ip>
```

---

# 🔄 **Redeploy After Code Update**

If new code is pushed or updated:

```
docker-compose down
docker-compose up --build -d
```

This rebuilds and restarts all services.

---

# 🔥 **Nginx Reverse Proxy (Used in Deployment)**

Nginx was used to:

* Serve Angular build files
* Forward `/api/` requests to backend
* Enable app access over port 80 only

The configuration file is located in:

```
nginx/default.conf
```

---

# 📷 **Screenshots to Include in Submission (You Will Upload)**


The following screenshots are included as part of the assignment:

Screenshot	File
Application Home UI	images/home.png
Add Tutorial Page	images/add.png
Added Confirmation	images/added.png
Docker Images Built	images/imagesbuild.png
Running Containers	images/images.png


---

# 📌 **What This Repository Contains**

This repo includes:

* Complete Angular frontend
* Complete Node.js backend
* Dockerfile for backend
* Dockerfile for frontend
* Nginx reverse proxy configuration
* docker-compose.yml
* README documentation

---

# 🎯 Summary

This project has been fully:

✔ Containerized
✔ Tested locally
✔ Uploaded to Ubuntu
✔ Deployed with Docker Compose
✔ Running via Nginx reverse proxy
✔ Accessible via single port (80)

This README includes the **exact steps we actually performed**, nothing extra and nothing missing.

---
