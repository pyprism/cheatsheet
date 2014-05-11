##Chapter 1 ~::~ Nmap Fundamentals
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
#Chapter 2 ~::~ Network Exploration
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
##Chapter 3 ~::~ Gathering Additional Host Information
####Getting information from WHOIS records
```
nmap --script whois <target>
```
####Collecting valid e-mail accounts
The script http-google-email is not included in Nmap's official repository. So you
need to download it from http://seclists.org/nmap-dev/2011/q3/att-401/
http-google-email.nse and copy it to your local scripts directory. After copying
http-google-email.nse , you should update the script database with:
```
nmap --script-updatedb
```
then
```
nmap -p80 --script http-google-email,http-email-harvest <target>
```
####Discovering hostnames pointing to the same IP address
https://secwiki.org/w/Nmap/
External_Script_Library .
```
nmap --script-updatedb
nmap -p80 --script hostmap nmap.org
```
####Brute forcing DNS records
```
nmap --script dns-brute <target>
```
####Fingerprinting the operating system of a host
```
nmap -O <target>
```
####Discovering UDP services
```
nmap -sU -p- <target>
```
####Listing protocols supported by a remote host
```
nmap -sO <target>
```
####Discovering stateful firewalls by using a TCP ACK scan
```
nmap -sA <target>
```
#####Port states
Nmap categorizes ports using the following states:
> Open : Indicates that an application is listening for connections on this port.
> Closed : Indicates that the probes were received but there is no application listening on this port.
> Filtered : Indicates that the probes were not received and the state could not be established. It also indicates that the probes are being dropped by some kind of filtering.
> Unfiltered : Indicates that the probes were received but a state could not be established.
> Open/Filtered : Indicates that Nmap couldn't determine if the port is filtered or open.
> Closed/Filtered : Indicates that Nmap couldn't determine if the port is filtered
or closed.
##Chapter 4 ~::~ Auditing Web Servers
##Chapter 5 ~::~ Auditing Databases






















