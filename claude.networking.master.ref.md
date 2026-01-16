Networking Master Reference
OSI MODEL (7 LAYERS)
7. Application - user-facing (HTTP, FTP, DNS, SMTP)
6. Presentation - data format, encryption (SSL/TLS)
5. Session - establishes/maintains connections
4. Transport - end-to-end delivery (TCP, UDP)
3. Network - routing, IP addressing (IP, ICMP)
2. Data Link - MAC addressing, switches (Ethernet, WiFi)
1. Physical - cables, signals, hubs
Mnemonic: "All People Seem To Need Data Processing"
TCP/IP MODEL (4 LAYERS)
4. Application - combines OSI layers 5-7
3. Transport - TCP, UDP
2. Internet - IP, routing
1. Network Access - combines OSI layers 1-2
IP ADDRESSING
IPv4:

32-bit address: 192.168.1.1
4 octets, each 0-255
~4.3 billion addresses

IPv6:

128-bit address: 2001:0db8:85a3::8a2e:0370:7334
Hexadecimal, separated by colons
Virtually unlimited addresses

Private IP Ranges (not routable on internet):

10.0.0.0 - 10.255.255.255 (Class A)
172.16.0.0 - 172.31.255.255 (Class B)
192.168.0.0 - 192.168.255.255 (Class C)
127.0.0.1 - localhost/loopback

Special Addresses:

0.0.0.0 - any address
255.255.255.255 - broadcast
169.254.x.x - APIPA (auto-config when DHCP fails)

SUBNET MASKS & CIDR
Common Subnet Masks:

/8 or 255.0.0.0 - Class A (16M hosts)
/16 or 255.255.0.0 - Class B (65K hosts)
/24 or 255.255.255.0 - Class C (254 hosts)
/32 - single host

CIDR Notation:
192.168.1.0/24 - network with 256 IPs (254 usable)
First IP = network address
Last IP = broadcast address
Quick Reference:

/30 - 4 IPs (2 usable) - point-to-point
/29 - 8 IPs (6 usable)
/28 - 16 IPs (14 usable)
/27 - 32 IPs (30 usable)
/26 - 64 IPs (62 usable)
/25 - 128 IPs (126 usable)

PROTOCOLS
TCP (Transmission Control Protocol):

Connection-oriented
Reliable, ordered delivery
Error checking, retransmission
Slower but guaranteed
Used for: HTTP, HTTPS, FTP, SSH, email

UDP (User Datagram Protocol):

Connectionless
No guarantee of delivery
No ordering
Faster, lower overhead
Used for: DNS, DHCP, streaming, gaming, VoIP

ICMP (Internet Control Message Protocol):

Network diagnostics
Ping, traceroute
Error reporting

ARP (Address Resolution Protocol):

Maps IP to MAC address
Layer 2 protocol

DHCP (Dynamic Host Configuration Protocol):

Automatically assigns IP addresses
Also provides subnet mask, gateway, DNS

DNS (Domain Name System):

Translates domain names to IP addresses
Port 53
Hierarchical structure

COMMON PORTS (see Cybersecurity sheet for full list)
Essential:
22 - SSH
53 - DNS
80 - HTTP
443 - HTTPS
3389 - RDP
NETWORKING COMMANDS
Linux/Mac
ping <host> - test connectivity
-c 4 send 4 packets
traceroute <host> - show route to host
nslookup <domain> - DNS lookup
dig <domain> - detailed DNS info
dig +short brief output
host <domain> - simple DNS lookup
ip addr or ifconfig - show IP config
ip route or route - routing table
ip link - network interfaces
netstat -tulpn - listening ports
-t TCP
-u UDP
-l listening
-p program
-n numeric
ss -tulpn - modern netstat replacement
arp -a - ARP cache (IP to MAC)
curl <url> - transfer data from URL
-I show headers only
-v verbose
wget <url> - download file
tcpdump - packet capture
tcpdump -i eth0 capture on interface
tcpdump port 80 filter by port
nmap <target> - network scanner
Windows
ipconfig - IP configuration
/all detailed info
/release release DHCP
/renew renew DHCP
/flushdns clear DNS cache
ping <host> - test connectivity
-t continuous ping
tracert <host> - trace route
nslookup <domain> - DNS lookup
netstat -ano - network connections
-a all connections
-n numeric
-o process ID
arp -a - ARP cache
route print - routing table
pathping <host> - combines ping and tracert
getmac - show MAC addresses
nbtstat -a <computer> - NetBIOS info
NETWORK DEVICES
Hub:

