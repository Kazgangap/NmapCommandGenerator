# Nmap User Guide
### What is Nmap?
Nmap (Network Mapper) is a free and open source tool used for network discovery and security scanning. Nmap is used to determine the port status of target systems on the network, open services, operating system information, and other network information.
### Nmap Scan Types
TCP SYN scan (Stealth scan): nmap -sS example.com This command performs a TCP SYN scan on example.com and detects open ports.

TCP Connect scan: nmap -sT example.com This command establishes full TCP connections on example.com and detects open ports.

UDP scan: nmap -sU example.com This command performs a UDP scan on example.com and detects open UDP ports.

Operating system scan: nmap -A example.com This command performs an operating system scan on example.com and makes predictions about the running operating system.

Service version detection: nmap -sV example.com This command performs service version detection on example.com and tries to determine the versions of running services.

Scan with operating system prediction: nmap -O example.com This command performs an operating system scan on example.com and makes predictions while also performing service version detection.

XMAS scan: nmap -sX example.com This command runs an XMAS scan on example.com. It tries to detect open ports with XMAS packets.

Null scan: nmap -sN example.com This command performs a Null scan on example.com. It tries to detect open ports with Null packets.

ACK scan: nmap -sA example.com This command performs ACK scan on example.com. It tries to detect open ports by analysing ACK responses.

ICMP Echo scan: nmap -PE example.com This command performs an ICMP Echo scan on example.com. It checks the status of the target by analysing ICMP Echo responses.

### Destination Port Customisation
You can use the -p- command to scan all ports.

To scan a single port: nmap -p example.com For example, the command nmap -p 80 example.com will scan only port 80.

To scan a range of ports: nmap -p <start_port>-<end_port> example.com For example, the command nmap -p 1-100 example.com will scan all ports from 1 to 100.

To scan multiple ports separated by commas: nmap -p ,, example.com For example, the command nmap -p 80,443,8080 example.com will scan ports 80, 443 and 8080.

To exclude certain ports: nmap -p , --exclude-ports , example.com For example, the nmap -p 1-100 --exclude-ports 20,80 example.com command will scan ports 1 to 100 but exclude ports 20 and 80.

### Nmap Script Usage
To start a script scan, use the -sC or --script command. For example, you can start a script scan with the nmap -sC example.com command.

You can use the nmap --script-help all command to see a complete list of nmap scripts. This provides a list of available scripts and brief descriptions.

To run a specific script, specify the name of the script using the --script command. For example, you can run the ssl-enum-ciphers script with the nmap --script ssl-enum-ciphers example.com command.

To run more than one script, you can create a comma-separated list. For example, you can run script1 and script2 with the command nmap --script script1,script2 example.com.

Nmap can use the --script-category command to run a specific script category. For example, you can run scripts in the vulnerability detection category with the nmap --script-category vuln example.com command.

You can use the -oN or --output command to save the script output to a file. For example, the nmap --script script1 -oN output.txt example.com command will save the output of script1 to the output.txt file.

You can use the -p or --port command to specify script targets. For example, with the command nmap --script script1 -p 80 example.com you can run script1 only on port 80.

You can use the --script-args command to make script scanning faster. For example, you can specify the script arguments with the nmap --script script1 --script-args="arg1=value1,arg2=value2" example.com command.
