# 🔎 Footprinting & Reconnaissance with Google Hacking Database (GHDB)

![Technique](https://img.shields.io/badge/Technique-Passive%20OSINT%20%26%20Google%20Dorking-blue?style=for-the-badge&logo=google&logoColor=white)
![Platform](https://img.shields.io/badge/Database-Exploit--DB%20GHDB-orange?style=for-the-badge)
![Module](https://img.shields.io/badge/Module-Week%202%20%7C%20Project%202-success?style=for-the-badge)

## 📌 Project Overview
This module documents **Phase 1: Passive Footprinting & OSINT Reconnaissance** using the **Google Hacking Database (GHDB)** as part of the **Networkwalks Cybersecurity Internship (Week 2 – Project Module 2)**.

The objective of this lab is to leverage advanced Google search operators ("Google Dorks") curated on **Exploit-DB** to passively identify publicly exposed IoT/CCTV interfaces and open directory listings indexed by search engines—without sending a single direct packet to target servers.

* **Author:** Akshat Jain
* **Program / Batch:** `B084C` — Networkwalks Cybersecurity Internship
* **Authorization Ref:** `NW-LOA-B084C-023`
* **Primary Sources:** Google Search, Exploit-DB GHDB (`exploit-db.com/google-hacking-database`)

---

## 🛠️ Lab Tasks & Methodology

| Task | Objective | Search Technique & Operators | Verification Criteria |
| :--- | :--- | :--- | :--- |
| **Task 1** | **Exposed Security Camera Discovery** | Queried GHDB (`Various Online Devices`) & custom dorks (`intitle:`, `inurl:`, `allintitle:`) to locate publicly accessible IP camera feeds | Verified 10x live accessible web camera panels, documented exact dorks, and checked for default/unauthenticated access |
| **Task 2** | **Open Directory & PDF Enumeration** | Used directory-indexing dorks (`intitle:index.of`, `"parent directory"`, `filetype:pdf`) to locate misconfigured web directories | Verified 10x open directory listings hosting downloadable mathematics PDF ebooks |

---

## 🎯 Key Google Dorks & Operators Used

### 1. Exposed IP Camera / Webcam Dorks (Task 1)
```text
intitle:"webcamXP" inurl:8080
intitle:"webcamXP 5"
intitle:"Live View / - AXIS" | inurl:view/view.shtml
allintitle:"Network Camera Network Camera"
intitle:"EvoCam" inurl:"webcam.html"
inurl:axis-cgi/jpg
inurl:"MultiCameraFrame?Mode=Motion"
"my webcamXP server!"
