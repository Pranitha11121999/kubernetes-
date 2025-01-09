# **Kubernetes (K8s) Overview**

## **Why is Kubernetes called K8s?**
- The name **Kubernetes** originates from the Greek word for "helmsman" or "pilot."
- It is abbreviated as **K8s**:
  - The "8" represents the eight letters between the "K" and "s" in "Kubernetes."

---

## **Kubernetes Architecture**

### **Key Components**

1. **Master Node** (Control Plane):
   - Manages the cluster and oversees worker nodes.
   - Handles requests from external clients and assigns them to worker nodes.
   - Components:
     - **API Server**: The heart of Kubernetes, handling external requests.
     - **Scheduler**: Allocates resources on worker nodes.
     - **etcd**: A distributed key-value store holding the cluster state and configuration.
     - **Controller Manager**:
       - Manages controllers like replica sets, ensuring the desired state is maintained.
       - **Cloud Controller Manager**: Provides integration with cloud providers (e.g., AWS, GCP).

2. **Worker Nodes**:
   - Nodes where containers are deployed and executed.
   - Key Components:
     - **Kubelet**:
       - Ensures pods are running as expected.
       - Informs the master node if a pod fails.
     - **Kube Proxy**:
       - Manages networking within the cluster.
       - Acts as a load balancer, handles IP assignments, and ensures communication between pods.

---

### **Pod: The Fundamental Unit**
- A **Pod** is a wrapper around one or more containers.
- It provides additional capabilities beyond a standalone container:
  - Networking
  - Storage
  - Lifecycle management

---

### **Container Runtime**
- Kubernetes requires a container runtime to execute containers.
- Supported runtimes include:
  - **CRI-O**
  - **Containerd**
  - **Docker Shim** *(Note: Docker is not mandatory)*

---

### **Networking in Kubernetes**
- In Docker:
  - Networking is managed through `docker0` (a bridge network).
- In Kubernetes:
  - Networking is handled by **Kube Proxy**, which:
    - Acts like a load balancer.
    - Assigns IP addresses to pods.
    - Manages pod-to-pod and pod-to-service communication.

---

## **Why Do We Need the Control Plane?**
- The control plane is essential for enterprise-level applications:
  - It decides **what needs to happen and where** within the cluster.
  - Ensures the desired state of the cluster is maintained.

---

### **Summary of Kubernetes Master Components**

| **Component**         | **Description**                                                                 |
|------------------------|---------------------------------------------------------------------------------|
| **API Server**         | The central hub for all external and internal cluster requests.                |
| **Scheduler**          | Allocates resources on worker nodes for tasks and pods.                       |
| **etcd**               | A distributed key-value store containing cluster state and configurations.     |
| **Controller Manager** | Manages controllers like replica sets, ensuring desired state is met.          |
| **Cloud Controller**   | Provides cloud platform-specific support (e.g., AWS, GCP, Azure integrations). |

---

### **How Kubernetes Differs from Docker**
- In Docker:
  - Containers are created and managed individually.
  - Networking is limited to the host (single-node architecture).
- In Kubernetes:
  - Containers are grouped into **pods** for advanced management.
  - Clustered architecture ensures scalability, auto-healing, and load balancing.

