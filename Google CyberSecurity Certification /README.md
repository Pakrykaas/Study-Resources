# Google CyberSecurity Certification

This file contains valid resources for CyberSecurity Analysts, presenting templates which can be used set guidelines for assessment documentation development.

This **README** file will introduce you to expect to find. 

Each document will be writen in markdown adding links for PDF and Google Docx in the document description.

## List of resources

1. Risk Assessment;
2. Network Incident Analysis;
3. Network Hardenning Tools;
4. Linux Basics;
5. SQL Basics;

### Risk Assessment

#### Scope and Goals

A fictional company *Botium Toys* performs a Risk Assessment in order to understand its CyberSecurity posture. The first step in order to develop a successful assessment starts by outlining what can and 
can't be tested, in order to protect the organization, its members and costumers, followed by the objective of such action, in general, the development of *deliverables*, easy to understand documentation 
even for those with no technical skills (ex: management) aiming to collect support in order to apply changes.  

**Scope**

The scope is not constant from audit to audit, however, once it is clearly defined, only the items presented should be audited. 

In this scenario, the scope is defined as the entire security program at *Botium Toys*. This means all assets need to be assessed alongside internal processes and procedures.

**Goals**

Creation of outcomes aiming to achieve compliance, identify weaknesses and vulnerabilities within the organization, and understanding processes and procedures failure looking forward to correcting them.

#### Control Assessment

**(Tables still not available in markdown, please address to the links)**

This list helps creating a qualitative analysis of the actual controls we have, describing their **category**, **type**, **name**, and **purpose** in order to introduce individuals to the different tools used to assure safety and well being while also setting a checklist avoiding leaving any control out of the test.

#### Compliance Checklist

**(In order to access the interactive checklist please address to the links)**

Here is displayed a checklist with different laws and regulations, the goal is to understand which ones fit in this line of business and assessing if the organization is in compliance. A simple and effective way to test our legal posture.

#### Stakeholder Memorandum

A document addressing to the main organs of the organization who take part in setting applying and aproving changes.

Since many times these will be people with different backgrounds the languange used has to be direct and simple.

This document is divided in **4** parts:

- Scope;
- Goals;
- Critical Findings;
- Findings;

The **Scope** introduces the stakeholders and the dedicated team to what will be tested providing introduction to core concepts.

The **Goals** will present the porpuse of the assessment, in this case a general assessment testing the overall position of the company.

The **Critical Findings** list the controls which either are not present or need an urgent update or configuration in order to fullfil its porpuse. These must be adressed ASAP, their current posture poses a vulnerablity for the organization.

The **Findings** list complement the *Critical Findings* list. Its the leftover of the controls which need an improvement in order to fully address its tasks. These are non urgent changes needed. 

### Network Incident Analysis

#### DNS & ICMP Incident Report

A company recieves the information of its web page lack of reponse. In order to understand what is the issue a Security Analyst tries to connect to the website and analyses the log files  which result from this acction.

The ICMP request starts from the client machine, yet no answer is given by the web server. 

The analyst has to conduct an investigation as well as a detailed report.

#### Wireshark Incident Report

**(Log still not available in markdown, please address to the links)**

Starting on the last fase of the last action, the analyst will now verify log documentation of all the movement caught on WireShark in order to unsderstand exactly what type of actions are being taken by third parties towards this server.

There is not yet a step by step explanation on how to analyse such log.

#### DNS & HTTP Incident Report

A disgrunted employee manages to access the website of its previous ex employeer and redirects all the clients traffic to a malicious web site which downloads all the payed products on its ex employeer's website.

The Security Analyst's duty in this case is to understand the whole process taken by the threat actor, analysing all the data in a sandbox in order to create countermesaures to stop this and avoid future attacks.
