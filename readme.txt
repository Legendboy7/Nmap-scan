1. Generate test traffic
Run these from Kali, one at a time, noting the timestamps and scan type:

# Host discovery across the lab subnet
nmap -sn 192.168.*.*/24

# TCP SYN scan of a limited port range
sudo nmap -sS -p 1-1000 192.168.*.*

# TCP connect scan
nmap -sT -p 1-1000 192.168.*.*

# UDP scan of a small, common-port set
sudo nmap -sU -p 53,123,161 192.168.*.*

# Service/version detection on selected ports
nmap -sV -p 22,80,443 192.168.*.*

──(unknown㉿kali)-[~/Documents/GitHub/Nmap-scan]
└─$ nmap -sS -sV -Pn -oA results.txt 192.168.*.*
Starting Nmap 7.991 ( https://nmap.org ) at 2026-10-25 04:17 -0400
Stats: 0:00:17 elapsed; 0 hosts completed (1 up), 1 undergoing Service Scan
Service scan Timing: About 30.00% done; ETC: 04:18 (0:00:25 remaining)
Stats: 0:00:42 elapsed; 0 hosts completed (1 up), 1 undergoing Service Scan
Service scan Timing: About 40.00% done; ETC: 04:18 (0:00:28 remaining)
Nmap scan report for 192.168.*.*
Host is up (0.00017s latency).
Not shown: 990 closed tcp ports (reset)
PORT      STATE SERVICE      VERSION
135/tcp   open  msrpc        Microsoft Windows RPC
139/tcp   open  netbios-ssn  Microsoft Windows netbios-ssn
445/tcp   open  microsoft-ds Microsoft Windows 7 - 10 microsoft-ds (workgroup: WORKGROUP)
5357/tcp  open  http         Microsoft HTTPAPI httpd 2.0 (SSDP/UPnP)
49152/tcp open  msrpc        Microsoft Windows RPC
49153/tcp open  msrpc        Microsoft Windows RPC
49154/tcp open  msrpc        Microsoft Windows RPC
49155/tcp open  msrpc        Microsoft Windows RPC
49156/tcp open  msrpc        Microsoft Windows RPC
49160/tcp open  msrpc        Microsoft Windows RPC
MAC Address: 00:0C:29:AC:*:* (VMware)
Service Info: Host: WIN-PRO17IVTBGQ; OS: Windows; CPE: cpe:/o:microsoft:windows

