# NETWORKWALKS-ZAIN-UL-ABIDIN-B083-WK2-PM3-FOOTPRINTING-MALTEGO

**Footprinting with Maltego**

---

## 📌 Project Overview

This project focuses on installing **Maltego** (an OSINT and graphical link-analysis tool) and using it to footprint an organization by discovering email addresses related to its domain.

Maltego turns scattered public information into a visual graph of connected entities, making it a powerful tool for reconnaissance and open-source intelligence (OSINT) gathering.

---

## 🎯 Objectives

- Download and install Maltego on a Windows computer.
- Create a free Maltego ID and complete initial configuration.
- Add a Domain entity and set it to the target organization's domain (`networkwalks.com`).
- Run email-related transforms to discover all email addresses associated with the domain.
- Understand how this information can be leveraged in a real attack.

---

## 🛡️ Ethical Use

This lab is intended for **educational and authorized security testing only**.

The target domain (`networkwalks.com`) was used with due permission as part of an authorized training exercise. Only publicly available OSINT data was gathered — no systems were accessed or attacked.

---

# 🧠 Background

Maltego is an OSINT (Open-Source Intelligence) and graphical link-analysis tool used by security researchers, investigators, and pentesters to map relationships between people, domains, organizations, and infrastructure.

Instead of manually searching multiple sources, Maltego uses "Transforms" — automated queries that pull data from search engines, WHOIS records, DNS, and other public sources — and displays the results as a connected graph. This makes it easy to visually trace how a domain, person, or organization is connected to other public information, such as email addresses, subdomains, and social media profiles.

---

# 🪜 Tasks & Solutions

## Task 1 — Install Maltego on Kali Linux

**Objective:** Download and install Maltego on a Kali Linux computer.

**Solution Steps:**
1. Maltego comes pre-installed on Kali Linux by default. Check by searching for it in the Applications menu, or run:
   ```bash
   which maltego
   ```
2. If it is not installed, download the Kali Linux (.deb) version from `https://maltego.com/downloads` (select Linux → .deb package).
3. Install the downloaded package:
   ```bash
   sudo dpkg -i maltego-*.deb
   sudo apt-get install -f
   ```
4. Launch Maltego from the Applications menu, or from the terminal:
   ```bash
   maltego
   ```
5. Complete the initial configuration wizard:
   - Choose **Maltego ID** as the activation option (free tier).
   - Select **Online Activation**.
   - Accept the End User License Agreement.
6. Create a free Maltego ID by registering with an email address, first name, and last name.
7. Complete authentication in the browser — Maltego will redirect back to the application once login is confirmed.
8. On the final setup screens, keep the default settings:
   - Web Browser: **Default System Browser**
   - Privacy Mode: **Normal**
   - Install Transforms from: **Utilities**
9. Click **Finish** — Maltego is now ready to use.

### Screenshot
![Maltego Installation](screenshots/task1-maltego-install.png)

---

## Task 2 — Find Email Addresses Related to networkwalks.com

**Objective:** Find all email addresses related to the target organization domain `networkwalks.com` (with due permission).

**Solution Steps:**
1. In the Entity Palette (left panel), search for **"Domain"**.
2. Drag the **Domain** entity onto the main graph area.
3. Double-click the entity and change its name to `networkwalks.com`.
4. Right-click the entity, and in the **Run Transforms** search box, type `email` to filter for email-related transforms.
5. Select and run a transform such as **"To Email Addresses [Search Engine]"**.
6. Maltego queries public sources and returns any email addresses associated with the domain, displayed as connected nodes on the graph (e.g. `info@networkwalks.com`).

### Screenshot
![Email Harvesting Results](screenshots/task2-maltego-emails.png)

**How attackers use this:** Harvested email addresses give attackers a starting point for phishing campaigns, credential-stuffing attempts, and social engineering. Combined with technology fingerprinting (from earlier modules), an attacker can craft targeted attacks — for example, running WordPress-specific attacks against a known WordPress site while phishing the discovered email addresses.

---

# 💡 Extra References & Tips

- Maltego was created by **Paterva** in 2008, in Pretoria, South Africa.
- Maltego has powered over **one million investigations** worldwide since 2008.
- Maltego is used by major organizations including the **FBI and INTERPOL**, as well as half of the companies in the DOW 30.
- Maltego comes in multiple editions — the **Community Edition (CE)** is free with limited features, while paid plans unlock more results, data, and commercial use.
- Maltego results and graphs can be exported to **XLSX, CSV, images, and PDF** for easy sharing and reporting.
- Other useful transforms to explore: DNS from Domain, Domain owner detail, Person from Domain, Search Web, To Details [Whois].

---

# 💡 Why This Matters

Reconnaissance tools like Maltego let an investigator (or an attacker) turn a single piece of information — like a domain name — into a full map of an organization's public footprint. Because everything comes from publicly available sources, this kind of footprinting is quiet and hard to detect, yet it can expose exactly the information needed to plan a targeted attack.

---

# 💡 What I Learned

### 1. OSINT Tooling
I learned how Maltego automates open-source intelligence gathering using Transforms, instead of manually searching each source individually.

### 2. Entity-Based Investigation
I learned how to represent a target (a domain) as an entity on a graph and expand it using relevant transforms to reveal connected information.

### 3. Email Harvesting
I learned how a single domain entity can be used to harvest associated email addresses through search-engine-based transforms.

### 4. Visual Link Analysis
I learned how graphing relationships between entities makes it easier to understand an organization's public footprint compared to reading raw text output.

### 5. Real-World Impact
I learned how harvested email addresses and technology fingerprints combine to give attackers a starting point for phishing and targeted exploitation.

---

# 🔐 Security & Ethical Use

This lab is created for learning and cybersecurity practice.

All testing was performed on the designated lab target (`networkwalks.com`) with due permission, as part of an authorized training exercise.

---

# 🔗 Tools & Resources

- **Maltego:** https://maltego.com
- **Maltego Academy / Documentation:** available via the Maltego website under Resources

---

# 👤 Author

**Zain ul Abidin**

**Cyber Security Student B083**

---

## 📌 Project Information

**Program Name:** Cybersecurity at Networkwalks
**Week:** 02
**Project Module:** PM3 — Footprinting with Maltego
**Author:** Zain ul Abidin
**B-Number:** B083
**Repository:** GitHub
