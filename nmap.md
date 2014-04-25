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






























