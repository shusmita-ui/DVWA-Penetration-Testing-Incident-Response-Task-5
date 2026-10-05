# Web Application Penetration Testing and Incident Response Using DVWA

## Project Overview

This project demonstrates a controlled web application security assessment and incident response exercise using Damn Vulnerable Web Application (DVWA).

The project combines vulnerability assessment and penetration testing activities with a simulated incident-response workflow. The testing was performed in a controlled local laboratory environment using Kali Linux, Apache, MariaDB and DVWA.

## Objectives

- Identify and analyze common web application vulnerabilities.
- Perform reconnaissance and service identification.
- Document security testing results with evidence.
- Detect a simulated SQL Injection attempt from web-server logs.
- Preserve relevant incident evidence.
- Perform containment and remediation.
- Verify recovery of the application.
- Recommend appropriate security mitigations.

## Scope

The assessment was restricted to the local DVWA laboratory environment.

- Target: DVWA
- Target Address: `127.0.0.1`
- Operating System: Kali Linux
- Web Server: Apache
- Database: MariaDB
- Testing Type: Controlled local laboratory testing

No external or unauthorized systems were targeted.

## Tools Used

- Kali Linux
- Nmap
- DVWA
- Apache
- MariaDB
- Burp Suite
- Web Browser
- Linux command-line tools

## Security Testing Areas

The project includes assessment and documentation of:

- SQL Injection
- Cross-Site Scripting (XSS)
- Cross-Site Request Forgery (CSRF)
- Local/Remote File Inclusion (LFI/RFI)
- Web application reconnaissance
- HTTP request analysis using Burp Suite

## Incident Response

A simulated SQL Injection incident was analyzed through Apache access logs.

The incident-response workflow included:

1. Detection
2. Evidence Collection
3. Containment
4. Eradication / Remediation
5. Recovery
6. Lessons Learned

## Repository Structure

```text
DVWA-Penetration-Testing-Incident-Response/
│
├── README.md
├── Report/
├── Screenshots/
│   ├── Reconnaissance/
│   ├── Vulnerabilities/
│   ├── Burp/
│   └── Incident-Response/
├── Logs/
├── Incident-Response/
├── Methodology/
└── Diagrams/
Key Findings

The security assessment identified several common web application security weaknesses in the controlled DVWA environment.

The most important incident-response demonstration involved detection of a SQL Injection request through Apache access logs.

Mitigation Summary
Use prepared statements and parameterized queries against SQL Injection.
Apply input validation and output encoding against XSS.
Implement anti-CSRF tokens.
Restrict file inclusion and validate file paths.
Monitor web-server logs for suspicious requests.
Maintain secure coding practices and regular security testing.
Evidence

Screenshots, log evidence, methodology documentation and the final capstone report are included in this repository.

Final Report

The complete project documentation is available in:

Report/Capstone-Project-Report.pdf

Disclaimer

This project was conducted strictly for educational and authorized cybersecurity testing in a controlled local laboratory environment.