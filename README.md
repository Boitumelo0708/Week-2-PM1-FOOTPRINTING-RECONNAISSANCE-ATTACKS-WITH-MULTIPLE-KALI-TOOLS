# Week-2-PM1-FOOTPRINTING-RECONNAISSANCE-ATTACKS-WITH-MULTIPLE-KALI-TOOLS
FOOTPRINTING &amp; RECONNAISSANCE ATTACKS WITH MULTIPLE KALI TOOLS


PENETRATION TESTING REPORT
FOOTPRINTING & NETWORK SCANNING PHASES
B084 W2| CYBERSECURITY | NETWORKWALKS

# Penetration Testing Report: Footprinting & Network Scanning

**B084 W2 | Cybersecurity | Networkwalks**

| | |
|---|---|
| **Pentester** | Moira Boitumelo Maribatsi |
| **Program/Batch** | B084-Networkwalks |
| **Date** | 11 November 2026 |
| **Modules completed** | W2-PM1 (Multiple Kali Tools), W2-PM5 (Zenmap Scanning) |
| **Client/Target** | 1. Networkwalks (written permission secured) 2. My own local LAN network |
| **Permission secured from client?** | Yes |
| **Phases covered** | Phase 1: Reconnaissance & Footprinting; Phase 2: Scanning & Network Discovery; Phases 3-5: In progress |

---

## 1. Liability Disclaimer

I have performed these activities only on systems and devices where I had secured written permission, or on devices and systems that I own myself. All materials are for education and research purposes only. Do not use anything from here to break the law. The instructor, the authors and Networkwalks are not responsible for what you do with this knowledge. Every action you take is your own responsibility. Misuse can lead to criminal charges, heavy fines, loss of your job and a permanent record. In most countries unauthorized access is a crime even when nothing is damaged.

## 2. Introduction

This report outlines the footprinting of the networkwalks.com domain using several Kali Linux tools and the scanning of my local network using Zenmap. The exercises demonstrate how an attacker gathers public information and maps live hosts on a network. This report details the activities completed as part of my Week 2 internship program at Networkwalks. Each step includes the command used, results observed, evidence in the form of screenshots, and insights on the significance of each finding.

## 3. Tools Used

| Tool | Purpose |
|---|---|
| Kali Linux & Windows | Operating systems used for reconnaissance activities |
| WHOIS | Find domain registration details (owner, dates, name servers) |
| WhatWeb | Fingerprint web technologies (server, CMS, plugins, IP) |
| nslookup | Resolve the domain name to its IP address using DNS |
| curl -I | Read the HTTP response headers of the website |
| wafw00f | Detect whether a Web Application Firewall protects the site |
| dnsrecon | Enumerate all DNS records (NS, MX, SPF, TXT, SRV) |
| Zenmap (Nmap GUI) | Scan the local subnet to find live hosts, IPs and MAC addresses |
| Windows CMD | Local IP and MAC address identification |

## 4. Activities Performed

### 4.1 Footprinting & Reconnaissance

I conducted reconnaissance against the networkwalks.com domain using six tools: WHOIS, WhatWeb, nslookup, curl, wafw00f, and DNSRecon. Each tool provided distinct information about the target.

- **WHOIS** revealed domain registration details, including the registrar and hosting provider.
- **WhatWeb** identified the technologies in use, specifically WordPress 7.0.4 and WP Download Manager 3.3.58. This is crucial as attackers can search for vulnerabilities associated with these versions.
- **nslookup** resolved the domain to its IP address, 192.232.216.135, allowing direct scanning of the server.
- **curl -I** exposed HTTP headers, revealing server and API details that aid technology fingerprinting.
- **wafw00f** identified ModSecurity, indicating the presence of a firewall, which helps shape an attacker's initial approach.
- **DNSRecon** provided a comprehensive list of DNS records, exposing email and service-related data, each a potential point for exploitation.

### 4.2 Network Scanning with Zenmap

For the network discovery activity, I used Zenmap on my local network. After determining my local subnet with the `ipconfig` command, I ran a Ping Scan in Zenmap to discover live hosts.

The results identified multiple active IPs and their MAC addresses, which are crucial for understanding the network infrastructure. After the scan, I generated and saved a network topology in PDF format as per the task requirements.

## 5. Risk Analysis / Impact

