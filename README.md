# networkwalks-week2
Footprinting and Ressonance Attacks
# Week 2 Penetration Testing Report – Footprinting, Reconnaissance & Network Scanning

**Networkwalks Cybersecurity & Ethical Hacking Internship | Batch B084K | Week 02**

This repository contains my Week 2 penetration testing report and the screenshots I collected as evidence. The work covers the first two phases of a penetration test:

- **Phase 1:** Reconnaissance & Footprinting
- **Phase 2:** Scanning & Network Discovery

All activities were performed on **Kali Linux** (running in VMware Workstation), and only against authorised targets.

---

##  Repository Structure

| File / Folder | Description |
|---|---|
| `Week_2_Pentesting_report.docx` | Full penetration testing report |
| `screenshots/` | Screenshots taken as evidence for each module |
| `README.md` | Project overview (this file) |

---

##  Modules Completed

| Module | Title | Target |
|---|---|---|
| W2-PM1 | Footprinting with Multiple Kali Tools | networkwalks.com |
| W2-PM2 | Footprinting with GHDB (Google Hacking Database) | Public Google-indexed content |
| W2-PM3 | Footprinting with Maltego | networkwalks.com |
| W2-PM4 | Footprinting with theHarvester | microsoft.com (passive OSINT) |
| W2-PM5 | Network Scanning with Zenmap | My own local network (192.168.10.0/24) |

---

##  Tools Used

| Tool | Purpose |
|---|---|
| `whois` | Domain registration details (registrar, dates, name servers) |
| `whatweb` | Web technology fingerprinting (CMS, plugins, server, IP) |
| `nslookup` | Resolve the domain to its IP address |
| `curl -I` | Read HTTP response headers |
| `wafw00f` | Detect a Web Application Firewall |
| `dnsrecon` | Enumerate DNS records (SOA, NS, MX, A, TXT, SRV) |
| GHDB + Google | Find exposed cameras and open directories with Google dorks |
| Maltego 4.13.0 | Graph-based OSINT; find emails linked to a domain |
| theHarvester 4.11.1 | Collect emails, hosts, IPs and ASNs from public sources |
| Zenmap / Nmap 7.991 | Ping scan to discover live hosts, IP & MAC addresses and topology |

---

##  Key Findings

- **networkwalks.com** runs WordPress 7.1.4 with WP Download Manager 3.3.76 on Apache, hosted on HostGator (IP 192.232.216.135), and is protected by a **ModSecurity (SpiderLabs) WAF**.
- DNS enumeration showed the BIND name-server version (9.16.23-RH), cPanel email records, an SPF soft-fail policy (`~all`), and that DNSSEC is not enabled.
- **Maltego** and **WhatWeb** both found the public email address info@networkwalks.com.
- **GHDB dorks** found live, unprotected webcams and open directory listings on the Internet.
- **theHarvester** (all sources) found 9,976 hosts, 147 IPs, 6 ASNs and 3 email addresses for microsoft.com, including many dev, staging and internal host names.
- **Zenmap** found **4 live hosts** on my lab subnet 192.168.10.0/24, and I recorded their IP and MAC addresses and the network topology.

> These are observations from information gathering only. No exploitation was performed, and no finding is a confirmed vulnerability.

---

##  Main Recommendations

- Hide CMS, plugin and DNS server version information
- Keep WordPress, plugins and server software patched
- Disable directory listing on web servers
- Strengthen email security (SPF `-all`, DMARC) and enable DNSSEC
- Secure Internet-facing cameras with authentication and keep them off the open Internet
- Regularly review your public attack surface and internal network devices

---

##  Disclaimer

This project was completed for **educational purposes only** as part of the Networkwalks Cybersecurity Internship. All testing was performed against systems I had written permission to test, on my own network, or using publicly available information (passive reconnaissance). Do not use these techniques against any system without explicit written authorisation. Unauthorised access is illegal.

---

## Author

**Tracy Muhoozi**
Cybersecurity Intern, Batch B084K, Networkwalks



## 📌 Project Information

**Program:** Cybersecurity & Ethical Hacking Internship at Networkwalks | **Week:** 02 | **Date:** November 2026
