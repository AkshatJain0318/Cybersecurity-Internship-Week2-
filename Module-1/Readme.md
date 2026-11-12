# 🔍 Footprinting & Reconnaissance with Multiple Kali Linux Tools

![Kali Linux](https://img.shields.io/badge/OS-Kali%20Linux-557C94?style=for-the-badge&logo=kalilinux&logoColor=white)
![Category](https://img.shields.io/badge/Domain-Cybersecurity%20%26%20Ethical%20Hacking-critical?style=for-the-badge)
![Status](https://img.shields.io/badge/Module-Week%202%20%7C%20Project%201-success?style=for-the-badge)

## 📌 Project Overview
This repository documents **Phase 1: Footprinting & Reconnaissance** performed as part of the **Networkwalks Cybersecurity Internship (Week 2 – Project Module 1)**. 

The objective of this lab is to gather passive and active intelligence on an authorized target domain (`networkwalks.com`) using six built-in Kali Linux reconnaissance utilities—mapping its domain ownership, IP infrastructure, web technology stack, HTTP headers, Web Application Firewall (WAF), and DNS records without launching intrusive attacks.

* **Author:** Akshat Jain
* **Program / Batch:** `B084C` — Networkwalks Cybersecurity Internship
* **Authorization Ref:** `NW-LOA-B084C-017`
* **Target Domain:** `networkwalks.com`

---

## 🛠️ Tools & Commands Executed

| Task | Tool | Command Executed | Purpose |
| :--- | :--- | :--- | :--- |
| **Task 1** | `whois` | `whois networkwalks.com` | Extract domain registrar, creation/expiry dates, and name servers |
| **Task 2** | `whatweb` | `whatweb networkwalks.com` | Fingerprint CMS, web server, frameworks, plugins, and server IP |
| **Task 3** | `nslookup` | `nslookup networkwalks.com` | Resolve the target domain name to its public IPv4 address |
| **Task 4** | `curl` | `curl -I https://networkwalks.com` | Inspect HTTP response headers, server banners, cookies, and API endpoints |
| **Task 5** | `wafw00f` | `wafw00f networkwalks.com` | Detect the presence and vendor of any Web Application Firewall (WAF) |
| **Task 6** | `dnsrecon` | `dnsrecon -d networkwalks.com` | Enumerate SOA, NS, MX, TXT (SPF), and cPanel SRV DNS records |

---

## 📊 Key Reconnaissance Findings

* **Domain & Hosting:** Registered via **GoDaddy.com, LLC** and hosted on **HostGator** name servers (`ns6135.hostgator.com`, `ns6136.hostgator.com`).
* **IP Resolution:** Resolves to **`192.232.216.135`** (United States).
* **Web Technology Stack:** Powered by **Apache** web server running **WordPress CMS**, **Bootstrap**, and **jQuery**, with an exposed WordPress REST API endpoint (`/wp-json/`).
* **Firewall Protection:** Protected by **ModSecurity (SpiderLabs)** Web Application Firewall.
* **DNS & Mail Architecture:** Mail handled via `mail.networkwalks.com` (`192.232.216.135`) with SPF records configured (`include:websitewelcome.com`) and cPanel autodiscovery `SRV` records active.

---

## 📂 Repository Structure

```text
├── outputs/                  # Raw terminal outputs (.txt) for all 6 tasks
│   ├── task1_whois.txt
│   ├── task2_whatweb.txt
│   ├── task3_nslookup.txt
│   ├── task4_curl.txt
│   ├── task5_wafw00f.txt
│   └── task6_dnsrecon.txt
├── screenshots/              # Terminal execution proof screenshots (.png)
├── Report/                   # Final compiled PDF project report
└── README.md                 # Project documentation
