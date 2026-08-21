<div align="center">

<!-- 01. HERO NETWORK -->
<img src="assets/hero-network.svg" alt="Mahija Ibad Pradipta - Connected Systems Network Topology" width="100%" />

<br/><br/>

<!-- NAVIGATION -->
<p align="center">
  <a href="#-system--whoami"><code>[ ABOUT ]</code></a> &nbsp;•&nbsp;
  <a href="#-technology-topology"><code>[ TECHNOLOGY ]</code></a> &nbsp;•&nbsp;
  <a href="#-featured-projects"><code>[ PROJECTS ]</code></a> &nbsp;•&nbsp;
  <a href="#-system-incidents--solutions"><code>[ INCIDENTS ]</code></a> &nbsp;•&nbsp;
  <a href="#-homelab-infrastructure"><code>[ HOMELAB ]</code></a> &nbsp;•&nbsp;
  <a href="#-system-activity"><code>[ ACTIVITY ]</code></a> &nbsp;•&nbsp;
  <a href="#-contact--directory"><code>[ CONTACT ]</code></a>
</p>

</div>

---

## 🖥️ SYSTEM / WHOAMI

```bash
$ whoami
Mahija Ibad Pradipta (Eeja07)
Computer Engineering Graduate building interconnected systems across
self-hosted infrastructure, IoT fleets, full-stack software, and edge computer vision.

$ system --capabilities
[OK] Infrastructure & Linux  -> Debian 12, Docker Compose, Cloudflare Tunnels, Tailscale, Nginx
[OK] IoT & Embedded Systems  -> ESP32-CAM, Raspberry Pi 5, EMQX (MQTT v5), WebSockets, Staged OTA
[OK] Full-Stack Engineering  -> TypeScript, NestJS, Next.js 15, Laravel 11, PostgreSQL, MySQL, MinIO
[OK] Edge AI & Vision        -> YOLOv8 Object Detection, ONNX Runtime, OpenCV, MAVSDK / PX4
[OK] DevOps & Testing        -> Multi-stage Alpine Containerization, Trivy Security Scans, CI/CD

$ network --telemetry
HOST_DOMAIN : portfolio.eeja.fun
LOCATION    : Indonesia (UTC+7 / WIB)
STATUS      : Open to Software Engineering, Infrastructure & IoT Systems Roles
```

---

## 🌐 TECHNOLOGY TOPOLOGY

<div align="center">
  <img src="assets/tech-topology.svg" alt="Technology Network Topology" width="100%" />
</div>

<br/>

| Subsystem Domain | Core Technologies & Protocols | Role in Stack |
| :--- | :--- | :--- |
| **Infrastructure & Network** | `Debian 12` `Docker Compose` `Cloudflare Tunnels` `Tailscale` `Nginx` `CI/CD` | Zero-trust ingress, containerization, encrypted mesh overlay |
| **Backend & Full-Stack** | `TypeScript` `NestJS` `Next.js 15` `Laravel 11` `PostgreSQL` `Prisma` `MinIO` `FastAPI` | REST APIs, Server-Side Rendering, relational data, object storage |
| **IoT & Embedded Fleets** | `ESP32 / ESP32-CAM` `Raspberry Pi 5` `EMQX MQTT v5` `Laravel Reverb` `OTA Pipelines` | Distributed telemetry capture, live streaming, firmware deployments |
| **Edge AI & Computer Vision** | `YOLOv8` `ONNX Runtime` `OpenCV` `MAVSDK / MAVLink` `Pixhawk 6C (PX4)` | On-device model execution, target detection, autonomous flight |

---

## 🛰️ FEATURED PROJECTS

---

### `NODE_01` — Mivion: IoT Surveillance & Fleet Management Platform

> Real-time IoT surveillance platform designed for managing fleets of edge cameras, ingesting telemetry, and orchestrating staged OTA firmware rollouts.

<div align="center">
  <img src="assets/arch-mivion.svg" alt="Mivion IoT Architecture Diagram" width="100%" />
</div>

* **Decoupled Telemetry & Event Ingestion:** ESP32-CAM devices stream telemetry via MQTT to EMQX v5, while connection webhooks synchronize device state to Laravel 11 for live dashboard broadcasting via WebSockets (Laravel Reverb).
* **Automated Staged OTA Engine:** Uploads compiled `.bin` firmware binaries to MinIO S3 storage, generates versioned `manifest.json` metadata with SHA256 checksums, and dispatches rollout triggers over MQTT.
* **Edge Vision & Storage Lifecycle:** Integrates an asynchronous FastAPI service for YOLO object detection postbacks and runs automated scheduled tasks to prune historical MinIO images older than 14 days.

