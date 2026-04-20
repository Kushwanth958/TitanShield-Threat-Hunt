
# TitanShield Threat Hunt Report

**Analyst:** Kushwanth Avutapalli  
**Date:** April 2026  
**Tools:** Azure Data Explorer, KQL, TitanShield Dataset

---

## Executive Summary

A comprehensive threat hunt was conducted against TitanShield's 
security dataset using KQL across multiple log sources including 
authentication events, security alerts, and network flows. 
The investigation identified sustained brute force activity, 
confirmed account breaches, compromised endpoints, and a 
coordinated targeted attack against a specific user. 
Immediate remediation is recommended.

---

## Findings

### Finding 1 — Authentication Overview
TitanShield experienced 18,936 total authentication events. 
54% were failed logins (10,146), indicating sustained brute 
force and credential stuffing activity across the environment.

### Finding 2 — Most Targeted Accounts
Five accounts were heavily targeted by external attackers. 
nihartzog led with 50 external login attempts, followed by 
aucampbell (47), mihill (45), waallen (44), and jadouglas (42). 
These accounts require immediate password resets and MFA enforcement.

### Finding 3 — Compromised Machines
111 unique machines triggered high severity security alerts. 
BRQZ-DESKTOP, E49P-MACHINE, and HNQF-LAPTOP were the most 
affected with 3 alerts each, indicating possible malware 
infection or active compromise.

### Finding 4 — Coordinated Targeted Attack
User olmartinez1 was simultaneously targeted by a phishing 
email and brute force login attempts on July 29, 2024. 
This coordinated attack pattern indicates a targeted threat 
actor focusing on this specific account across multiple 
attack vectors simultaneously.

### Finding 5 — Attack Timing Pattern
External attack attempts peak at 2PM (623 attempts) and 1PM 
(616 attempts), suggesting attackers deliberately target 
business hours to blend in with legitimate traffic and 
evade after-hours detection rules.

---

## Recommendations

- **Enforce MFA immediately** on the top 5 targeted accounts 
  (nihartzog, aucampbell, mihill, waallen, jadouglas) and 
  reset all passwords.
- **Isolate and reimage** BRQZ-DESKTOP, E49P-MACHINE, and 
  HNQF-LAPTOP for forensic investigation and malware removal.
- **Deploy business-hours detection rules** that flag unusual 
  spikes in failed logins between 12PM-3PM from external IPs, 
  and immediately investigate olmartinez1's account for 
  signs of compromise.

---

## Tools Used
- Azure Data Explorer
- KQL (Kusto Query Language)
- TitanShield Cybersecurity Dataset
