# FUTURE_CS_01 – Vulnerability Assessment Report
**Author:** BONIVENTURE YOHANA SALUMU

**CIN ID:** FIT/APR26/CS8088

**Date:** June 2026

**Task:** Vulnerability Assessment Report for a Live Website (Read-Only Scope)

## Project Overview

This repository contains the deliverables for Cyber Security Task 1 assigned by Future Interns.

The task involved performing a read-only vulnerability assessment on a publicly available practice website in order to identify common security weaknesses and document them in a professional report format.

The assessment was conducted using passive reconnaissance techniques, meaning no exploitation or intrusive attacks were performed.

Target Website Application: Inlane Freight
Host Address: inlanefreight.com
Purpose: Transportation services


## Tools Used

1. Nmap

Used for basic port scanning and service detection.

Example command used:
nmap -sV -sV inlanefreight.com -Pn -T4 -oN nmap.txt

Purpose:
- Identify open ports
- Detect running services
- Gather service version information

2. WhatWeb

Used to detect the technology stack and server configuration of the target website.

Example command:
whatweb http:s://www.inlanefreight.com

##### Output
```
https://www.inlanefreight.com [200 OK]
Apache[2.4.41],
Bootstrap[5.6.17],
Country[UNITED STATES][US],
Email[info@inlanefreight.com, info@themeansar.com],
HTML5,
HTTPServer[Ubuntu Linux][Apache/2.4.41 (Ubuntu)],
IP[134.209.24.248],
JQuery[3.5.1],
MetaGenerator[WordPress 5.6.17],
Script[text/javascript],
Title[Inlanefreight – Protected by Wordfence],
UncommonHeaders[link],
WordPress[5.6.17]
```


Detected technologies:
- Apache server 2.4.41
- WordPress[5.6.17]
- Bootstrap[5.6.17]
- JQuery[3.5.1]

Evidence saved as:
Task_01_Vulnerability_Assessment_Report/reconnaissance/whatweb.txt
Task_01_Vulnerability_Assessment_Report/reconnaissance/whatweb.png
Task_01_Vulnerability_Assessment_Report/reconnaissance/nmap.txt
Task_01_Vulnerability_Assessment_Report/reconnaissance/nmap.png

3. Curl (Security Headers Analysis)

Used to analyze HTTP security headers of the web application.

Key results identified missing security headers such as:
- Content-Security-Policy
- X-Frame-Options
- X-Content-Type-Options
- Referrer-Policy

The scan also detected:
- Website served over HTTP
- Server information disclosure


## Deliverables Included

- Vulnerability_Assessment_Report.pdf
- README.md

Evidence folder contains:
- whatweb.txt
- whatweb.png
- Screenshots of scan outputs

These files document the findings gathered during the assessment.


## Key Findings Summary

Missing Security Headers

Several recommended HTTP security headers were not configured:
- Content-Security-Policy
- X-Frame-Options
- X-Content-Type-Options
- Referrer-Policy

These headers help protect websites against:
- Cross-Site Scripting (XSS)
- Clickjacking attacks
- MIME-type sniffing
- Information leakage

Server Information Disclosure

The server exposes detailed version information:
- Server: Apache/2.4.25 (Debian)
-  WordPress[5.6.17]

Open Ports Discovered
Nmap scan revealed:
- Port 80 (HTTP) - Apache 2.4.41
- port 443 (HTTPS) - Apache httpd 2.4.41

## Overall Risk Level

Low – High

The vulnerabilities discovered mainly involve misconfigurations and information disclosure, which could assist attackers during reconnaissance phases.


## Scope and Methodology

Allowed activities:
- Passive reconnaissance
- Header inspection
- Technology fingerprinting
- Service identification

Not performed:
- Exploitation
- SQL Injection testing
- Brute force attacks
- Directory brute forcing
- Denial-of-Service attacks

All testing was conducted in read-only mode nothing exploited , respecting ethical guidelines.


## References

- OWASP Web Security Testing Guide
- Sample vulnerability reports from GitHub (as suggested in the task)
