<div align="center">

<!-- HEADER BANNER -->
<img src="assets/header.svg" alt="Mahija Ibad Pradipta" width="100%" />

<br/><br/>

<!-- TYPING ANIMATION -->
<a href="https://portfolio.eeja.fun">
  <img src="https://readme-typing-svg.demolab.com?font=Fira+Code&weight=600&size=19&duration=2800&pause=1000&color=38BDF8&center=true&vCenter=true&width=500&height=42&lines=IoT+%26+Embedded+Systems;Full-Stack+Development;Infrastructure+%26+Homelab;Computer+Vision" alt="Engineering Disciplines" />
</a>

<br/>

<p align="center">
  Building practical systems across software, IoT fleets, self-hosted infrastructure, and computer vision.
</p>

<br/>

</div>

---

<br/>

## About

Computer Engineering graduate focused on building reliable, interconnected systems. My work spans microcontroller sensor hardware and edge cameras to full-stack web applications and on-device computer vision models.

```bash
$ whoami
Mahija Ibad Pradipta (Eeja07) • Computer Engineering Graduate
```

<br/>

---

<br/>

## Technologies

<div align="center">
  <img src="assets/skills-grid.svg" alt="Technical Stack and Disciplines" width="100%" />
</div>

<br/>

* **Software & Web:** Python, JavaScript, TypeScript, Node.js, Next.js 15, NestJS, Laravel 11, REST APIs
* **IoT & Embedded:** ESP32, ESP32-CAM, Raspberry Pi 5, MQTT (EMQX v5), WebSockets, Staged OTA
* **Computer Vision:** YOLOv8, OpenCV, ONNX Runtime, MAVSDK, Pixhawk 6C (PX4), FastAPI
* **Infrastructure:** Linux (Debian 12), Docker Compose, Cloudflare Tunnels, Tailscale, Nginx, PostgreSQL, MySQL, MinIO S3

<br/>

---

<br/>

## Featured Projects

<br/>

### Mivion — IoT Surveillance & Fleet Management

> Real-time IoT surveillance platform managing ESP32-CAM edge devices with MQTT messaging, WebSocket live feeds, staged OTA firmware deployment, and computer vision inference.

<div align="center">
  <img src="assets/project-mivion.svg" alt="Mivion IoT Platform Architecture" width="100%" />
</div>

<br/>

* **Telemetry & State Ingestion:** ESP32-CAM devices stream telemetry over MQTT to EMQX v5, while connection webhooks notify Laravel 11 to broadcast live device status via WebSockets (Laravel Reverb).
* **Automated Staged OTA Engine:** Uploads compiled `.bin` firmware to MinIO S3 with versioned `manifest.json` metadata and SHA256 checksums for controlled device rollouts.
* **Edge Vision & Retention Lifecycle:** Feeds uploaded snapshots to an asynchronous FastAPI detection service running YOLO human detection, backed by automated scheduled cleanup for 14-day image retention.

```text
Stack: Laravel 11 • EMQX v5 (MQTT) • MinIO (S3) • Laravel Reverb (WSS) • FastAPI • YOLOv8 • Docker • MySQL 8.0
```

[View Repository →](https://github.com/Eeja07/iot-surveillance-platform-web)

<br/>

---

<br/>

### Autonomous Search Drone — Pixhawk 6C & Edge Vision

> Autonomous search-and-rescue quadcopter platform pairing a Pixhawk 6C flight controller with an onboard Raspberry Pi 5 companion computer for real-time edge vision and offboard mission execution.

<div align="center">
  <img src="assets/project-drone.svg" alt="Autonomous Drone Search System Architecture" width="100%" />
</div>

<br/>

* **Companion & Autopilot Link:** Holybro S500 airframe and Pixhawk 6C (PX4) paired with a Raspberry Pi 5 companion computer communicating over high-baud UART via MAVLink.
* **On-Device Vision Pipeline:** Captures video frames using OpenCV and executes real-time target detection onboard using ONNX Runtime with `yolov8n320.onnx` without cloud dependency.
* **Autonomous Offboard Control:** Python control daemon powered by MAVSDK commands systematic search sweeps and coordinates target tracking with live video streaming via Flask.

```text
Stack: Python • MAVSDK • PX4 Autopilot • Pixhawk 6C • Raspberry Pi 5 • YOLOv8 • ONNX Runtime • OpenCV • Flask
```

[View Repository →](https://github.com/Eeja07/autonomus-human-search-system-using-drone-final-project-program)

<br/>

---

<br/>

### JobTracker — Full-Stack Monorepo Platform

> Job application tracking platform structured as a TypeScript monorepo with NestJS backend APIs, Next.js 15 frontend, and automated container security scans.

<div align="center">
  <img src="assets/project-jobtracker.svg" alt="JobTracker Monorepo Architecture" width="100%" />
</div>

<br/>

* **Turborepo Workspace Architecture:** Modular workspace isolating the NestJS REST API (`apps/api`), Next.js 15 web client (`apps/web`), and shared UI tokens (`packages/ui`).
* **Security & Data Persistence:** User authentication protected with memory-hard Argon2id password hashing, structured Pino logging, and PostgreSQL storage managed via Prisma ORM.
* **Automated CI/CD Quality Gates:** GitHub Actions workflow enforcing typechecks (`tsc --noEmit`), unit testing, and multi-stage Alpine Docker builds scanned with Trivy.

```text
Stack: NestJS • Next.js 15 • PostgreSQL • Prisma ORM • Turborepo • TypeScript • Docker • Trivy • Pino • Argon2id
```

[View Repository →](https://github.com/Eeja07/job-tracker)

<br/>

---

<br/>

## Current Focus

* **Distributed Systems:** Message-driven microservices, event streaming, and resilient state synchronization.
* **DevOps & Infrastructure:** CI/CD pipeline automation, container orchestration, and reproducible homelab deployments.
* **Edge AI Acceleration:** Model optimization, pruning, and low-latency inference on embedded ARM hardware.
* **Robotics & UAV Systems:** ROS 2 communication nodes and sensor fusion algorithms for autonomous aerial platforms.

<br/>

---

<br/>

## Activity

<div align="center">

<img src="https://github-readme-stats.vercel.app/api?username=Eeja07&show_icons=true&bg_color=0d1117&title_color=38bdf8&icon_color=60a5fa&text_color=8b949e&border_color=30363d" height="150" alt="GitHub Stats" />
&nbsp;
<img src="https://github-readme-stats.vercel.app/api/top-langs/?username=Eeja07&layout=compact&bg_color=0d1117&title_color=38bdf8&text_color=8b949e&border_color=30363d" height="150" alt="Top Languages" />

<br/><br/>

<img src="https://raw.githubusercontent.com/Eeja07/Eeja07/output/github-snake-dark.svg" alt="GitHub Contribution Snake Animation" width="100%" />

</div>

<br/>

---

<br/>

## Connect

* **Portfolio:** [portfolio.eeja.fun](https://portfolio.eeja.fun)
* **LinkedIn:** [linkedin.com/in/mahijapradipta](https://linkedin.com/in/mahijapradipta)
* **Email:** [mahijapradipta86@gmail.com](mailto:mahijapradipta86@gmail.com)
* **GitHub:** [github.com/Eeja07](https://github.com/Eeja07)

<br/>

<div align="center">
  <sub>Mahija Ibad Pradipta • Connected Systems &amp; Software</sub>
</div>
