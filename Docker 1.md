# Docker 1 — Introduction to Containers

## 1. Real Problem in Software Development

Developers often face a common issue:

> **"It works on my machine."**

This happens because different systems may have different environments.

Common causes:

* Different operating systems
* Different runtime versions
* Missing dependencies
* Missing or incorrect environment variables

Because of this, an application that runs perfectly on one developer's machine may fail on another system or production server.

---

# 2. Background Concepts

Before understanding Docker, it is useful to understand three related technologies:

* Simulator
* Emulator
* Virtualization

---

# 3. Simulator

A **simulator** does not replicate the real system exactly.
It only **imitates the behavior of the system** using models.

### Examples

1. Flight simulator
2. Network simulator

### Simulator Flow

```
Real System
↓
Mathematical / logical model
↓
Simulator software
↓
Simulated output / behavior
```

Simulators are mainly used for:

* Training
* Testing
* Prediction

---

# 4. Emulator

An **emulator imitates hardware** so that software designed for one system can run on another system.

### Examples

1. Android Emulator
2. PlayStation Emulator

### Emulator Flow

```
Hardware (x86 laptop)
↓
Host OS
↓
Emulator software
↓
Emulated hardware (pretending to be ARM)
↓
Guest OS
↓
Application
```

Key idea:

The emulator pretends to be another machine's hardware so that its operating system and applications can run.

---

# 5. Virtualization

**Virtualization creates multiple virtual computers on one physical machine.**

### Examples

1. VirtualBox
2. VMware
3. Hyper-V

### Virtualization Flow

```
Hardware
↓
Host OS (Windows / Mac / Linux)
↓
Hypervisor (VirtualBox / VMware)
↓
VM1 → Ubuntu
VM2 → Kali
VM3 → Windows Server
```

Each Virtual Machine contains:

* A Guest OS
* Libraries
* Applications

---

# 6. Technology Comparison

| Technology     | What it imitates     | Example          |
| -------------- | -------------------- | ---------------- |
| Simulator      | Behaviour            | Flight simulator |
| Emulator       | Hardware             | Android emulator |
| Virtualization | Computer environment | VirtualBox       |

---

# 7. Why Virtual Machines Are Not Always Ideal

Virtual machines are powerful but they have limitations.

Every VM requires:

* A full operating system
* Dedicated memory
* Storage space
* Boot time

This makes them:

* Heavy
* Slower to start
* Resource intensive

Engineers therefore asked:

> If we only want to isolate the **application**, do we really need a full operating system?

---

# 8. Introduction to Docker

Docker provides a solution using **containers**.

Instead of running full operating systems, containers run applications in isolated environments while sharing the host operating system kernel.

### Docker Architecture Flow

```
Hardware
↓
Host OS
↓
Docker Engine
↓
Containers
↓
Applications
```

Containers are:

* Lightweight
* Fast to start
* Efficient in resource usage

---

# 9. Docker vs Virtual Machines

| Feature        | Virtual Machine | Docker             |
| -------------- | --------------- | ------------------ |
| OS             | Full Guest OS   | Shares Host Kernel |
| Size           | Large           | Small              |
| Startup Time   | Slow            | Fast               |
| Resource Usage | High            | Low                |

---

# 10. Docker Image vs Docker Container

This is an important concept.

### Docker Image

A **Docker image** is a template used to create containers.

Analogy:

> Image = Blueprint / Recipe

It contains:

* Application code
* Runtime
* Libraries
* Dependencies
* Configuration

### Docker Container

A **Docker container** is a running instance of an image.

Analogy:

> Container = Running instance / Cooked dish

---

# 11. Core Docker Components

Students should remember these **five core components**:

1. Docker Engine
2. Image
3. Container
4. Volume
5. Network

---

# 12. Docker Configuration Capabilities

Docker allows configuration of the application environment.

Common configurations include:

1. Runtime configuration (Node, Python, Java versions)
2. Environment variables
3. Port mapping
4. Volumes / storage configuration
5. Networking configuration
6. Resource limits (CPU, RAM)
7. File system configuration (copy / mount files)
8. Startup command configuration (CMD / ENTRYPOINT)
9. Image build configuration (Dockerfile setup)
10. Security configuration (users, permissions)

---

# 13. Basic Docker Commands

These are some commonly used Docker commands.

### Pull an image

Downloads an image from a registry.

```
docker pull nginx
```

---

### List images

Shows images available locally.

```
docker images
```

---

### Run a container

Creates and starts a container from an image.

```
docker run nginx
```

---

### Run container with port mapping

Maps host port to container port.

```
docker run -p 8080:80 nginx
```

---

### List running containers

```
docker ps
```

---

### List all containers

```
docker ps -a
```

---

### Stop a container

```
docker stop <container_id>
```

---

### Remove a container

```
docker rm <container_id>
```

---

### Remove an image

```
docker rmi <image_name>
```

---

### View container logs

```
docker logs <container_id>
```

---

### Execute command inside container

```
docker exec -it <container_id> bash
```

---

# Summary

The evolution of environment management can be understood as:

```
Simulator
↓
Emulator
↓
Virtualization
↓
Containers
↓
Docker
```

Docker simplifies application deployment by packaging the **application and its environment** into containers that run consistently across systems.
