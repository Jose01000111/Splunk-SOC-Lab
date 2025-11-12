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
- Troubleshoot **disk space issues** and learn operational problem-solving in Splunk  

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
| [🚀 Phase II — Splunk Installation 🧩](https://github.com/Jose01000111/Phase-II-Splunk-Installation.git) |
| [🚀 Phase III — GUI Exploration & Disk Space Troubleshooting 🛠️](https://github.com/Jose01000111/Phase-III-GUI-Exploration-Disk-Space-Troubleshooting-Splunk-Server-Issue-.git) | 
| [🚀 Phase III.V — Rebuild Endpoint/Server Connection 🔄](https://github.com/Jose01000111/Phase-III.V-Rebuild-Endpoint-Connection.git) |
| [🚀 Phase IV — GUI Discovery 🔑](https://github.com/Jose01000111/Phase-IV-Splunk-GUI-Discovery.git) |

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
  - Observed that the server only had 4GB free, below the 5GB minimum required  
  - Checked server disk usage and identified temporary files and large logs as potential space sources  
  - Removed temporary dispatch files 🧹, cleared system caches 🗑️, and moved large logs to a backup folder 📂  
  - Verified free space after cleanup but indexing did not fully resume  
  - Determined that the underlying VM disk size was insufficient and needed to be resized for proper functionality 💻  

- **Phase IV — GUI Discovery 🔑**  
  - Explored the Splunk dashboard, default panels, and menus 🖥️  
  - Reviewed default indexes `_internal`, `_audit`, `_introspection` 📂  
  - Navigated menus including **Search & Reporting**, **Settings**, and **Apps** 🧭  

---

## ⏩ Summary & ✅ Notes
📌 Key Takeaways from Phase III & IV:  
- Disk space issues can block indexing and GUI exploration; cleanup helps, but VM resizing is sometimes required 💻  
- Hands-on GUI exploration is a fast way to become comfortable with Splunk’s interface 🖥️  
- Documenting dashboards, indexes, menus, and alerts creates a helpful glossary for future labs 📂  
- Even “easy” labs help build intuitive understanding of Splunk workflows ⚡  

---

## 📌 Notes
- Splunk **data path:** `/opt/splunk/var/lib/splunk/`  
- Splunk **service commands:** `/opt/splunk/bin/splunk [start|stop|restart|status]`  
- Firewall ports must be open: **8000 (web)** and **8089 (management)**  
- If admin password is forgotten or no users exist, follow the troubleshooting steps in Phase II  



