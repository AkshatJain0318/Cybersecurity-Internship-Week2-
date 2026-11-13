# 🌐 Network Scanning & Host Discovery with Zenmap (Nmap GUI)

![Tool](https://img.shields.io/badge/Tool-Nmap%207.993%20%2F%20Zenmap%20GUI-2E8B57?style=for-the-badge&logo=gnubash&logoColor=white)
![OS](https://img.shields.io/badge/Platform-Windows%20PC-0078D6?style=for-the-badge&logo=windows&logoColor=white)
![Module](https://img.shields.io/badge/Module-Week%202%20%7C%20Project%205-success?style=for-the-badge)

## 📌 Project Overview
This module documents **Phase 2: Active Network Scanning & Host Discovery** performed using **Zenmap** (the official graphical front-end for Nmap) as part of the **Networkwalks Cybersecurity Internship (Week 2 – Project Module 5)**.

The objective of this lab is to identify the local host's network configuration on a Windows system, perform an ICMP/ARP ping sweep across the local area network (`10.57.180.0/24`), enumerate active hosts along with their IP and MAC addresses, and export a visual network topology map.

* **Author:** Akshat Jain
* **Program / Batch:** `B084C` — Networkwalks Cybersecurity Internship
* **Authorization Ref:** `NW-LOA-B084C-023`
* **Target Network:** Local LAN Subnet (`10.57.180.0/24`)
* **Tools Used:** Zenmap (`Nmap v7.993`), Npcap, Windows Command Prompt (`ipconfig`)

---

## 🛠️ Lab Tasks & Execution Summary

| Task | Objective | Command / Method | Key Result |
| :--- | :--- | :--- | :--- |
| **Task 1** | **Zenmap Installation** | Installed official Nmap/Zenmap Windows binary (`v7.993`) with Npcap driver | GUI scanner configured on Windows host |
| **Task 2** | **Local IP & Subnet Discovery** | `ipconfig` (Windows CMD) | IPv4: `10.57.180.168` \| Subnet: `10.57.180.0/24` |
| **Task 3** | **Live Host Discovery Scan** | `nmap -sn 10.57.180.0/24` (Ping Scan profile) | Scanned 256 IP addresses in `3.54 seconds` |
| **Task 4** | **Active Host Count** | Analyzed `Nmap Output` summary | **3 live hosts** detected on the subnet |
| **Task 5** | **Live IP Enumeration** | Extracted active endpoints from host list | `10.57.180.21`, `10.57.180.174`, `10.57.180.168` |
| **Task 6** | **MAC & Vendor Identification** | ARP/Nmap output + `ipconfig /all` | Mapped hardware MACs and OUI vendors |
| **Task 7** | **Network Topology Export** | `Topology` tab → Legend enabled → `Save Graphic` | Exported visual network map in `.pdf` format |

---

## 📊 Discovered Hosts & Network Inventory

* **Local Interface:** Wireless LAN adapter Wi-Fi
* **Subnet Mask:** `255.255.255.0` (`/24`)
* **Default Gateway:** `10.57.180.174`

| Host # | IPv4 Address | MAC Address | Vendor / Role | Latency |
| :--- | :--- | :--- | :--- | :--- |
| **1** | `10.57.180.21` | `6C:E8:C6:E5:F4:22` | Earda Technologies (Client Device) | `0.026s` |
| **2** | `10.57.180.174` | `4A:0F:0F:CD:EF:D8` | Default Gateway / Hotspot Router | `0.022s` |
| **3** | `10.57.180.168` | *Local NIC (`ipconfig /all`)* | Local Scanning Host (Windows PC) | `localhost` |

---

## 🚀 Quick Reproduction (Windows CMD & Zenmap)

1. **Identify local network configuration in Command Prompt:**
   ```cmd
   ipconfig
   ipconfig /all
