# ⚡ Splunk Security Operations Lab 🧠

<img width="400" height="186" alt="rmIiKm1" src="https://github.com/user-attachments/assets/ff0bd4cc-3f16-4162-bda8-becb0283bbe3" />

Welcome to my Home SOC Lab project!  
This repository documents the creation of a **Splunk Enterprise Security (ES)** lab — simulating a mini **Security Operations Center (SOC)**.  
The lab originally started with Ubuntu virtual machines, but starting Phase 6 we transitioned to using **Docker on Windows 11 Pro** for faster, more flexible, and resettable lab setups.  
The lab is designed for hands-on learning in **log ingestion, alerting, monitoring workflows**, and serves as a **practical journal** of my progress, including persistent Windows Firewall logs and SPL exercises.

---

## 🎯 Objectives
- Build a **home SIEM environment** with Splunk Enterprise  
- Configure **server and endpoint VMs or Docker container** for log ingestion  
- Practice **SOC workflows**, including alert triage, data visualization, and SPL analysis  
- Ingest **Windows Firewall logs** for realistic endpoint monitoring  
- Document the process for **continuous learning and reference**  
- Maintain a **step-by-step GitHub journal** of lab activities  
- Troubleshoot **permissions, disk space, and container issues** in Splunk  

---

## 🏗️ Lab Environment
| Component      | Platform / Setup                          | Function / Context |
|----------------|------------------------------------------|------------------|
| Splunk Server  | Ubuntu 22.04 VM (original) <br> Docker container on Windows 11 Pro x64 | Hosts Splunk Enterprise & Enterprise Security. Docker allows rapid deployment, persistent data volumes, and easier reset for experiments. |
| Endpoint       | Ubuntu VM / Windows Host                  | Generates logs for ingestion. Windows endpoints now produce Firewall logs and test traffic that are ingested into Docker Splunk, simulating real-world endpoint → SOC workflow. |
| Network        | Virtual Network / Host-only / NAT / Docker port mapping | Ensures connectivity between endpoint, host, and container. Ports 8000 (Web UI), 8089 (management), and 9997 (Forwarder) are mapped from container to Windows host. |
| Tools / Tech   | Docker Desktop, WSL2, PowerShell, Splunk Enterprise container image | Docker + WSL2 provides a lightweight SOC lab setup. PowerShell used to generate firewall logs. Splunk Web used for ingestion, SPL queries, and dashboards. |
| Security Tools | **Phase VII — Sysmon & Suricata** on Windows 11 Host | Captures Windows event logs and network traffic. Logs exported/imported into Docker Splunk for analysis. Persistent firewall logging added in Phase 9 for real-time ALLOW/DROP events. |

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
| [🚀 Phase VIII — Splunk Log Ingestion, SPL Analysis, and Dashboard Creation 📊](https://github.com/Jose01000111/-Phase-8-Splunk-Log-Ingestion-SPL-Analysis-and-Dashboard-Creation.git) |
| [🚀 Phase IX — Persistent Windows Firewall Logs & Field Extraction 🔥](https://github.com/Jose01000111/Splunk-SOC-Lab-with-Persistent-Windows-Firewall-Logs.git) |

---

## 📝 Lab Progress Overview

- **Phase I — Environment Setup 🧱**  
  - Updated and cleaned Ubuntu VMs  
  - Created project folders for lab files and logs  
  - Gathered system info (OS, IPs, hostname)  
  - Verified network connectivity between VMs  

- **Phase II — Splunk Installation 🧩**  
  - Installed Splunk Enterprise on server VM  
  - Configured firewall and opened ports 8000, 8089  
  - Created admin credentials and verified web access  
  - Verified Splunk service and indexes  

- **Phase III — GUI Exploration & Disk Space Troubleshooting 🛠️**  
  - Explored GUI but blocked due to low disk space  
  - Cleaned temporary files, caches, large logs  
  - Verified free space; VM disk size required resizing  

- **Phase IV — GUI Discovery 🔑**  
  - Explored dashboards, default panels, and menus  
  - Reviewed default indexes `_internal`, `_audit`, `_introspection`  
  - Navigated **Search & Reporting**, **Settings**, and **Apps**  

- **Phase VI — Docker-Based Splunk SOC Lab 🐳**  
  - Pulled Splunk Enterprise container image on Windows 11 Pro x64  
  - Mapped ports 8000 (Web UI) and 9997 (Forwarder)  
  - Created sample logs on Windows host and ingested into Docker Splunk  
  - Verified log ingestion and container persistence  

- **Phase VII — Windows 11 + Sysmon + Suricata ⚡**  
  - Captured Windows events via Sysmon and network traffic via Suricata  
  - Ingested logs into Docker Splunk  
  - Practiced container isolation and log export/import  

- **Phase VIII — Splunk Log Ingestion, SPL Analysis, and Dashboard Creation 📊**  
  - Copied `sample2.log` into Docker container  
  - Uploaded log into Splunk, set source type `syslog`, index `os_logs`  
  - Ran SPL queries, filtered events, counted by host, created time charts  
  - Built dashboards with Total Logs, Top Hosts, Log Volume  

- **Phase IX — Persistent Windows Firewall Logs & Field Extraction 🔥**  
  - Configured Windows Firewall logging using PowerShell (`pfirewall.log`)  
  - Copied log to accessible folder for Splunk ingestion  
  - Uploaded into Docker Splunk with sourcetype `windows_firewall`, index `os_logs`  
  - Validated ingestion with SPL searches, confirmed ALLOW/DROP actions  
  - Practiced auto and manual field extraction for structured analysis  
  - Ensured data persistence across container restarts for SOC exercises  

---

## ⏩ Summary & ✅ Notes

📌 Key Takeaways:  
- Docker on Windows 11 provides a flexible SOC lab setup with persistent data  
- Windows Firewall logging adds realistic endpoint events for SOC workflow  
- Containers preserve logs and settings for repeatable lab experiments  
- SPL queries and field extraction are critical for analyzing structured logs  
- Hands-on experience with log ingestion, dashboarding, and troubleshooting builds practical SOC skills  

---

## 📌 Notes
- Splunk **data path:** `/opt/splunk/var/lib/splunk/`  
- Splunk **service commands:** `/opt/splunk/bin/splunk [start|stop|restart|status]`  
- Docker ports mapped to host: **8000 (web)**, **8089 (management)**, **9997 (forwarder)**  
- Admin password should remain private  
- Check leftover containers, file permissions, and paths if ingestion issues occur  
- Firewall logs: `C:\Windows\System32\LogFiles\Firewall\pfirewall.log`  

