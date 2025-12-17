# 🚀 High-Availability Containerized Web Cluster

![Docker](https://img.shields.io/badge/Docker-2CA5E0?style=for-the-badge&logo=docker&logoColor=white)
![Prometheus](https://img.shields.io/badge/Prometheus-E6522C?style=for-the-badge&logo=prometheus&logoColor=white)
![Grafana](https://img.shields.io/badge/Grafana-F46800?style=for-the-badge&logo=grafana&logoColor=white)
![HAProxy](https://img.shields.io/badge/HAProxy-106EBE?style=for-the-badge&logo=haproxy&logoColor=white)

## 📋 Project Overview
This project demonstrates a robust **DevOps Architecture** deploying three static websites behind a Load Balancer with a full monitoring stack. It is designed to be **Fault-Tolerant** and **Self-Healing**.

### 🏗️ Architecture Stack
* **Web Layer:** 3x Nginx Containers (Site 1, Site 2, Site 3).
* **Load Balancing:** HAProxy (Round-Robin Algorithm).
* **High Availability:** Keepalived (VRRP IP Failover).
* **Monitoring:**
    * **Prometheus:** Metrics Collection.
    * **cAdvisor:** Container Resource Usage (CPU/RAM).
    * **Grafana:** Real-time Visualization Dashboard.

---

## 🛠️ Installation & Setup

### Prerequisites
* Docker & Docker Compose installed.
* Linux Environment (Ubuntu recommended).

### 🚀 Quick Start
Run the following command to build and start the cluster:

```bash
docker-compose up -d --build
```

---

## 📊 Dashboard Access

| Service | URL | Description |
| :--- | :--- | :--- |
| **Load Balancer** | `http://localhost:8080` | Access the app (Cycles through Red/Green/Blue sites) |
| **Grafana** | `http://localhost:3000` | Visualization Dashboard (User/Pass: `admin`) |
| **Prometheus** | `http://localhost:9090` | Raw Metrics Database |

---

## 🧪 Testing Failover
To test the High Availability:
1. Stop a container manually: `docker stop site1`
2. Check the **Grafana Dashboard**.
3. You will see the status turn **RED (DOWN)** within 5-10 seconds.
4. HAProxy will automatically stop routing traffic to the dead container.

---

## 👤 Author
**Muhammad Saqib Afzal**
*DevOps Engineer*
