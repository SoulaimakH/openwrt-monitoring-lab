# OpenWRT – Suricata – Wazuh Security Monitoring Lab

## 📌 Project Overview

This project demonstrates a **network security monitoring lab** where:

- **OpenWRT** acts as the gateway router
- **Traffic is mirrored (SPAN)** from OpenWRT
- **Suricata IDS** is deployed in Docker on an **Ubuntu server**
- **Wazuh SIEM** collects and visualizes security alerts
- **Kali Linux** is used to generate attacks and test vulnerabilities

The goal is to simulate real-world attacks and verify detection using IDS and SIEM tools.

---

## 🧱 Architecture

![Network Diagram](archi.png)

### Components
- **OpenWRT Router**
  - Routes internal traffic
  - Mirrors traffic only to Suricata through a private network
- **Ubuntu Server**
  - Dockerized Suricata IDS
  - Dockerized Wazuh Manager & Dashboard
- **Kali Linux**
  - Vulnerability scanning & attack simulation

---

## 🔀 Traffic Flow

1. Internal devices communicate through OpenWRT
2. OpenWRT mirrors traffic (port mirroring)
3. Mirrored traffic is sent to Suricata (private network only)
4. Suricata analyzes packets and generates alerts
5. Alerts are forwarded to Wazuh SIEM
6. Wazuh visualizes alerts on the dashboard

---

## 🛠 Technologies Used

- OpenWRT
- Suricata IDS
- Wazuh SIEM
- Docker & Docker Compose
- Kali Linux
- Ubuntu Server
- Nmap, Nikto, Hydra

---

## ⚙️ Configuration Steps

### 1️⃣ OpenWRT – Traffic Mirroring
See:
```text
openwrt/port-mirroring.md
