# 🐳 Docker Compose Multi-Service Project

This project demonstrates Docker Compose used to orchestrate a full-stack environment that includes:

- A MySQL database with PHPMyAdmin
- A PostgreSQL database with pgAdmin4
- A multi-stage built and scaled ReactJS frontend with a NodeJS backend
- Nginx for load balancing
- Persistent volumes for database storage
- Proper service dependencies and environment variable management

---

## 📁 Project Structure

.
├── docker-compose.yaml
├── nginx.conf
├── react-node-scaled/
│ ├── react-app/
│ └── node-api/
├── mysql-phpmyadmin/
├── pgadmin-postgres/
├── screenshots/
└── README.md


---

## ⚙️ Services Overview

### 1️⃣ **MySQL + PHPMyAdmin**
- **MySQL** container exposed on port `3306`
- **PHPMyAdmin** exposed on port `8081`
- Environment variables set for DB credentials
- **Volume** used to persist MySQL data even after container restart

### 2️⃣ **PostgreSQL + pgAdmin4**
- **PostgreSQL** on port `5432`
- **pgAdmin4** UI on port `5050`
- `depends_on` ensures pgAdmin waits for the DB to be ready
- Volume attached to persist PostgreSQL data

### 3️⃣ **ReactJS Frontend + NodeJS Backend**
- **React App** is built using **multi-stage Docker build** for production
- **NodeJS API** serves as backend service
- React frontend is scaled using Docker Compose with 3 replicas
- Nginx handles **load balancing** across ReactJS replicas

### 4️⃣ **NGINX**
- Acts as a reverse proxy/load balancer for the React replicas
- Configured via custom `nginx.conf`

---

## 🧠 Docker Compose Concepts Used

- **Multiple services**
- **Environment variables**
- **Volumes for persistent storage**
- **Service dependencies with `depends_on`**
- **Multi-stage Docker builds**
- **Scaling services**
- **Load balancing with NGINX**

---

## 🛠️ How to Run the Project

1. Clone the repository:
   ```bash
   git clone https://github.com/KeerthanaGarimella/docker-compose-project.git
   cd docker-compose-project
