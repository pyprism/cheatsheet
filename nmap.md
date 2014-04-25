##Chapter 1
####Listing open ports on a remote host
```
nmap hiren.com
```
####Version detection
```
nmap -sV hiren.me
```
####Aggressive detection
```
nmap -sC -sV -O <target>
```
####Finding live hosts
```
nmap -sP 192.168.1.1/24
```
####Scanning using specific port ranges
```
nmap -p80 192.168.1.1/24
```
#####More
* Port list:
```
 nmap -p80,443 localhost
```
* Port range:
```
nmap -p1-100 localhost
```
* All ports:
```
nmap -p- localhost
```
* Specific ports by protocols:
```
nmap -pT:25,U:53 <target>
```
* Service name:
```
nmap -p smtp <target>
```
* Service name wildcards:
```
nmap -p smtp* <target>
```
* Only ports registered in Nmap services:
```
nmap -p[1-65535] <target>
```
####Scan using script
```
nmap --script <script name> <host>
```
####Scanning using a specified network interface
```
nmap -e <INTERFACE> scanme.nmap.org
```
#Chapter 2
####Discovering hosts with TCP SYN ping scans
```
nmap -sP -PS 192.168.1.1/24
```
####Discovering hosts with TCP ACK ping scans
```
nmap -sP -PA <target>
```
####Discovering hosts with UDP ping scans
```
nmap -sP -PU <target>
```
####Discovering hosts with ICMP ping scans
```
nmap -sP -PE hiren.net
```
####Discovering hosts with IP protocol ping scans
```
nmap -sP -PO <target>
```
####Discovering hosts with ARP ping scans
Effective for LAN network
```
nmap -sP -PR 192.168.1.1/24
```
####MAC address spoofing
Change your motherfking MAC adrs ~
```
nmap -sP -PR --spoof-mac 5C:4C:A9:F2:DC:7C
```
####Hiding our traffic with additional random data
Generate Random Data
```
nmap -sS -PS --data-length 300 scanme.nmap.org
```
####Forcing DNS resolution
Force DNS resulation even if host is offline :(
```
nmap -sS -PS -F -R XX.XXX.XXX.220-230
```

























