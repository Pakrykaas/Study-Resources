Links for documentation:

PDF: https://drive.google.com/file/d/1-Ty5qSaB-pdnxa-BOqv2nIX1gYUNEFsB/view?usp=sharing

DOCX: https://drive.google.com/file/d/1TU1uXOZgNEW4FKBrjxkgORnacwMU2Lik/view?usp=sharing

# Cybersecurity Incident Report - Network Traffic Analysis

## Network Traffic Analysis - WireShark

### Part 1: 

**Identify the type of attack that may have caused this network interruption**

It is possible to identify the IP 192.0.2.1 as the source of the attack, this it is the only IP which constantly sends SYN requests to the server, even after the connection failure. 
The attack posed is a DoS (Denial of Service), the source IP was always the one described above. 
Do not misunderstand with DDoS (Distributed Denial of Service) this is the exact same outcome, the difference resides in the fact that the user used multiple machines (bots, most often) with different 
IP addresses to undertake the action.

### Part 2: 

**Explain how the attack is causing the website to malfunction**

This attack success is due to the overloading the RAM of the server with unanswered SYN requests. 
After the connection is established with a client, the same machine keeps sending connection requests to the server. This cannot be answered due to the fact of the connection being already established. 
An online connection between two parties using the internet, relies on the TCP protocol 3 Way Handshake. 
This handshake is used to determine if the connection is possible and to exchange encryption keys when available by the layer 7 protocol (as an example HTTPS). 
The 3 Way Handshake is made of (SYN, SYN ACK, ACK). When this 3 steps have been fulfilled the connection is established and the data exchange starts. 
What happened in this particular case was the continuation of connection requests after the third stage of the handshake. 
Each request is made of packets (pieces of data) which contain a certain size expressed in bytes. 
If the server is not able to give answer to this requests the packets will be saved in its RAM awaiting the chance to answer the request, if the RAM gets totally filled with packets (data) the machine 
stops performing, due to the fact of not having space to run its own processes.
