Here’s a GitHub `README.md` file designed as a **Kubernetes Flashcards Cheat Sheet** with **Questions & Answers** — great for quick revision:

---

## 📚 Kubernetes Flashcards Cheat Sheet

This repository serves as a **quick flashcard-style revision guide** for important Kubernetes concepts — ideal for interviews and daily technical refresh.

---

### 1. ❓ What is Kubernetes, and how does it work?

**Answer:**
Kubernetes is an open-source container orchestration platform that automates the deployment, scaling, and management of containerized applications.
It works by managing clusters of nodes (worker machines) and schedules containers (in Pods) to run on these nodes, maintaining desired state via controllers like Deployments.

---

### 2. ❓ Explain the difference between Deployments, StatefulSets, and DaemonSets.

| Resource        | Purpose                                                                                             |
| --------------- | --------------------------------------------------------------------------------------------------- |
| **Deployment**  | Manages stateless applications, supports scaling, rolling updates, and rollback.                    |
| **StatefulSet** | Manages stateful applications, provides stable network IDs and persistent storage.                  |
| **DaemonSet**   | Ensures a copy of a Pod runs on **every** (or selected) node in the cluster (e.g., logging agents). |

---

### 3. ❓ What are Pods, Services, and Ingress in Kubernetes?

* **Pod:** Smallest deployable unit; encapsulates one or more containers.
* **Service:** Stable endpoint (ClusterIP, NodePort, LoadBalancer) to access Pods.
* **Ingress:** Manages external HTTP(S) access to Services, with routing and TLS termination.

---

### 4. ❓ How does Kubernetes Networking work? (ClusterIP, NodePort, LoadBalancer)

| Type             | Description                                                   |
| ---------------- | ------------------------------------------------------------- |
| **ClusterIP**    | Default; accessible **only within the cluster**.              |
| **NodePort**     | Exposes service on each Node’s IP at a static port.           |
| **LoadBalancer** | Provisions an external load balancer (usually cloud-managed). |

---

### 5. ❓ What is a ConfigMap and Secret in Kubernetes?

* **ConfigMap:** Stores non-sensitive key-value pairs (e.g., app configs).
* **Secret:** Stores sensitive data like passwords or API tokens, base64-encoded.

---

### 6. ❓ How do you debug a failing Pod?

* View logs:

  ```bash
  kubectl logs <pod-name>
  ```
* Describe Pod (events, reasons):

  ```bash
  kubectl describe pod <pod-name>
  ```
* Exec into Pod for troubleshooting:

  ```bash
  kubectl exec -it <pod-name> -- /bin/sh
  ```

---

### 7. ❓ What is Helm, and why is it used?

**Answer:**
Helm is the **package manager for Kubernetes**, used to define, install, and upgrade complex Kubernetes applications via reusable templates called **Charts**.

---

### 8. ❓ Explain Kubernetes Autoscaling (HPA, VPA, Cluster Autoscaler).

| Autoscaler             | Function                                                   |
| ---------------------- | ---------------------------------------------------------- |
| **HPA (Horizontal)**   | Scales Pods based on CPU/memory or custom metrics.         |
| **VPA (Vertical)**     | Adjusts CPU/memory **requests/limits** for Pods.           |
| **Cluster Autoscaler** | Adds/removes Nodes based on cluster-wide Pod requirements. |

---

### 9. ❓ How do you manage Kubernetes RBAC?

* RBAC (**Role-Based Access Control**) is managed via:

  * **Roles/ClusterRoles:** Define permissions.
  * **RoleBindings/ClusterRoleBindings:** Assign roles to users, groups, or service accounts.

```yaml
kind: Role
apiVersion: rbac.authorization.k8s.io/v1
metadata:
  name: pod-reader
rules:
- apiGroups: [""]
  resources: ["pods"]
  verbs: ["get", "watch", "list"]
```

---

### 10. ❓ What is etcd, and why is it important in Kubernetes?

**Answer:**
`etcd` is a **distributed key-value store** that holds all cluster state data (configurations, secrets, service discovery info).
Kubernetes control plane relies on `etcd` to manage desired and current cluster state.

---

## 📝 Contribution

Feel free to fork and contribute more flashcards!

---

## 🧩 License

MIT License

---

If you want, I can generate this as a ready-to-use `README.md` file for you to directly put into a GitHub repo. Let me know!
