# **Learn Kubernetes Practically (Free)**

## **Resources**
- **All Labs Page**: [Explore Labs](https://kode.wiki/3RxQ3dL)
- **Familiarize with Environment**: [Get Started](https://kode.wiki/4etu01y)
- **Pods**: [Learn About Pods](https://kode.wiki/3KIMDRL)
- **Replica Sets**: [Learn About Replica Sets](https://kode.wiki/3RxA8Mt)
- **Deployments**: [Learn About Deployments](https://kode.wiki/4c3YUw7)
- **Rolling Updates and Rollbacks**: [Learn Rolling Updates](https://kode.wiki/4cpKxSo)
- **Services**: [Learn About Services](https://kode.wiki/45pFOhr)

---

## **Day 1: Understanding Containers and Kubernetes**

### **Containers**
- Containers are **ephemeral** in nature—short-lived and can be recreated anytime.
- They isolate applications and make deployment easy.

#### **Docker vs. Kubernetes**
| **Feature**       | **Docker**                                | **Kubernetes**                              |
|--------------------|-------------------------------------------|---------------------------------------------|
| **Purpose**        | Simplifies the container journey         | Orchestrates and manages containers         |
| **Key Function**   | Runs containers on a single host         | Manages multiple containers across clusters |

---

### **Challenges in Docker**

#### **Problem 1: Single Host Limitation**
- **Scenario**: With 100 containers running on a single host, if one container consumes excessive resources, others may not function effectively.
- **Impact**: Resource contention due to single-host architecture.

#### **Problem 2: Auto-Healing**
- **Scenario**: If a container is stopped or killed, the application running inside it also stops.
- **Need**: The container must automatically restart without user intervention.

#### **Problem 3: Auto-Scaling**
- **Scenario**: EC2 instance hosting Docker has fixed resources (e.g., 4GB RAM, 4 CPUs). When website traffic increases or decreases, the container cannot scale automatically.
- **Impact**: Resource limits cause performance bottlenecks.

#### **Problem 4: Enterprise-Level Support**
- **Scenario**: Docker is a simple platform and lacks support for advanced enterprise features.

---

### **How Kubernetes Solves These Problems**

#### **Problem 1: Single Host Limitation**
- Kubernetes operates as a **cluster**:
  - Cluster consists of a **Master Node** (control plane) and multiple **Worker Nodes**.
  - Resources are distributed across nodes.

#### **Problem 2: Auto-Healing**
- Kubernetes uses:
  - **Replication Controller**: Ensures desired pod count is maintained.
  - **Deployment YAML Files**: Define configurations for containers.
  - **Horizontal Pod Autoscaler**: Automatically adjusts the number of pods based on resource usage.

#### **Problem 3: Auto-Scaling**
- Kubernetes monitors and manages resources with an API service:
  - Regularly checks pod health and updates or restarts containers if necessary.
  - Scales up/down pods based on traffic and load.

#### **Problem 4: Enterprise-Level Support**
- Kubernetes supports integration with external tools to enable enterprise-level features, such as:
  - Monitoring (e.g., Prometheus, Grafana)
  - Security (e.g., Istio, Calico)
  - CI/CD (e.g., Jenkins, GitLab)

---

### **Key Kubernetes Concepts**
- **YAML Files**: Core configuration files for defining deployments, pods, and services.
- **Replication Controller**: Ensures the required number of pod replicas are always running.
- **Horizontal Pod Autoscaler**: Dynamically adjusts the number of pods based on load.

---

### **Real-World Use Cases for Kubernetes**
1. **Application Deployment**: Run and scale web applications automatically.
2. **CI/CD Pipelines**: Optimize build and deployment pipelines.
3. **Containerization**: Manage microservices using pods.
4. **Monitoring**: Automatically recover failed containers.
5. **Traffic Management**: Handle high-traffic applications with ease.