Layer 1 device
Broadcasts to all ports
Inefficient, creates collisions
Rarely used today

Switch:

Layer 2 device
Forwards based on MAC address
Each port = separate collision domain
Most common LAN device

Router:

Layer 3 device
Routes between networks
Uses IP addresses
Connects different networks

Gateway:

Connects different network protocols
Can be any layer
Default gateway = router to internet

Firewall:

Filters traffic based on rules
Can be hardware or software
Stateful vs stateless

Access Point (AP):

Wireless network access
Bridges WiFi to wired network

Modem:

Converts digital to analog signals
Connects to ISP

NAT (Network Address Translation)
Purpose: Convert private IPs to public IP
Types:

Static NAT - one-to-one mapping
Dynamic NAT - pool of public IPs
PAT (Port Address Translation) - many-to-one with ports

Benefits:

Conserves public IP addresses
Adds security layer
Hides internal network structure

DNS RECORDS
A Record - domain to IPv4
AAAA Record - domain to IPv6
CNAME - alias to another domain
MX - mail server
NS - name server
TXT - text info (SPF, DKIM)
PTR - reverse DNS (IP to domain)
SOA - start of authority
NETWORK TOPOLOGIES
Bus - single cable, all devices connected
Star - all devices connect to central hub/switch
Ring - circular connection
Mesh - every device connects to every other
Hybrid - combination of topologies
WIRELESS NETWORKING
Standards:

802.11a - 5GHz, 54Mbps
802.11b - 2.4GHz, 11Mbps
802.11g - 2.4GHz, 54Mbps
802.11n - 2.4/5GHz, 600Mbps
802.11ac - 5GHz, 1-7Gbps (WiFi 5)
802.11ax - 2.4/5/6GHz, 9.6Gbps (WiFi 6)

Security:

WEP - broken, don't use
WPA - weak, avoid
WPA2 - good, widely used
WPA3 - best, newest

Channels:

2.4GHz: channels 1, 6, 11 don't overlap
5GHz: more channels, less interference

VPN (Virtual Private Network)
Types:

Site-to-Site - connects networks
Remote Access - connects users to network

Protocols:

OpenVPN - open source, secure
IPsec - industry standard
L2TP - often with IPsec
PPTP - outdated, insecure
WireGuard - modern, fast

TROUBLESHOOTING METHODOLOGY
1. Identify the problem

Gather info
Question users
Identify symptoms

2. Establish theory

Most likely cause first
Check obvious things

3. Test theory

Confirm or disprove

4. Establish plan

Action plan to resolve

5. Implement solution

Apply fix

6. Verify functionality

Test it works
Prevent recurrence

7. Document

Record findings
For future reference

COMMON ISSUES & FIXES
No internet connection:

Check physical connections
ping 127.0.0.1 - test TCP/IP stack
ping default gateway - test local network
ping 8.8.8.8 - test internet (Google DNS)
ping google.com - test DNS
Check IP config (ipconfig or ip addr)
Renew DHCP
Check firewall

Slow network:

Check bandwidth usage
Test with speed test
Check for interference (WiFi)
Update network drivers
Restart router/switch
Check for malware

IP conflict:

Two devices same IP
Release/renew DHCP
Use static IPs outside DHCP range

DNS issues:

Flush DNS cache
Try different DNS (8.8.8.8, 1.1.1.1)
Check DNS settings

NETWORK PERFORMANCE
Bandwidth - maximum data transfer rate
Throughput - actual data transfer rate
Latency - delay/ping time
Jitter - variation in latency
Packet Loss - percentage of lost packets
Good metrics:

Latency: <20ms excellent, <100ms good
Packet loss: <1% good, 0% ideal
Jitter: <30ms good for VoIP/gaming