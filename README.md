# DevTrack - Engineering Milestone Planner & GitHub Deployment Guide

A clean, professional developer workspace for planning software projects, mastering Git workflows, and safely storing project state behind an AES-256-GCM encrypted backend.

---

## 🔒 Security & Access Control

The backend includes zero-knowledge style encryption at rest:

- **Authenticated Encryption:** Data is encrypted using `AES-256-GCM` before being written to disk (`server/data/vault.enc.json`).
- **Master Authorization Key:** All read/write requests require an `X-Access-Key` header. Requests without the key receive `401 Unauthorized` and data on disk remains fully encrypted ciphertext.
- **Key Rotation:** The owner can rotate and update the master access key through the Security Vault interface or directly in `.env`.
- **Default Master Key:** Defined in `.env` as `MASTER_ACCESS_KEY=dev-secret-key-2026`. Change this to your private passphrase.

---

## 🛠️ Core Capabilities

### 1. 📋 Project Roadmaps & Architecture Milestones
- Structured phases: Setup, Architecture, Implementation, and Deployment.
- Implementation context (*"Why this step matters"*), starter templates, and common pitfall warnings.
- Clean progress tracking with zero distracting gimmicks.

### 2. 🚀 GitHub Deployment Pipeline
- **Method A (CLI):** Full command-line deployment pipeline (`git init`, `git add .`, `git commit`, `git remote add origin`, `git push -u origin main`) with personalized command generator.
- **Method B (Web):** Browser-only drag-and-drop guide for users avoiding the terminal.
- **Terminal Playground:** Safe sandbox terminal to practice Git commands with realistic outputs.

### 3. 📄 Documentation & Asset Generator
- **README.md Builder:** Generates clean, standardized GitHub project documentation with badges, features, and setup steps.
- **.gitignore Generator:** Pre-configured templates for Node.js, Python, Flutter, and Vanilla Web.

### 4. ⚠️ Developer Troubleshooting & Error Reference
- Searchable reference guide for common errors:
  - Git remote already exists, push rejected, PAT authentication.
  - CORS errors, undefined properties, mobile horizontal scrollbar bugs.
  - Windows PowerShell execution policy workarounds and port collisions (`EADDRINUSE`).

---

## 🚀 Running the Platform
1. Start both the encrypted backend server and the frontend client concurrently:
   ```bash
   npm.cmd run dev
   ```

2. Open your browser:
   - **Frontend App:** `http://localhost:5173`
   - **Encrypted Backend API:** `http://localhost:5000`

---
