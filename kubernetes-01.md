# 📚 Kubernetes Flashcards Cheat Sheet

This repository serves as a **flashcard-style revision guide** for important Kubernetes concepts — perfect for interviews and tech refresh.

---

## 1. ❓ What is Kubernetes, and how does it work?

<details>
<summary>Show Answer</summary>

Kubernetes is an open-source container orchestration platform that automates the deployment, scaling, and management of containerized applications.

It manages clusters of nodes and schedules containers (within Pods) across them while ensuring the desired state using controllers like Deployments.

</details>

---

## 2. ❓ Explain the difference between Deployments, StatefulSets, and DaemonSets.

<details>
<summary>Show Answer</summary>

- **Deployment:** Manages stateless applications, supports scaling, rolling updates, and rollback.
- **StatefulSet:** Manages stateful applications, provides stable network IDs and persistent storage.
- **DaemonSet:** Ensures a copy of a Pod runs on every (or selected) node in the cluster (e.g., for logging agents).

</details>

---

## 3. ❓ What are Pods, Services, and Ingress in Kubernetes?

<details>
<summary>Show Answer</summary>

- **Pod:** Smallest deployable unit; encapsulates one or more containers.
- **Service:** Stable endpoint (ClusterIP, NodePort, LoadBalancer) to access Pods.
- **Ingress:** Manages external HTTP(S) access to Services, with routing and TLS termination.

</details>

---

## 4. ❓ How does Kubernetes Networking work? (ClusterIP, NodePort, LoadBalancer)

<details>
<summary>Show Answer</summary>

- **ClusterIP:** Default service type; accessible only within the cluster.
- **NodePort:** Exposes service on each Node’s IP at a static port.
- **LoadBalancer:** Provisions an external load balancer (typically cloud-managed).

</details>

---

## 5. ❓ What is a ConfigMap and Secret in Kubernetes?

<details>
<summary>Show Answer</summary>

- **ConfigMap:** Stores non-sensitive key-value pairs (e.g., app configs).
- **Secret:** Stores sensitive data like passwords or API tokens, base64-encoded.

</details>

---

## 6. ❓ How do you debug a failing Pod?

<details>
<summary>Show Answer</summary>

- View logs:

    kubectl logs &lt;pod-name&gt;

- Describe Pod (events, reasons):

    kubectl describe pod &lt;pod-name&gt;

- Exec into Pod for troubleshooting:

    kubectl exec -it &lt;pod-name&gt; -- /bin/sh

</details>

---

## 7. ❓ What is Helm, and why is it used?

<details>
<summary>Show Answer</summary>

Helm is the package manager for Kubernetes.  
It simplifies defining, installing, and upgrading complex Kubernetes applications via reusable templates called Charts.

</details>

---

## 8. ❓ Explain Kubernetes Autoscaling (HPA, VPA, Cluster Autoscaler).

<details>
<summary>Show Answer</summary>

- **HPA (Horizontal Pod Autoscaler):** Scales Pods based on CPU/memory or custom metrics.
- **VPA (Vertical Pod Autoscaler):** Adjusts CPU/memory requests/limits for Pods.
- **Cluster Autoscaler:** Adds or removes Nodes based on overall cluster resource demand.

</details>

---

## 9. ❓ How do you manage Kubernetes RBAC?

<details>
<summary>Show Answer</summary>

RBAC (Role-Based Access Control) is managed via:

- **Roles/ClusterRoles:** Define permissions for resources.
- **RoleBindings/ClusterRoleBindings:** Assign roles to users, groups, or service accounts.

Example:

    kind: Role
    apiVersion: rbac.authorization.k8s.io/v1
    metadata:
      name: pod-reader
    rules:
    - apiGroups: [""]
      resources: ["pods"]
      verbs: ["get", "watch", "list"]

</details>

---

## 10. ❓ What is etcd, and why is it important in Kubernetes?

<details>
<summary>Show Answer</summary>

etcd is a distributed key-value store holding the entire cluster state (configuration, secrets, discovery data).

Kubernetes relies on etcd to maintain the desired and current state of the cluster.

</details>

---

## 📝 Contribution

Feel free to fork and contribute more flashcards!

## 🧩 License

MIT License
