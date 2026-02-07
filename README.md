# Authentication Security: Brute Force and Session Fixation Defences

This project demonstrates defensive security controls against authentication and session management vulnerabilities identified in OWASP A7.

The focus of this repository is on detecting, mitigating, and hardening systems against brute-force attacks and session fixation in web environments.

## My Role
- Designed and implemented brute-force mitigation controls
- Configured iptables firewall rules for rate limiting
- Hardened authentication workflows
- Implemented session ID regeneration to prevent session fixation
- Verified defences using Burp Suite

## Threats Addressed
- Brute-force authentication attacks
- Weak account lockout policies
- Static session identifiers
- Session hijacking and fixation

## Technologies Used
- Kali Linux
- iptables
- Apache2
- Burp Suite
- DVWA

## Project Structure
- `/defence` — Defensive implementations and explanations
- `/screenshots` — Evidence of mitigations
- `/report` — Final project report (PDF)

## Disclaimer
This project was conducted in a controlled lab environment for educational purposes only.
