# 🛡️ Wazuh Deployment & Detection Lab Guide

This repository provides a complete deployment guide for Wazuh (SIEM), including configuration files, certificate setup, and lab scenarios to test various detection capabilities.

---

## 📦 Components Overview

Wazuh consists of the following core components:

| Component         | Role                                                                 |
|------------------|----------------------------------------------------------------------|
| **Wazuh Indexer**   | Stores and indexes logs, powers search and dashboards.              |
| **Wazuh Server**    | Parses logs, detects threats, sends alerts to Indexer.             |
| **Wazuh Dashboard** | Web interface for log visualization, agent management, SOC view.   |
| **Wazuh Agents**    | Installed on endpoints to collect logs and monitor changes.         |

---

## 🏗️ System Requirements

- **CPU:** 4 cores
- **RAM:** 8 GB minimum
- **Disk:** 50 GB SSD (for 25 agents with 90-day retention)
- **Supported OS:** Ubuntu 16.04–22.04, CentOS 7/8, RHEL 7–9, Amazon Linux 2

---

## 🧪 Lab Scenarios

| Scenario                        | Tools Used                             | Description                                                                 |
|--------------------------------|----------------------------------------|-----------------------------------------------------------------------------|
| **PHP Injection**              | Wazuh + DVWA                           | Detect SQL-like injections in web input                                     |
| **Brute Force Attack**         | Wazuh + DVWA + Hydra                   | Monitor repeated login failures via SSH/RDP                                 |
| **DDoS Attack**                | Wazuh + DVWA + MHDDOS                  | Analyze log patterns during resource exhaustion attacks                     |
| **File Integrity Monitoring**  | Wazuh + FIM                            | Track file creation, modification, and deletion in sensitive directories    |
| **Malware Detection (YARA)**   | Wazuh + YARA                           | Detect known malware samples using YARA signature rules                     |

---

## 🔐 SSL Certificate Setup

Use `wazuh-certs-tool.sh` and `config.yml` to generate and deploy certificates for secure communication between:
- Indexer ↔ Server
- Server ↔ Dashboard
- Filebeat ↔ Indexer

---

## 📂 Folder Structure

```
.
├── 01_intro/                       # Requirements and architecture
├── 02_indexer/                    # Indexer installation & SSL config
├── 03_server/                     # Wazuh Manager & Filebeat setup
├── 04_dashboard/                  # Dashboard deployment & config
├── 05_agents/                     # Wazuh Agent installation
├── 06_poc/
│   ├── file_integrity_monitoring/ # FIM proof of concept
│   ├── brute_force_detection/     # Brute-force detection lab
│   ├── sql_injection_detection/   # SQLi detection lab
│   └── malware_yara/              # YARA malware detection lab
└── 07_troubleshooting/           # Common errors and fixes
```

---

## 📊 Dashboards & Monitoring

- Real-time alerts
- Custom visualizations
- SOC central view
- Agent grouping & health status
- Rule & decoder inspection

---

## 📎 References

- [Official Wazuh Documentation](https://documentation.wazuh.com/)
- [YARA Rules - Valhalla](https://valhalla.nextron-systems.com/)
- [Hydra GitHub](https://github.com/vanhauser-thc/thc-hydra)
- [OWASP DVWA](http://www.dvwa.co.uk/)

---

## ⚠️ Disclaimer

The malware samples and attack simulations are strictly for educational and lab purposes. Use in isolated environments only.

---

## 🧠 Maintainer

Created by AkimSams  
Pull requests and forks are welcome!
