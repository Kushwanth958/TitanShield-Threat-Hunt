# TitanShield Threat Hunt Investigation

## Overview
A hands-on threat hunting investigation conducted against the 
TitanShield enterprise security dataset using KQL in Azure 
Data Explorer. The goal was to identify active threats, 
compromised accounts, and attack patterns across multiple 
log sources.

## Investigation Summary

| # | Investigation | Key Finding |
|---|--------------|-------------|
| 1 | Authentication Analysis | 10,146 failed logins (54% of all events) |
| 2 | Targeted Accounts | nihartzog hit 50 times by external attackers |
| 3 | High Severity Alerts | 111 machines compromised, BRQZ-DESKTOP worst |
| 4 | Coordinated Attack | olmartinez1 hit by phishing + brute force same day |
| 5 | Attack Timing | Peak attacks at 2PM — deliberately during business hours |

## Repository Structure
