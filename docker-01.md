## 1. ❓ What is Docker, and how does it differ from a VM?

<details>
<summary>Show Answer</summary>

Docker is a containerization platform that packages applications and their dependencies into containers.

**Difference from VM:**
- Docker containers share the host OS kernel and are lightweight.
- VMs run a full guest OS on top of a hypervisor, consuming more resources.

</details>

---

## 2. ❓ Explain the Docker Architecture (Docker Engine, Images, Containers, Registry).

<details>
<summary>Show Answer</summary>

- **Docker Engine:** Core component running the Docker daemon (`dockerd`).
- **Images:** Read-only templates used to create containers.
- **Containers:** Running instances of Docker images.
- **Registry:** Stores and distributes Docker images (e.g., Docker Hub).

</details>

---

## 3. ❓ What is a Dockerfile, and how do you optimize it? (Multi-stage builds)

<details>
<summary>Show Answer</summary>

A **Dockerfile** is a script defining instructions to build a Docker image.

**Optimization tips:**
- Use Multi-stage builds to reduce image size:

```

FROM golang\:alpine AS builder
WORKDIR /app
COPY . .
RUN go build -o app

FROM alpine
COPY --from=builder /app/app .
CMD \["./app"]

```

- Minimize layers and avoid unnecessary files.

</details>

---

## 4. ❓ How do Docker Volumes work, and why are they needed?

<details>
<summary>Show Answer</summary>

**Docker Volumes** store persistent data independent of container lifecycle.

- Created using:

```

docker volume create my\_volume

```

- Needed for:
  - Data persistence across container restarts.
  - Sharing data between containers.
  - Isolated storage managed by Docker.

</details>

---

## 5. ❓ What is the difference between docker run, docker exec, and docker attach?

<details>
<summary>Show Answer</summary>

- **docker run:** Creates and starts a new container.
- **docker exec:** Runs a command in an already running container.
- **docker attach:** Connects to a running container’s standard input/output.

</details>

---

## 6. ❓ Explain Docker Networking (Bridge, Host, None, Overlay).

<details>
<summary>Show Answer</summary>

- **Bridge:** Default network; containers can communicate via the bridge.
- **Host:** Container shares the host's network namespace.
- **None:** Disables networking for the container.
- **Overlay:** Enables communication between containers across multiple Docker hosts (Swarm/Kubernetes).

</details>

---

## 7. ❓ How do you clean up unused Docker resources? (docker system prune)

<details>
<summary>Show Answer</summary>

To remove unused containers, images, volumes, and networks:

```

docker system prune

```

For an even deeper clean:

```

docker system prune -a --volumes

```

</details>

---

## 8. ❓ What is Docker Compose, and how is it used?

<details>
<summary>Show Answer</summary>

**Docker Compose** is a tool to define and run multi-container Docker applications using a `docker-compose.yml` file.

Usage:

```

docker-compose up -d
docker-compose down

```

It simplifies defining services, networks, and volumes for applications.

</details>

---

## 9. ❓ How do you secure Docker containers? (Best practices)

<details>
<summary>Show Answer</summary>

- Use minimal base images (e.g., `alpine`).
- Drop unnecessary capabilities (`--cap-drop`).
- Run containers as non-root users.
- Regularly scan images for vulnerabilities.
- Use signed images (Docker Content Trust).

</details>

---

## 10. ❓ What is Docker Swarm, and how does it compare to Kubernetes?

<details>
<summary>Show Answer</summary>

**Docker Swarm** is Docker’s native clustering and orchestration tool.

**Docker Swarm vs Kubernetes:**
- Swarm: Simpler setup, Docker-integrated, less feature-rich.
- Kubernetes: Advanced orchestration, scalable, widely adopted in production.

</details>


