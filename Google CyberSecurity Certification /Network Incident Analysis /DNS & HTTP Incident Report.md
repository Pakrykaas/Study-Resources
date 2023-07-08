Links for documentation:

PDF: https://drive.google.com/file/d/1abFyzZeZWmNiq9WVeKkNZ7YcUWtwA1Qu/view?usp=sharing

DOCX: https://drive.google.com/file/d/1GR2ImjoIS42YIDXXfZQX8DdoJf-rEt8F/view?usp=sharing

# Cybersecurity incident report

## DNS and HTTP Log File

> **14:18:32.192571** IP your.machine.52444 > dns.google.domain: 35084+ A? yummyrecipesforme.com. (24)

> **14:18:32.204388** IP dns.google.domain > your.machine.52444: 35084 1/0/0 A 203.0.113.22 (40)

> **14:18:36.786501** IP your.machine.36086 > yummyrecipesforme.com.http: Flags [S], seq 2873951608, win 65495, options [mss 65495,sackOK,TS val 3302576859 ecr 0,nop,wscale 7], length 0

> **14:18:36.786517** IP yummyrecipesforme.com.http > your.machine.36086: Flags [S.], seq 3984334959, ack 2873951609, win 65483, options [mss 65495,sackOK,TS val 3302576859 ecr 3302576859,nop,wscale 7],
> length 0

> **14:18:36.786529** IP your.machine.36086 > yummyrecipesforme.com.http: Flags [.], ack 1, win 512, options [nop,nop,TS val 3302576859 ecr 3302576859], length 0

> **14:18:36.786589** IP your.machine.36086 > yummyrecipesforme.com.http: Flags [P.], seq 1:74, ack 1, win 512, options [nop,nop,TS val 3302576859 ecr 3302576859], length 73: HTTP: GET / HTTP/1.1

> **14:18:36.786595** IP yummyrecipesforme.com.http > your.machine.36086: Flags [.], ack 74, win 512, options [nop,nop,TS val 3302576859 ecr 3302576859], length 0
> ...<a lot of traffic on the port 80>...

> **14:20:32.192571** IP your.machine.52444 > dns.google.domain: 21899+ A? greatrecipesforme.com. (24)

> **14:20:32.204388** IP dns.google.domain > your.machine.52444: 21899 1/0/0 A 192.0.2.17 (40)

> **14:25:29.576493** IP your.machine.56378 > greatrecipesforme.com.http: Flags [S], seq 1020702883, win 65495, options [mss 65495,sackOK,TS val 3302989649 ecr 0,nop,wscale 7], length 0

> **14:25:29.576510** IP greatrecipesforme.com.http > your.machine.56378: Flags [S.], seq 1993648018, ack 1020702884, win 65483, options [mss 65495,sackOK,TS val 3302989649 ecr 3302989649,nop,wscale 7], length 0

> **14:25:29.576524** IP your.machine.56378 > greatrecipesforme.com.http: Flags [.], ack 1, win 512, options [nop,nop,TS val 3302989649 ecr 3302989649], length 0

> **14:25:29.576590** IP your.machine.56378 > greatrecipesforme.com.http: Flags [P.], seq 1:74, ack 1, win 512, options [nop,nop,TS val 3302989649 ecr 3302989649], length 73: HTTP: GET / HTTP/1.1

> **14:25:29.576597** IP greatrecipesforme.com.http > your.machine.56378: Flags [.], ack 74, win 512, options [nop,nop,TS val 3302989649 ecr 3302989649], length 0 ...<a lot of traffic on the port 80>...

### Part 1: 

**Identify the network protocol involved in the incident**

In this scenario, the network protocols used were DNS (in order to discover the IP address of the site **yummrecipesforme.com**, on port **52444**) as well as HTTP (in order to display/transfer the 
HTML document, on port **36086**)

### Part 2: 

**Document the incident**

At *14:18:32.192571* the request for yumrecipesforme.com IP address started, being the answer provided to the client's machine. 

From here a connection was established and the client managed to access the website. 

At *14:18:36.786589* a GET request was made. 

At *14:18:36.786595* the connection comment presented *“...<a lot of traffic on the port 80>...”* 

At *14:20:32.192571* a new request from the client machine to the DNS server was established, being the answer - **greatrecipesforme.com**. 

It's possible to see that, after high traffic in port 80 the connection was changed to a different site. 

### Part 3: 

**Recommend one remediation for brute force attacks**

The main solution for this type of attack is blocking the capacity to interact with the systems after a certain number of failed attempts. This can be either total deactivation/block of a certain IP, 
or, by the usage of clipping levels, after a certain number of failed attempts there is a period of inactivity till the system accepts new password attempts.


