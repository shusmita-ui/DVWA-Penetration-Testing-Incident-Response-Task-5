# Methodology

## Overview

The project followed a structured web application security assessment and incident-response methodology.

## Phase 1: Reconnaissance

The local target was analyzed using Nmap to identify accessible services and obtain service/version information.

The primary target was:

`127.0.0.1`

The reconnaissance phase identified services including:

- HTTP / Apache
- MySQL/MariaDB

OS detection was also performed as part of the assessment.

## Phase 2: Vulnerability Assessment

DVWA was assessed for common web application vulnerabilities.

The documented areas included:

- SQL Injection
- Cross-Site Scripting (XSS)
- Cross-Site Request Forgery (CSRF)
- Local/Remote File Inclusion (LFI/RFI)

Existing evidence from the security-testing phase was incorporated into the capstone project.

## Phase 3: Web Request Analysis

Burp Suite was used during the security-testing phase to inspect and analyze HTTP requests and application behavior.

## Phase 4: Incident Detection

A simulated SQL Injection request was generated in the controlled DVWA environment.

Apache access logs were reviewed to identify suspicious request patterns.

Example indicators included encoded characters and SQL-related patterns such as:

`%27`

`%3D`

`OR`

`SELECT`

`UNION`

## Phase 5: Evidence Collection

The relevant Apache log entry was preserved as incident evidence.

The evidence was stored in:

`Logs/task5_sqli_incident.log`

## Phase 6: Containment

The affected SQL Injection module was isolated as a containment measure.

This prevented normal access to the affected component while the incident was being investigated and remediated.

## Phase 7: Remediation

The vulnerable implementation was replaced with the secure implementation using prepared statements.

The presence of `mysqli_prepare` was used to verify the secure implementation.

## Phase 8: Recovery

After remediation, the application environment was restored and verified.

## Phase 9: Mitigation

Security recommendations were documented for the identified vulnerabilities.

The recommendations focused on:

- Secure coding
- Input validation
- Parameterized queries
- Output encoding
- CSRF protection
- File-access restrictions
- Log monitoring