| # | Risk / Finding | Evidence / Observation | Potential Impact | Risk Level |
|---|---|---|---|---|
| 1 | Exposure of web technology information | WhatWeb revealed WordPress and WP Download Manager | Attackers can exploit known vulnerabilities in outdated software | Medium |
| 2 | Identifiable server IP address | nslookup resolved to 192.232.216.135 | An attacker can scan the server for weaknesses | Low |
| 3 | Sensitive HTTP technical information revealed | curl output displayed HTTP headers | Could assist in fingerprinting and enumeration of the web application | Low |
| 4 | Identifiable WAF technology | wafw00f detected ModSecurity | Information about defenses may influence the attack strategy | Low |
| 5 | Exposed DNS infrastructure | DNSRecon provided detailed DNS records | Insight into the infrastructure could lead to targeted attacks | Medium |
| 6 | Multiple live hosts visible | Zenmap identified several active hosts | Unknown devices could indicate unauthorized access or vulnerabilities | Medium |

> **Note:** The identified risks are based on collected information, not confirmed vulnerabilities. Further authorized testing is necessary to validate any actual vulnerabilities.

## 6. Recommendations

- **Review technology exposure:** Regularly assess what technology details are publicly visible to minimize potential exploit paths.
- **Software updates:** Ensure CMS platforms and plugins are current with security patches.
- **Analyze HTTP headers:** Limit the exposure of unnecessary technical information in HTTP responses.
- **DNS record scrutiny:** Conduct regular checks of DNS records to ensure minimal exposure of critical information.
- **Monitor WAF effectiveness:** Continuously update and maintain WAF settings to address emerging threats.
- **Regular network scanning:** Implement periodic internal network scans to identify active devices.
- **Investigate unauthorized devices:** Look into any unexpected devices on the network promptly.
- **Documentation upkeep:** Maintain and regularly update network documentation to reflect current configurations and devices.
- **Perform authorized security testing:** Ensure all reconnaissance and scanning activities are conducted with proper authorization.

## 7. Conclusion

During Week 2 of my Cybersecurity & Ethical Hacking internship, I engaged in practical activities involving footprinting, reconnaissance, and network scanning. I collected valuable information about the networkwalks.com domain and my local network, demonstrating the significance of information gathering as a precursor to potential exploitation. This experience underlined the importance of maintaining updated documentation and security practices to safeguard against unauthorized access.

## 8. Evidence Collected

Screenshots of the command outputs collected during the activities.

### curl -I Results
<img width="1788" height="550" alt="image" src="https://github.com/user-attachments/assets/1b48ba8b-a396-43ea-a264-030406826f63" />


### dnsrecon -d Results
<img width="1838" height="1222" alt="image" src="https://github.com/user-attachments/assets/b749389f-b555-484f-a96a-a8531a45bf0a" />


### nslookup Results
<img width="1774" height="649" alt="image" src="https://github.com/user-attachments/assets/4dfe12cd-eb0e-4a18-bebc-ec1b4d0b04dd" />


### wafw00f Results
<img width="1789" height="814" alt="image" src="https://github.com/user-attachments/assets/2af730a6-d72e-4b53-b227-c8ed5599cf42" />

### WhatWeb Results
<img width="1919" height="944" alt="image" src="https://github.com/user-attachments/assets/ea19b176-bdca-4444-8cf5-99cf6a9efd51" />


### WHOIS Results
<img width="2107" height="1125" alt="image" src="https://github.com/user-attachments/assets/f05319a1-fdbc-45e5-a983-31903929c6fb" />


---
## Zenmap LAN Topology
<img width="503" height="441" alt="Zenmap LAN Topology" src="https://github.com/user-attachments/assets/00677941-cc0f-4ffe-82d3-5251754fc239" />

## Author

**Moira Boitumelo Maribatsi**
Cybersecurity Professional, B084
Certifications: CCNA, ITIL V4, CompTIA Security+
LinkedIn: [moira-boitumelo-maribatsi](https://www.linkedin.com/in/moira-boitumelo-maribatsi-60855b1a0)
GitHub: [Boitumelo0708](https://github.com/Boitumelo0708)

## Project Information

**Program:** Cybersecurity program at Networkwalks | **Week:** 02 | **Repository:** GitHub

### Tasks

- [x] Task 1. Run `whois` to find the domain registration details.
- [x] Task 2. Run `whatweb` to fingerprint the web technologies.
- [x] Task 3. Run `nslookup` to resolve the domain to its IP address.
- [x] Task 4. Run `curl -I` to read the HTTP response headers.
- [x] Task 5. Run `wafw00f` to detect a Web Application Firewall.
- [x] Task 6. Run `dnsrecon` to enumerate all DNS records.

All tasks are completed and evidence has been collected.
