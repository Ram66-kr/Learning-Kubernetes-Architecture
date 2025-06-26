
##################################################################################################
DevOps Learning Journey – Kubernetes Architecture
###################################################################################################

Spent the day exploring Kubernetes and its core components.
Gained a better understanding of how it manages, schedules, and scales containers across clusters.


##  Core Concepts:
- **Docker → Container** | **Kubernetes (K8s) → Pods**
- **To run a container**, you need a **container runtime** (e.g., `containerd`, `CRI-O`).
In Kubernetes, container runtimes are responsible for running the containers within a pod.

---

##  Kubernetes Architecture

Kubernetes follows a **master-worker** architecture:

###  Control Plane (Master Components):
- **API Server:** The heart of Kubernetes. It exposes your cluster to the outside world.
- **Scheduler:** Schedules pods to nodes based on available resources.
- **etcd:** A distributed key-value store used to store all cluster data. Critical for backups and disaster recovery.
- **Controller Manager:** Manages core controller logic such as ReplicaSets, auto-scaling, and node lifecycle.
- **Cloud Controller Manager (CCM):** Integrates K8s with cloud providers like EKS, AKS, GKE.

 *Note:* CCM is not required for on-premise implementations. It helps Kubernetes understand cloud-native resources like load balancers and storage.

---

###  Data Plane (Worker Components):
- **Kubelet:** Ensures containers in a pod are running. If not, it notifies the control plane (supports auto-healing).
- **Container Runtime:** Executes the actual containers inside pods. Examples: `containerd`, `CRI-O`, Docker Shim (deprecated).
- **Kube-proxy:** Manages networking on the node. Handles:
  - IP address assignment
  - Load balancing
  - Network routing using iptables

---

 **Key Takeaway:** Kubernetes abstracts container management into a powerful architecture that supports scaling, healing, and multi-cloud operations.

 Fun fact: Kubernetes automatically restarts failed pods for high availability!
