# Week-2-PM1-FOOTPRINTING-RECONNAISSANCE-ATTACKS-WITH-MULTIPLE-KALI-TOOLS
FOOTPRINTING &amp; RECONNAISSANCE ATTACKS WITH MULTIPLE KALI TOOLS


PENETRATION TESTING REPORT
FOOTPRINTING & NETWORK SCANNING PHASES
B084 W2| CYBERSECURITY | NETWORKWALKS



Pentester Name	Moira Boitumelo Maribatsi
Program/Batch	B084-Networkwalks
Date	11 November 2026
Modules completed	W2-PM1 (Multiple Kali Tools)
W2-PM5 (Zenmap Scanning)
Client/Target	1.Networkwalks (secured written permission already)
2.My own local LAN Network
Permission secured from client?	Yes
Phases covered	Phase 1: Reconnaissance & Footprinting
Phase 2: Scanning & Network Discovery
Phase 3-5: In Progress


1.	Liability Disclaimer
I have performed these activities only on the systems & devices where I had secured written permission or the devices/systems that I own myself. All these materials are for education and research purpose only. Do not use anything from here to break the law. The instructor, the authors and Networkwalks are not responsible for what you do with this knowledge. Every action you take is your own responsibility. Misuse can lead to criminal charges, heavy fines, loss of your job and a permanent record. In most countries unauthorized access is a crime even when nothing is damaged.


2.	Introduction
This report outlines the footprinting of the networkwalks.com domain using several Kali Linux tools and the scanning of my local network using Zenmap. The exercises demonstrate how an attacker gathers public information and maps live hosts on a network. This report details the activities completed as part of my Week 2 internship program at Networkwalks. Each step includes the command used, results observed, evidence in the form of screenshots, and insights on the significance of each finding.


3.	Tools Used
The following table summarizes each tool employed in this report and its corresponding purpose:


*Tool	Purpose*
Kali Linux & Windows	                   Operating systems used for reconnaissance activities
WHOIS	                                   Find domain registration details (owner, dates, name servers)
WhatWeb	                                 Fingerprint web technologies (server, CMS, plugins, IP)
nslookup	                               Resolve the domain name to its IP address using DNS
curl -I	                                 Read the HTTP response headers of the website
wafw00f	                                 Detect whether a Web Application Firewall protects the site
dnsrecon	                               Enumerate all DNS records (NS, MX, SPF, TXT, SRV)
Zenmap                                   (Nmap GUI)	Scan the local subnet to find live hosts, IPs and MAC addresses
Windows                                  CMD	Local IP and MAC address identification


4. Activities Performed

4.1 Footprinting & Reconnaissance
I conducted reconnaissance against the networkwalks.com domain utilizing six tools: WHOIS, WhatWeb, nslookup, curl, wafw00f, and DNSRecon. Each tool provided distinct information regarding the target.

•	WHOIS revealed domain registration details, including the registrar and hosting provider.
•	WhatWeb identified the technologies in use, specifically WordPress 7.0.4 and WP Download Manager 3.3.58. This information is crucial as attackers can search for vulnerabilities associated with these versions.
•	Using nslookup, I resolved the domain to its IP address, 192.232.216.135, allowing for direct scanning of the server.
•	The curl command with the -I flag exposed HTTP headers, revealing server and API details, aiding in technology fingerprinting.
•	wafw00f identified ModSecurity, indicating the presence of a firewall which helps shape the initial approach of an attacker.
•	Lastly, DNSRecon provided a comprehensive list of DNS records, exposing email and service-related data, each serving as potential points for exploitation.


4.2 Network Scanning with Zenmap
For the network discovery activity, I utilized Zenmap on my local network. After determining my local subnet with the ipconfig command, I initiated a Ping Scan in Zenmap to discover live hosts.

The results identified multiple active IPs and their MAC addresses, which are crucial for understanding the network infrastructure. Post-scan, I generated and saved a network topology in PDF format as per the task requirements.





5.	Risk Analysis / Impact

Based on the findings from the footprinting and scanning activities, the following potential risks were identified:

#	Risk / Finding	Evidence / Observation	Potential Impact	Risk Level
1	Exposure of web technology information	WhatWeb revealed WordPress and WP Download Manager	Attackers can exploit known vulnerabilities in outdated software.	Medium
2	Identifiable server IP address	nslookup resolved to 192.232.216.135	An attacker can scan the server for weaknesses.	Low
3	Sensitive HTTP technical information revealed	Curl output displayed HTTP headers	Could assist in fingerprinting and enumeration of the web application.	Low
4	Identifiable WAF technology	Wafw00f detected ModSecurity	Information about defenses may influence the attack strategy.	Low
5	Exposed DNS infrastructure	DNSRecon provided detailed DNS records	Insight into the infrastructure could lead to targeted attacks.	Medium
6	Multiple live hosts visible	Zenmap identified several active hosts	Presence of unknown devices could indicate unauthorized access or vulnerabilities.	Medium

Note: The identified risks are based on collected information, not confirmed vulnerabilities. Further authorized testing is necessary to validate any actual vulnerabilities.

6.	Recommendations

To mitigate the observed risks, I recommend implementing the following security measures:

•	Review technology exposure: Regularly assess what technology details are publicly visible to minimize potential exploit paths.
•	Software updates: Ensure that CMS platforms and plugins are current with security patches.
•	Analyze HTTP headers: Limit the exposure of unnecessary technical information in HTTP responses.
•	DNS record scrutiny: Conduct regular checks of DNS records to ensure minimal exposure of critical information.
•	Monitor WAF effectiveness: Continuously update and maintain the WAF settings to address emerging threats.
•	Regular network scanning: Implement periodic internal network scans to identify active devices.
•	Investigate unauthorized devices: Look into any unexpected devices on the network promptly.
•	Documentation upkeep: Maintain and regularly update network documentation to reflect current configurations and devices.
•	Perform authorized security testing: Ensure all reconnaissance and scanning activities are conducted with proper authorization.
7.	Conclusion
During Week 2 of my Cybersecurity & Ethical Hacking internship, I engaged in practical activities involving footprinting, reconnaissance, and network scanning. I collected valuable information regarding the networkwalks.com domain and my local network, demonstrating the significance of information gathering as a precursor to potential exploitation. This experience underlined the importance of maintaining updated documentation and security practices to safeguard against unauthorized access.


8.	Evidences Collected
Screenshots, command outputs, and data collected during the activities.

Curl –I Results

 

     dnsrecon –d Results

 


nslookup Results

 

Wafh00f Results

 


Whatweb Results
 


Whois Results

 
________________________________________



👤 Author
Moira Boitumelo Maribatsi
Cybersecurity Professional B084
Certifications: CCNA, ITIL V4, CompTia Sec +
LinkedIn: https://www.linkedin.com/in/moira-boitumelo-maribatsi-60855b1a0
Git Hub: Boitumelo0708 (Boitumelo Maribatsi )


📌 Project Information
Program Name: Cybersecurity program at Networkwalks | Week: 02 | Repository: GitHub

TASKS
•	Task 1. Run whois to find the domain registration details.
•	Task 2. Run whatweb to fingerprint the web technologies.
•	Task 3. Run nslookup to resolve the domain to its IP address.
•	Task 4. Run curl -I to read the HTTP response headers.
•	Task 5. Run wafw00f to detect a Web Application Firewall.
•	Task 6. Run dnsrecon to enumerate all DNS records.
All tasks are completed, and evidence is collected for this.
