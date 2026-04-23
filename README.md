# 🚀 Next.js Static Export with Docker, GHCR & CI/CD

## 📌 Overview

This project demonstrates how to build, containerize, and deploy a **Next.js static website** using modern DevOps practices.

The application is exported as **pure static HTML/CSS/JS** and served using **Nginx inside Docker**, with a fully automated **CI/CD pipeline using GitHub Actions**.

---

## 🎯 Objectives

* Build a Next.js application using TypeScript and Tailwind CSS
* Configure static export (no Node.js runtime required)
* Containerize the application using Docker (multi-stage build)
* Serve the app using Nginx (rootless container)
* Automate testing and deployment using GitHub Actions
* Publish Docker images to GitHub Container Registry (GHCR)
* Integrate Slack notifications for CI/CD events

---

## 🛠️ Tech Stack

| Layer            | Technology                       |
| ---------------- | -------------------------------- |
| Framework        | Next.js 16 (App Router)          |
| Language         | TypeScript                       |
| Styling          | Tailwind CSS                     |
| Package Manager  | pnpm                             |
| Containerization | Docker                           |
| Web Server       | Nginx (nginx-unprivileged)       |
| CI/CD            | GitHub Actions                   |
| Registry         | GitHub Container Registry (GHCR) |
| Notifications    | Slack Webhooks                   |

---

## 📁 Project Structure

```
my-app/
├── .github/
│   └── workflows/
│       └── ci-cd.yml        # CI/CD pipeline
├── app/                     # Next.js app directory
├── public/                  # Static assets
├── Dockerfile               # Multi-stage Docker build
├── compose.yml              # Docker Compose config
├── nginx.conf               # Nginx configuration
├── next.config.ts           # Static export config
├── package.json             # Project dependencies & scripts
└── pnpm-lock.yaml           # Lock file
```

---

## ⚙️ Setup Instructions

### 🔹 Prerequisites

Ensure the following are installed:

* Node.js (v24+)
* pnpm
* Docker
* Git

---

## 🧩 Step 1 — Install Dependencies

```
pnpm install
```

---

## ▶️ Step 2 — Run Development Server

```
pnpm dev
```

Open: http://localhost:3000

---

## 🏗️ Step 3 — Build Static Export

```
pnpm build
```

This generates a static output inside the `/out` directory.

---

## 🐳 Step 4 — Run with Docker

Build and start the container:

```
docker compose up -d --build
```

Open in browser:

```
http://localhost:8080
```

To stop:

```
docker compose down
```

---

## 🔄 CI/CD Pipeline

The project uses GitHub Actions for automation.

### ✅ On Pull Request:

* Runs linting
* Builds the project

### ✅ On Push to `main`:

* Runs tests
* Builds Docker image
* Pushes image to GHCR

---

## 📦 Docker Image

Published to:

```
ghcr.io/<your-username>/<your-repo>
```

Tags:

* `latest`
* `sha-<commit-id>`

---

## 💬 Slack Notifications

Slack is integrated to send deployment updates.

### Setup:

1. Create a Slack App
2. Enable Incoming Webhooks
3. Add webhook URL to GitHub Secrets:

```
SLACK_WEBHOOK_URL
```

---

## 🚀 Key Features

* ⚡ Static site (no backend runtime required)
* 🐳 Lightweight Docker image (Nginx only)
* 🔄 Automated CI/CD pipeline
* 📦 Container registry integration
* 🔔 Real-time deployment notifications

---

## 🧠 Learning Outcomes

* Understanding of static site generation in Next.js
* Hands-on experience with Docker multi-stage builds
* CI/CD pipeline creation using GitHub Actions
* Container registry usage (GHCR)
* Debugging real-world DevOps issues

---

## ⚠️ Common Issues

| Issue                 | Solution                                |
| --------------------- | --------------------------------------- |
| Docker not running    | Start Docker Desktop                    |
| No `out` folder       | Check `next.config.ts`                  |
| Build fails in Docker | Reinstall dependencies in builder stage |
| Port 8080 not working | Ensure no port conflict                 |

---

## 👨‍💻 Author

**Kenyi Oliver**

---

## 📌 Conclusion

This project demonstrates a complete modern DevOps workflow for deploying a frontend application using:

* Static site generation
* Containerization
* CI/CD automation

It provides a scalable and production-ready approach for frontend deployments.

---
