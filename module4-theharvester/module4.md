# NETWORKWALKS-ZAIN-UL-ABIDIN-B083-WK2-PM4-FOOTPRINTING-THEHARVESTER

**Footprinting & Reconnaissance Attacks with theHarvester**

---

## 📌 Project Overview

This project focuses on using **theHarvester**, a Python-based OSINT tool pre-installed in Kali Linux, to gather email addresses and sub-domains related to a target organization (`microsoft.com`) using different public data sources.

---

## 🎯 Objectives

- Understand what theHarvester is and how it gathers OSINT data.
- Find email IDs & sub-domains for `microsoft.com` using the **Baidu** source, limited to 1000 results.
- Find email IDs & sub-domains for `microsoft.com` using **all sources**, limited to 50 results.
- Compare results across different sources.
- Document every output with screenshots and text files.

---

## 🛡️ Ethical Use

This lab is intended for **educational and authorized security testing only**.

`microsoft.com` was used as a publicly documented lab example target within this training course. Only publicly available OSINT data was gathered — no systems were accessed or attacked.

---

# 🧠 Background

theHarvester is a footprinting tool used for gathering information such as emails, sub-domains, hosts, employee names, open ports, and banners from different public sources — including search engines, PGP key servers, and the SHODAN computer database. It is developed in Python.

theHarvester comes pre-installed in Kali Linux and can be started directly from the terminal using simple commands.

In this module, the goal is to learn how to gather the list of email IDs related to a target organization using theHarvester, comparing results between a single source and multiple sources combined.

---

# 🪜 Tasks & Solutions

## Task 1 — Harvest with Baidu (limit 1000)

**Objective:** Find email IDs & sub-domains related to the target organization `microsoft.com` using theHarvester in Kali Linux with the **Baidu** source. Set the limit of number of results to 1000.

**Solution Steps:**
1. Open **theHarvester** from the Kali Linux applications menu (or search for it).
2. Review the usage instructions and guidelines shown when the tool starts — this lists all supported sources (baidu, bevigil, bitbucket, brave, censys, crtsh, dnsdumpster, duckduckgo, hunter, rapiddns, virustotal, waybackarchive, yahoo, and many more).
3. In the terminal, run the following command:
   ```bash
   theHarvester -d microsoft.com -l 1000 -b baidu
   ```
   - `-d` → target domain
   - `-l` → limit the number of search results
   - `-b` → data source to use
4. theHarvester queries Baidu and displays any discovered IPs, emails, and hosts related to the domain.

### Screenshot
![theHarvester Baidu Results](screenshots/task1-harvester-baidu.png)
### Screenshot
![theHarvester Baidu Results](screenshots/task1-harvester2-baidu.png)

**Note:** Results may vary from what is shown in the original lab, since theHarvester relies on external sources whose data and algorithms change over time — the method stays the same even if the exact output differs.

**How attackers use this:** Each harvested email is a possible target for phishing and password-based attacks. Because this data comes only from public sources, the target organization never knows it is being studied.

---

## Task 2 — Harvest with All Sources (limit 50)

**Objective:** Find email IDs & sub-domains related to the target organization `microsoft.com` using theHarvester in Kali Linux with **all sources**. Set the limit of number of results to 50.

**Solution Steps:**
1. Open a new terminal window in Kali Linux.
2. Run the following command:
   ```bash
   theHarvester -d microsoft.com -l 50 -b all
   ```
   - `-b all` runs the query against every supported source at once.
3. theHarvester attempts each source one by one. Some sources may show a **"Missing API key"** warning — this is expected, since certain sources (like bevigil, Bitbucket, BuiltWith, Brave) require a paid or registered API key that is not configured by default. The tool continues with the remaining sources regardless.
4. Once complete, review the combined results (emails, sub-domains, hosts) gathered from all sources that did not require missing API keys.

### Screenshot
![theHarvester All Sources Results](screenshots/task2-harvester-all.png)
### Screenshot
![theHarvester All Sources Results](screenshots/task2-harvester2-all.png)

**How attackers use this:** Running against all available sources maximizes the amount of public data collected in one pass. Each sub-domain discovered is another potential entry point into the organization that a defender may have forgotten about — expanding the attack surface an attacker can target.

---

# 💡 Why Footprinting with theHarvester Matters

theHarvester collects emails, sub-domains, and hosts from dozens of public sources without ever touching the target directly. Each harvested email is a possible target for phishing and password attacks. Each sub-domain is another door into the organization that a defender may have forgotten about.

Because the tool only reads public data, the target never knows it is being studied, which is exactly why this kind of passive recon is so powerful and so hard to detect. Defenders run the same tool on themselves to see what an attacker would see, and then reduce what they leak.

---

# 💡 Extra References & Tips

- theHarvester is passive recon: it reads public sources and never touches the target.
- Different data sources return different results, so always try more than one.
- Harvested emails feed phishing campaigns; sub-domains expand the attack surface.
- The less an organization exposes publicly, the harder every later attack stage becomes.
- theHarvester comes pre-installed in Kali Linux. On other OSes it can be installed with:
  ```bash
  sudo apt-get install theHarvester
  ```
  If that does not work, it can be installed manually from GitHub:
  ```bash
  git clone https://github.com/laramies/theHarvester.git
  cd theHarvester
  sudo python ./theHarvester.py
  ```

---

# 💡 What I Learned

### 1. OSINT Automation
I learned how theHarvester automates the process of collecting emails, sub-domains, and hosts from dozens of public sources in a single command.

### 2. Source-Specific vs Combined Results
I learned how querying a single source (Baidu) compares to querying all supported sources at once, and why results can vary significantly between them.

### 3. Understanding Tool Limitations
I learned that some sources require API keys that aren't configured by default, and that this doesn't stop the tool — it simply skips those sources and continues with the rest.

### 4. Passive Reconnaissance
I learned that theHarvester never sends a request directly to the target, making this form of footprinting extremely quiet and hard to detect.

### 5. Documentation
I learned how to properly record command-line tool output with screenshots and text files for a professional report.

---

# 🔐 Security & Ethical Use

This lab is created for learning and cybersecurity practice.

All testing was performed against a publicly documented lab target (`microsoft.com`) as part of an authorized training exercise, using only passive, publicly available OSINT sources.

---

# 🔗 Tools & Resources

- **theHarvester GitHub:** https://github.com/laramies/theHarvester

---

# 👤 Author

**Zain ul Abidin**

**Cyber Security Student B083**

---

## 📌 Project Information

**Program Name:** Cybersecurity at Networkwalks
**Week:** 02
**Project Module:** PM4 — Footprinting & Reconnaissance Attacks with theHarvester
**Author:** Zain ul Abidin
**B-Number:** B083
**Repository:** GitHub
