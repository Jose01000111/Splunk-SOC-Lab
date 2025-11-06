# ⚡ Splunk Security Operations Lab 🧠

<img width="400" height="186" alt="rmIiKm1" src="https://github.com/user-attachments/assets/ff0bd4cc-3f16-4162-bda8-becb0283bbe3" />

Welcome to my Home SOC Lab project!  
This repository documents the creation of a **Splunk Enterprise Security (ES)** lab — simulating a mini **Security Operations Center (SOC)** using Ubuntu virtual machines.  
The lab is designed for hands-on learning in **log ingestion, alerting, and monitoring workflows**, and serves as a **practical journal** of my lab progress.

---

## 🎯 Objectives
- Build a **home SIEM environment** with Splunk Enterprise  
- Configure **server and endpoint VMs** for log ingestion and analysis  
- Practice **SOC workflows**, including alert triage and data visualization  
- Document the process for **continuous learning and reference**  
- Maintain a **step-by-step journal** of lab activities for GitHub  

---

## 🏗️ Lab Environment
| Component      | Platform      | Function |
|----------------|--------------|---------|
| Splunk Server  | Ubuntu 22.04 | Hosts Splunk Enterprise & Enterprise Security, receives logs from endpoints |
| Endpoint VM    | Ubuntu 22.04 | Generates logs and forwards them to Splunk Server for analysis |
| Network        | Virtual Network (Host-only / NAT) | Ensures connectivity between server and endpoint for log forwarding |

---

# 🗂️ Lab Directory

| Phase | 
|-------|
| [🚀 Phase I — Environment Setup 🧱](https://github.com/Jose01000111/SplunkES-Phase-1.git) |
|[🚀 Phase II — Splunk Installation](https://github.com/Jose01000111/Phase-II-Splunk-Installation.git)|

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

---

## 📌 Notes
- Splunk **data path:** `/opt/splunk/var/lib/splunk/`  
- Splunk **service commands:** `/opt/splunk/bin/splunk [start|stop|restart|status]`  
- Firewall ports must be open: **8000 (web)** and **8089 (management)**  
- If admin password is forgotten or no users exist, follow the troubleshooting steps in Phase II  

---


