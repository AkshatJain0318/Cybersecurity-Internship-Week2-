# 🛡️ Cybersecurity & Ethical Hacking Internship Portfolio (Week 2)

![Environment](https://img.shields.io/badge/Environment-Kali%20Linux%20%26%20Windows-557C94?style=for-the-badge&logo=kalilinux&logoColor=white)
![Program](https://img.shields.io/badge/Internship-Networkwalks%20Cybersecurity-blue?style=for-the-badge)
![Batch](https://img.shields.io/badge/Batch-B084C-informational?style=for-the-badge)
![Status](https://img.shields.io/badge/Week%202%20Modules-Completed%20(PM1%20%7C%20PM2%20%7C%20PM5)-success?style=for-the-badge)

## 📌 Repository Overview
This repository serves as a comprehensive portfolio of practical reconnaissance, OSINT, and network scanning labs completed during **Week 2** of the **Networkwalks Cybersecurity & Ethical Hacking Internship**.

The labs demonstrate an end-to-end pre-exploitation workflow—moving from passive and active external footprinting against an authorized domain (`networkwalks.com`), to Google Hacking Database (GHDB) OSINT enumeration, and finally to internal local network discovery and topology mapping using Zenmap.

* **Intern Name:** Akshat Jain
* **Program / Batch:** `B084C` — Networkwalks Cybersecurity Internship
* **Authorization Ref:** `NW-LOA-B084C-023`
* **Assessment Phases Covered:** Phase 1 (Footprinting & Reconnaissance) & Phase 2 (Network Scanning & Host Discovery)

---

## 🗂️ Completed Modules & Reports Index

| Module ID | Module Title | Environment & Tools | Folder & Documentation |
| :--- | :--- | :--- | :--- |
| **W2-PM1** | **Footprinting & Reconnaissance with Multiple Kali Tools** | Kali Linux (`whois`, `whatweb`, `nslookup`, `curl`, `wafw00f`, `dnsrecon`) | [📂 Open Folder](./Module-1-Footprinting/) • [📄 Read Docs](./Module-1-Footprinting/README.md) |
| **W2-PM2** | **Footprinting & Reconnaissance with GHDB** | Web OSINT (Exploit-DB GHDB, Advanced Google Dorks) | [📂 Open Folder](./Module-2-GHDB-Footprinting/) • [📄 Read Docs](./Module-2-GHDB-Footprinting/README.md) |
| **W2-PM5** | **Network Scanning & Host Discovery with Zenmap** | Windows PC (`Zenmap / Nmap v7.993`, `Npcap`, `ipconfig`) | [📂 Open Folder](./Module-5-Zenmap-Scanning/) • [📄 Read Docs](./Module-5-Zenmap-Scanning/README.md) |
| **W2-PM-FINAL** | **Combined Penetration Testing Report (Phases 1 & 2)** | Consolidated Risk Matrix, Recommendations & Evidences | [📂 Open Folder](./Final-Report/) • [📑 Combined PDF](./Final-Report/W2_PM_FINAL_Report.pdf) |

---

## 🔍 Executive Summary of Technical Findings

### 1. External Domain Footprinting (`networkwalks.com` — W2-PM1)
* **Domain & Hosting Infrastructure:** Registered via **GoDaddy.com, LLC** with transfer/delete locks enabled; authoritative DNS hosted on **HostGator** (`ns6135.hostgator.com`, `ns6136.hostgator.com`).
* **IP & Web Stack:** Resolves to **`192.232.216.135`**. Fingerprinted **Apache** HTTP server running **WordPress CMS**, **Bootstrap**, and **jQuery**, with an exposed `/wp-json/` REST API endpoint.
* **Perimeter Defense & DNS:** Protected by **ModSecurity (SpiderLabs) WAF**. DNS enumeration revealed `mail.networkwalks.com`, configured SPF policies, and cPanel `SRV` autodiscovery records.

### 2. Passive OSINT via Google Dorking (`GHDB` — W2-PM2)
* **Exposed IoT/Camera Interfaces:** Crafted and verified 10x GHDB queries (`intitle:"webcamXP" inurl:8080`, `inurl:view/view.shtml`, etc.) identifying publicly indexed camera web panels.
* **Open Directory Enumeration:** Verified 10x misconfigured web directories (`intitle:index.of "parent directory" mathematics pdf`) exposing downloadable academic PDF resources.

### 3. Internal LAN Scanning & Topology (`10.57.180.0/24` — W2-PM5)
* **Subnet Discovery:** Identified local Windows interface (`10.57.180.168`, mask `255.255.255.0`) and executed an ICMP/ARP ping sweep (`nmap -sn 10.57.180.0/24`).
* **Active Hosts Mapped (3 Hosts Up in `3.54s`):**
  * `10.57.180.21` — MAC: `6C:E8:C6:E5:F4:22` (*Earda Technologies*)
  * `10.57.180.174` — MAC: `4A:0F:0F:CD:EF:D8` (*Default Gateway / Router*)
  * `10.57.180.168` — *Local Scanning Workstation (Windows PC)*
* **Topology Mapping:** Visualized node relationships in Zenmap Topology Viewer and exported the network diagram to PDF.

---

## 📂 Repository Architecture

```text
Networkwalks-Cybersecurity-Internship/
├── README.md                             # Main Portfolio Overview & Module Index (This File)
│
├── Final-Report/
│   └── W2_PM_FINAL_Report.pdf            # Combined Penetration Testing Report (PM1 + PM2 + PM5)
│
├── Module-1-Footprinting/
│   ├── Report/                           # Module 1 PDF Assessment Report
│   ├── outputs/                          # Raw terminal outputs (.txt)
│   ├── screenshots/                      # Kali Linux terminal evidence
│   └── README.md                         # Module 1 Documentation
│
├── Module-2-GHDB-Footprinting/
│   ├── Report/                           # Module 2 PDF Assessment Report
│   ├── findings/                         # Verified Google Dork tables
│   ├── screenshots/                      # Search & verification captures
│   └── README.md                         # Module 2 Documentation
│
└── Module-5-Zenmap-Scanning/
    ├── Report/                           # Module 5 PDF Assessment Report
    ├── topology/                         # Exported Zenmap network topology (.pdf)
    ├── screenshots/                      # ipconfig & Zenmap Ping Scan captures
    └── README.md                         # Module 5 Documentation