```text
Stack: Laravel 11 • EMQX v5 (MQTT) • MinIO (S3) • Laravel Reverb • FastAPI • YOLOv8 • Docker • MySQL
```
👉 [View Repository →](https://github.com/Eeja07/iot-surveillance-platform-web)

---

### `NODE_02` — Autonomous Human Search System using Drone

> Autonomous search-and-rescue quadcopter platform integrating a Pixhawk 6C autopilot with an onboard Raspberry Pi 5 companion computer for real-time vision and offboard flight control.

<div align="center">
  <img src="assets/arch-drone.svg" alt="Autonomous Drone Search System Architecture" width="100%" />
</div>

* **Companion Computer & Autopilot Integration:** Pairs a Holybro S500 quadcopter airframe and Pixhawk 6C flight controller (PX4) with a Raspberry Pi 5 communicating over high-baud UART via MAVLink.
* **On-Device Vision Pipeline:** Captures video frames using OpenCV and executes target detection onboard via ONNX Runtime using the `yolov8n320.onnx` model without requiring cloud connectivity.
* **Offboard Mission Control:** Python-based control service utilizing MAVSDK executes systematic search patterns and coordinates target tracking with live video streaming via Flask.

```text
Stack: Python • MAVSDK • PX4 Autopilot • Pixhawk 6C • Raspberry Pi 5 • YOLOv8 • ONNX Runtime • OpenCV • Flask
```
👉 [View Repository →](https://github.com/Eeja07/autonomus-human-search-system-using-drone-final-project-program)

---

### `NODE_03` — JobTracker Monorepo & API Platform

> Job application tracking platform structured as a TypeScript monorepo with NestJS backend APIs, Next.js frontend, and automated container security scans.

<div align="center">
  <img src="assets/arch-jobtracker.svg" alt="JobTracker Architecture Diagram" width="100%" />
</div>

* **Turborepo Workspace Architecture:** Modular monorepo isolating `apps/api` (NestJS REST API), `apps/web` (Next.js frontend), and `packages/ui` (shared design tokens and components).
* **Security & Data Layer:** Passwords secured with memory-hard Argon2id hashing, structured JSON logging via Pino, and relational data management powered by Prisma ORM and PostgreSQL.
* **Automated CI/CD Quality Gates:** GitHub Actions pipeline enforcing frozen lockfile builds, typechecking (`tsc --noEmit`), automated unit tests, multi-stage Alpine Docker builds, and Trivy container vulnerability scanning.

```text
Stack: NestJS • Next.js 15 • PostgreSQL • Prisma ORM • Turborepo • TypeScript • Docker • Trivy • Pino • Argon2id
```
👉 [View Repository →](https://github.com/Eeja07/job-tracker)

---

## 🛠️ SYSTEM INCIDENTS & SOLUTIONS

```text
INCIDENT #001: ESP32-CAM Stale Socket Exhaustion on Network Disconnect

Problem
ESP32-CAM clients remained in a connected state locally after abrupt Wi-Fi drops,
failing to receive new MQTT commands or stream telemetry frames.

Investigation
Unclean network drops without standard TCP FIN packets left half-open sockets active
on the microcontroller, consuming limited LWIP socket descriptors.

Resolution
Implemented application-level heartbeat timeouts on the client, exponential backoff
reconnection logic with explicit socket cleanup, and EMQX webhook client status tracking.

STATUS: RESOLVED
```

```text
INCIDENT #002: Companion Computer Inference Latency & Frame Buffering

Problem
Running standard model inference synchronously inside the video capture loop introduced
frame pipeline delays and degraded the responsiveness of the offboard control loop.

Investigation
Synchronous frame ingestion blocked execution between camera I/O and matrix operations,
causing frame queue latency on the companion computer.

Resolution
Exported the model to an optimized ONNX format (yolov8n320.onnx) for ONNX Runtime execution
and decoupled camera ingestion into a dedicated threaded frame reader.

STATUS: RESOLVED
```

---

## 🏛️ HOMELAB INFRASTRUCTURE

<div align="center">
  <img src="assets/homelab-topology.svg" alt="Homelab & Cloud Infrastructure Topology" width="100%" />
</div>

<br/>

```text
┌────────────────────────────────────────────────────────────────────────┐
│ 1. EDGE INGRESS LAYER                                                  │
│    • Cloudflare Zero-Trust Tunnel (cloudflared daemon)                 │
│    • Domain Routing: *.eeja.fun -> Local Container Ports               │
├────────────────────────────────────────────────────────────────────────┤
│ 2. SECURE MANAGEMENT OVERLAY                                           │
│    • Tailscale WireGuard Mesh VPN for encrypted administrative access  │
├────────────────────────────────────────────────────────────────────────┤
│ 3. HOST RUNTIME (Debian 12 Bookworm)                                   │
│    • Docker Compose isolated bridge networks                           │
│    • Running: Portfolio, EMQX MQTT Broker, MinIO S3, Postgres & MySQL  │
└────────────────────────────────────────────────────────────────────────┘
```

---

## 📊 SYSTEM ACTIVITY

<div align="center">

<img src="https://github-readme-stats.vercel.app/api?username=Eeja07&show_icons=true&theme=tokyonight&hide_border=true&bg_color=090d16&title_color=00e5ff&icon_color=38bdf8&text_color=94a3b8" height="145" alt="GitHub Stats" />
<img src="https://github-readme-stats.vercel.app/api/top-langs/?username=Eeja07&layout=compact&theme=tokyonight&hide_border=true&bg_color=090d16&title_color=a855f7&text_color=94a3b8" height="145" alt="Top Languages" />

</div>

---

## 📡 CONTACT / DIRECTORY

```bash
$ connect --target mahija
[EMAIL]     -> mahijapradipta86@gmail.com
[PORTFOLIO] -> https://portfolio.eeja.fun
[GITHUB]    -> https://github.com/Eeja07
[LINKEDIN]  -> https://linkedin.com/in/mahijapradipta
[LOCATION]  -> Indonesia (GMT+7)
```

<div align="center">
  <sub>Engineered by <b>Mahija Ibad Pradipta</b> • Connected Systems Lab</sub>
</div>
