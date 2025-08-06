# web-server-hardening-detection
This project demonstrates how to secure an Apache web server using ModSecurity (WAF) and Fail2Ban, and how to detect and observe attacks such as directory brute-force and SQL injection attempts.

## Objectives

- Harden a Linux web server using ModSecurity and Fail2Ban.
- Simulate attacks from Kali Linux (e.g., Gobuster, SQLi).
- Observe and confirm detection through logs.
- Understand how WAFs and log-based defenses operate.

## 🖥Environment

- Ubuntu (Web Server)
- Kali Linux (Attacker)
- Apache 2.4
- ModSecurity (OWASP CRS)
- Fail2Ban

## Setup Instructions

See [`setup/`](./setup/) for detailed instructions on installing Apache, ModSecurity, and Fail2Ban.

## Simulated Attacks

See [`attacks/`](./attacks/) for details on attacks performed (Gobuster, SQLi via curl).

## Observations

See [`screenshots/`](./screenshots/) and [`logs/`](./logs/) for evidence of alerts and detections.
