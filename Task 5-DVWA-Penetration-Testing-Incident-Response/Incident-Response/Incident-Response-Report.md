# Incident Response Report

## Incident Title

Simulated SQL Injection Detection and Response in DVWA

## Incident Type

Web Application Security Incident

## Environment

- Application: DVWA
- Host: Kali Linux
- Target: `127.0.0.1`
- Web Server: Apache
- Database: MariaDB
- Testing Environment: Controlled Local Laboratory

## Incident Description

A simulated SQL Injection request was performed against the DVWA SQL Injection module.

The request was subsequently identified in the Apache access log during incident analysis.

The purpose of this exercise was to demonstrate detection, evidence collection, containment, remediation and recovery.

## 1. Detection

Apache access logs were searched for suspicious SQL-related patterns.

Example command:

```bash
sudo grep -iE "OR|UNION|SELECT|%27|%3D" /var/log/apache2/access.log | tail -n 20

The analysis identified a suspicious request containing an SQL Injection pattern.

Example encoded request component:

id=1%27+OR+%271%27%3D%271
2. Evidence Collection

The relevant log information was preserved for incident documentation.

Evidence file:

task5_sqli_incident.log

The preserved log provides evidence of the suspicious HTTP request detected during the incident analysis.

3. Containment

The affected SQL Injection module was isolated as a containment measure.

The purpose was to prevent continued access to the affected component during remediation.

4. Eradication and Remediation

The vulnerable implementation was replaced with the secure implementation from the previously preserved backup.

The secure implementation uses prepared statements.

Verification was performed using:

sudo grep -n "mysqli_prepare" /var/www/html/DVWA/vulnerabilities/sqli/source/low.php

The presence of mysqli_prepare confirmed the prepared-statement implementation.

5. Recovery

After remediation, the application was restored and checked to confirm that the environment was functioning normally.

6. Lessons Learned

The exercise demonstrated the importance of:

Monitoring web-server access logs.
Recognizing suspicious request patterns.
Preserving incident evidence.
Isolating affected components.
Using secure coding practices.
Verifying remediation after an incident.
Maintaining an incident-response procedure.
7. Recommended Mitigation
SQL Injection

Use prepared statements and parameterized queries instead of directly constructing SQL queries from user input.

Logging and Monitoring

Monitor Apache and application logs for suspicious requests and unusual input patterns.

Input Validation

Validate and constrain user input according to the expected data type and format.

Secure Development

Perform regular security testing and code reviews to identify vulnerabilities before deployment.

Incident Response Lifecycle
Detection
    ↓
Evidence Collection
    ↓
Containment
    ↓
Eradication / Remediation
    ↓
Recovery
    ↓
Lessons Learned
Conclusion

The simulated SQL Injection incident was successfully detected through Apache log analysis. Relevant evidence was preserved, the affected component was contained, the secure implementation was restored, and recovery was verified.

This exercise demonstrates how vulnerability assessment findings can be integrated with an incident-response process.