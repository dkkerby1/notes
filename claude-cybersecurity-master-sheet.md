Cybersecurity Master Reference
CORE CONCEPTS
CIA Triad:

Confidentiality - only authorized access
Integrity - data accuracy and trustworthiness
Availability - systems accessible when needed

Authentication vs Authorization:

Authentication - proving identity (login)
Authorization - what you're allowed to do (permissions)

Defense in Depth - multiple layers of security
Principle of Least Privilege - minimum access needed
Zero Trust - never trust, always verify
ATTACK TYPES
Malware:

Virus - self-replicating, needs host file
Worm - self-replicating, spreads independently
Trojan - disguised as legitimate software
Ransomware - encrypts files, demands payment
Spyware - monitors activity secretly
Rootkit - hides malware presence
Keylogger - records keystrokes

Social Engineering:

Phishing - fake emails/websites
Spear Phishing - targeted phishing
Whaling - targets executives
Vishing - voice/phone phishing
Smishing - SMS phishing
Pretexting - fabricated scenario
Baiting - offering something to exploit
Tailgating - physical unauthorized entry

Network Attacks:

DDoS - overwhelm with traffic
Man-in-the-Middle (MITM) - intercept communication
DNS Spoofing - redirect to fake site
ARP Spoofing - intercept LAN traffic
Session Hijacking - steal active session
Packet Sniffing - capture network traffic
Port Scanning - find open ports

Web Application Attacks:

SQL Injection - malicious database queries
XSS (Cross-Site Scripting) - inject malicious scripts
CSRF (Cross-Site Request Forgery) - unauthorized actions
Path Traversal - access unauthorized files
Command Injection - execute system commands
File Upload Vulnerabilities - upload malicious files

Password Attacks:

Brute Force - try all combinations
Dictionary Attack - try common passwords
Credential Stuffing - reuse leaked credentials
Rainbow Table - precomputed hash lookup
Password Spraying - few passwords, many accounts

Other Attacks:

Zero-Day Exploit - unknown vulnerability
Privilege Escalation - gain higher access
Backdoor - hidden access method
Logic Bomb - triggers on condition
Insider Threat - attack from within org

CRYPTOGRAPHY
Encryption Types:

Symmetric - same key encrypt/decrypt (AES, DES)
Asymmetric - public/private key pair (RSA, ECC)

Hashing:

One-way function, same input = same output
MD5 - 128-bit, deprecated (collisions)
SHA-1 - 160-bit, deprecated
SHA-256 - 256-bit, secure
SHA-512 - 512-bit, more secure
bcrypt - password hashing with salt

Common Uses:

SSL/TLS - secure web traffic (HTTPS)
SSH - secure remote access
VPN - encrypted network tunnel
PGP/GPG - email encryption
Digital Signatures - verify authenticity
Certificates - verify identity (PKI)

SECURITY TOOLS
Reconnaissance:
nmap - network scanner, port discovery
-sV service version detection
-O OS detection
-sS stealth SYN scan
-p- scan all ports
whois - domain registration info
dig - DNS lookup
theHarvester - gather emails, subdomains
Vulnerability Scanning:
nessus - comprehensive vuln scanner
openvas - open-source vuln scanner
nikto - web server scanner
burp suite - web app security testing
Penetration Testing:
metasploit - exploit framework
sqlmap - SQL injection automation
john - password cracking
hashcat - advanced password cracking
hydra - brute force login
aircrack-ng - WiFi security testing
Network Analysis:
wireshark - packet analyzer GUI
tcpdump - command-line packet capture
netstat - network connections
ss - socket statistics (newer netstat)
Security Monitoring:
snort - intrusion detection system
fail2ban - blocks suspicious IPs
OSSEC - host intrusion detection
splunk - SIEM platform
Forensics:
autopsy - digital forensics platform
volatility - memory forensics
binwalk - firmware analysis
LINUX SECURITY COMMANDS
sudo - run as superuser
chmod - change file permissions
chmod 600 file owner read/write only
chmod 644 file owner rw, others read
chmod 755 file owner rwx, others rx
chown user:group file - change ownership
passwd - change password
last - recent logins
who - currently logged in
w - who's logged in and what they're doing
ps aux - running processes
netstat -tulpn - listening ports
iptables - firewall rules
ufw - simplified firewall
ufw enable turn on
ufw allow 22 allow port 22
fail2ban-client status - banned IPs
COMMON PORTS
20/21 - FTP (File Transfer)
22 - SSH (Secure Shell)
23 - Telnet (insecure remote)
25 - SMTP (Email)
53 - DNS (Domain Name System)
80 - HTTP (Web)
110 - POP3 (Email retrieval)
143 - IMAP (Email)
443 - HTTPS (Secure web)
445 - SMB (File sharing)
3306 - MySQL
3389 - RDP (Remote Desktop)
5432 - PostgreSQL
8080 - HTTP alternate
SECURITY BEST PRACTICES
Passwords:

12+ characters minimum
Mix upper/lower/numbers/symbols
Unique for each account
Use password manager
Enable MFA/2FA

System Hardening:

Keep software updated
Disable unused services
Remove default accounts
Configure firewall
Encrypt sensitive data
Regular backups
Monitor logs
Principle of least privilege

Network Security:

Segment networks
Use VLANs
Disable unused ports
Strong WiFi encryption (WPA3/WPA2)
Change default credentials
Regular security audits

Web Security:

Input validation
Parameterized queries (prevent SQL injection)
Output encoding (prevent XSS)
HTTPS everywhere
Security headers (CSP, HSTS)
Rate limiting
Keep frameworks updated

INCIDENT RESPONSE
Steps:

Preparation - plan, tools ready
Identification - detect incident
Containment - limit damage
Eradication - remove threat
Recovery - restore systems
Lessons Learned - post-mortem

Important:

Document everything
Preserve evidence
Follow chain of custody
Communicate with stakeholders

COMPLIANCE & FRAMEWORKS
NIST Cybersecurity Framework:

Identify
Protect
Detect
Respond
Recover

Common Regulations:

GDPR - EU data protection
HIPAA - healthcare data (US)
PCI DSS - payment card data
SOX - financial reporting
CCPA - California privacy

Security Standards:

ISO 27001 - information security
CIS Controls - security best practices
OWASP Top 10 - web app risks

VULNERABILITIES & CVE
CVE - Common Vulnerabilities and Exposures

Unique ID for known vulnerabilities
Format: CVE-YYYY-NNNNN

CVSS - Common Vulnerability Scoring System

0.0-3.9: Low
4.0-6.9: Medium
7.0-8.9: High
9.0-10.0: Critical

Resources:

cve.mitre.org
nvd.nist.gov
exploit-db.com

RED TEAM vs BLUE TEAM
Red Team (Offense):

Simulate attacks
Find vulnerabilities
Test defenses
Penetration testing

Blue Team (Defense):

Monitor systems
Detect threats
Respond to incidents
Improve security posture

Purple Team:

Collaboration between red/blue
Share knowledge
Improve both offense and defense