# Task 1: Network Port Scanning

## Objective
To scan the local network and identify open ports using Nmap.

## Tools Used
- Kali Linux
- Nmap

## Network Information
IP Address: 10.116.114.94
Network Range: 10.116.114.0/24

## Commands Used
1. nmap --version
2. ip a
3. sudo nmap -sS 10.116.114.0/24
4. sudo nmap -sS 10.116.114.0/24 -oN scan_result.txt

## Results
- Multiple devices found in network
- Open ports detected like 80 (HTTP), 443 (HTTPS), 22 (SSH)

## Security Risks
- Open ports can allow unauthorized access
- SSH may be vulnerable to brute force attacks
- HTTP traffic is not encrypted

## Conclusion
Network scanning helps identify exposed services and improve security.
