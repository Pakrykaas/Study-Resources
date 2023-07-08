Links for documentation:

PDF: https://drive.google.com/file/d/1-Ty5qSaB-pdnxa-BOqv2nIX1gYUNEFsB/view?usp=sharing

DOCX: https://drive.google.com/file/d/1dC9x26Bk05_t47bzeZFc4cHLiUNtWKVE/view?usp=sharing

# Cybersecurity Incident Report

## DNS and ICMP Log File

>13:24:32.192571 IP 192.51.100.15.52444 > 203.0.113.2.domain: 35084+ A?
yummyrecipesforme.com. (24)
>13:24:36.098564 IP 203.0.113.2 > 192.51.100.15: ICMP 203.0.113.2
udp port 53 unreachable length 254

>13:26:32.192571 IP 192.51.100.15.52444 > 203.0.113.2.domain: 35084+ A?
yummyrecipesforme.com. (24)
>13:27:15.934126 IP 203.0.113.2 > 192.51.100.15: ICMP 203.0.113.2
udp port 53 unreachable length 320

>13:28:32.192571 IP 192.51.100.15.52444 > 203.0.113.2.domain: 35084+ A?
yummyrecipesforme.com. (24)
>13:28:50.022967 IP 203.0.113.2 > 192.51.100.15: ICMP 203.0.113.2
udp port 53 unreachable length 150

## Network Traffic Analysis - DNS and ICMP

### Part 1: 

**Providing a summary of the problem found in the DNS and ICMP
traffic log**

At 13:24:32.192571 a connection attempt was generated from the company’s private IP 192.51.100.15 to the DNS server 203.0.113.2, in order to locate the IP
address for the site yummyrecipesforme.com.

The answer from the DNS server, in the form of an ICMP packet did not reach
the IP 192.51.100.15 due to UDP port 53 having the DNS server being unreachable, being the hour registry 13:24:36.098564 for the first event.

At 13:26:32.192571 and 13:28:32.192571 hours the same action was taken, with no different results identified.

### Part 2:

**Explain your analysis of the data and provide one solution to implement**

After analyzing the present data 3 options seem valid.

- First, it is possible that at the moment of yummyrecipesforme.com IP request the DNS server was down due to layer 1 issues, not presenting a direct risk to the organization. 

- Second there is a chance of a high number of requests from different clients in the same moment, which can indicate a layer 3 attack (ICMP Flood) presenting this as a direct risk for the organization’s
normal functioning.

- Third, our machine in the IP 192.51.100.15 is being used as a bot as the firewall in the DNS server blocked all the traffic originating from it in port 53, and possibly other ports.
