# ⚡ Splunk Security Operations Lab 🧠

<img width="400" height="186" alt="rmIiKm1" src="https://github.com/user-attachments/assets/ff0bd4cc-3f16-4162-bda8-becb0283bbe3" />

Welcome to my Home SOC Lab project!  
This repository documents the creation of a **Splunk Enterprise Security (ES)** lab — simulating a mini **Security Operations Center (SOC)**.  
The lab started with Ubuntu virtual machines, but Phase 6 transitions to using **Docker on Windows 11 Pro** to make the lab faster, more flexible, and easier to reset.  
The lab is designed for hands-on learning in **log ingestion, alerting, and monitoring workflows**, and serves as a **practical journal** of my progress.

---

## 🎯 Objectives
- Build a **home SIEM environment** with Splunk Enterprise  
- Configure **server and endpoint VMs or Docker container** for log ingestion  
- Practice **SOC workflows**, including alert triage and data visualization  
- Document the process for **continuous learning and reference**  
- Maintain a **step-by-step journal** of lab activities for GitHub  
- Troubleshoot **permissions, disk space, and container issues** in Splunk  

---

## 🏗️ Lab Environment
| Component      | Platform / Setup                          | Function / Context |
|----------------|------------------------------------------|------------------|
| Splunk Server  | Ubuntu 22.04 VM (original) <br> Docker container on Windows 11 Pro x64 | Hosts Splunk Enterprise & Enterprise Security. Using Docker allows me to spin up Splunk quickly without managing full VMs, making it easier to experiment and reset environments. |
| Endpoint       | Ubuntu VM / Windows Host                  | Generates logs for ingestion. On Windows, logs are created and copied into the Docker container, simulating endpoint → SOC workflow. |
| Network        | Virtual Network / Host-only / NAT / Docker port mapping | Ensures connectivity between endpoint, host, and container. Ports 8000 (Web) and 9997 (Forwarder) are mapped from Docker container to Windows host for Splunk access and data ingestion. |
| Tools / Tech   | Docker Desktop, WSL2, Splunk Enterprise container image | Docker + WSL2 allows lightweight SOC lab setup. Tools let me experiment with log ingestion, searches, and dashboards without VM setup time. Keeps the lab environment flexible and disposable. |
| Security Tools | **Phase VII — Sysmon & Suricata** on Windows 11 Host | Captures Windows event logs and network traffic. Sysmon collects endpoint events; Suricata captures network traffic. Logs are exported/imported into Docker Splunk for analysis while keeping Windows host clean. |

---

# 🗂️ Lab Directory

| Phase | 
|-------|
| [🚀 Phase I — Environment Setup 🧱](https://github.com/Jose01000111/SplunkES-Phase-1.git) |
| [🚀 Phase II — Splunk Installation 🧩](https://github.com/Jose01000111/Phase-II-Splunk-Installation.git) |
| [🚀 Phase III — GUI Exploration & Disk Space Troubleshooting 🛠️](https://github.com/Jose01000111/Phase-III-GUI-Exploration-Disk-Space-Troubleshooting-Splunk-Server-Issue-.git) | 
| [🚀 Phase III.V — Rebuild Endpoint/Server Connection 🔄](https://github.com/Jose01000111/Phase-III.V-Rebuild-Endpoint-Connection.git) |
| [🚀 Phase IV — GUI Discovery 🔑](https://github.com/Jose01000111/Phase-IV-Splunk-GUI-Discovery.git) |
| [🚀 Phase VI — Docker-Based Splunk SOC Lab 🐳](https://github.com/Jose01000111/Docker-Based-Splunk-SOC-Lab-.git) |
| [🚀 Phase VII — Windows 11 + Sysmon + Suricata ⚡](https://github.com/Jose01000111/Export-and-Ingest-Sysmon-Logs-into-Splunk.git) |

---

## 📝 Lab Progress Overview

- **Phase I — Environment Setup 🧱**  
  - Updated and cleaned Ubuntu VMs  
  - Created project folders for lab files and logs  
  - Gathered system info (OS, IPs, hostname)  
  - Verified network connectivity between VMs  

- **Phase II — Splunk Installation 🧩**  
  - Downloaded and installed Splunk Enterprise on server VM  
  - Configured firewall and opened required ports (8000, 8089)  
  - Created admin credentials and verified web access  
  - Verified Splunk service and indexes  

- **Phase III — GUI Exploration & Disk Space Troubleshooting 🛠️**  
  - Attempted to explore the Splunk GUI but indexing was blocked due to low disk space  
  - Checked server disk usage and identified temporary files and large logs as potential space sources  
  - Removed temporary dispatch files, cleared caches, moved large logs  
  - Verified free space after cleanup but indexing did not fully resume  
  - Determined underlying VM disk size was insufficient and needed resizing  

- **Phase IV — GUI Discovery 🔑**  
  - Explored the Splunk dashboard, default panels, and menus  
  - Reviewed default indexes `_internal`, `_audit`, `_introspection`  
  - Navigated menus including **Search & Reporting**, **Settings**, and **Apps**  

- **Phase VI — Docker-Based Splunk SOC Lab 🐳**  
  - Pulled Splunk Enterprise container image and ran on Windows 11 Pro x64  
  - Containers allowed me to spin up Splunk without a full VM  
  - Mapped ports 8000 (Web) and 9997 (Forwarder) from container to host  
  - Created sample logs on Windows host and ingested into Docker-based Splunk  
  - Verified logs appeared in Splunk searches, confirming end-to-end ingestion workflow  
  - Practiced starting/stopping container and observed persistence of data  

- **Phase VII — Windows 11 + Sysmon + Suricata ⚡**  
  - Captured **Windows events** via Sysmon and **network events** via Suricata  
  - Ingested logs into Docker Splunk while keeping Windows host clean  
  - Practiced container isolation, log export/import, and basic network monitoring  

---

## ⏩ Summary & ✅ Notes

📌 Key Takeaways:  
- Moving from full Ubuntu VMs to Docker on Windows made the lab setup faster and more flexible  
- Containers are lightweight compared to full VMs and allow quick reset/rebuild of the SOC environment  
- Creating logs on Windows endpoints and ingesting into Docker Splunk simulates real-world endpoint → SOC workflows  
- Hands-on GUI exploration, dashboard navigation, and indexing are essential for understanding Splunk operations  
- Troubleshooting leftover containers, permissions, and file paths is valuable experience  

---

## 📌 Notes
- Splunk **data path:** `/opt/splunk/var/lib/splunk/`  
- Splunk **service commands:** `/opt/splunk/bin/splunk [start|stop|restart|status]`  
- Docker ports mapped to host: **8000 (web)**, **9997 (forwarder)**  
- Admin password should remain private; do not include in documentation  
- If issues arise with ingestion or container, check leftover containers and file paths  
