# GlobalTech Adversary Simulation Project

This project simulates a **realistic multi-phase cyber attack** on a fictional enterprise network using industry-standard tools and techniques. It showcases end-to-end penetration testing workflows — from initial access to data exfiltration — conducted in a controlled lab environment.

---

## Project Overview

**Objective:** Simulate a full kill-chain attack on a Linux-based enterprise network to demonstrate offensive security techniques, persistence, lateral movement and data exfiltration.

**Environment:**
- Attacker: Kali Linux
- Victim: Ubuntu Linux (Simulated enterprise host)

---

## Phases of the Simulation

### Phase 1: Initial Access
- Reconnaissance using `nmap`, `enum4linux`
- Exploited misconfigured services to gain initial foothold

### Phase 2: Exploitation
- Generated a Linux reverse shell payload using `msfvenom`
- Executed payload via USB transfer
- Established Meterpreter session using Metasploit handler

### Phase 3: Persistence
- Configured persistence via:
  - **Cron jobs** (execute every 10 seconds post-reboot)
  - **Systemd service creation** (for stealth)
- Maintained access after system reboot

### Phase 4: Lateral Movement
- Discovered other hosts using Nmap subnet scanning
- Identified SSH open ports
- Performed brute-force SSH login using Metasploit’s `ssh_login` module
- Gained shell access via weak credentials (`admin:admin`)
- Escalated privileges using `sudo`

### Phase 5: Data Exfiltration
- Located sensitive HR data on victim machine
- Encrypted files using custom Python AES script (`cryptography` library)
- Exfiltrated encrypted files using `scp`
- Decrypted files on attacker machine

---

## Tools & Techniques

| Tool            | Purpose                        |
|-----------------|--------------------------------|
| Metasploit      | Exploitation & persistence     |
| Msfvenom        | Payload generation             |
| Nmap            | Network scanning               |
| SSH / Brute-Force | Lateral movement            |
| Cron / Systemd  | Persistence techniques         |
| Python (cryptography) | Data encryption       |
| SCP             | Secure file transfer           |

---

## Key Takeaways

- **Persistence is critical**: Cron jobs and systemd services ensure long-term access.
- **Weak credentials are dangerous**: Lateral movement via SSH highlights the need for strong password policies.
- **Data must be protected at rest and in motion**: Encryption before exfiltration bypasses basic DLP.
- **Detection is possible**: With log monitoring, FIM, and traffic analysis (e.g., `Wireshark`, `Tripwire`).

---

## Disclaimer

This project was conducted in a **controlled environment** for **educational and ethical purposes only**. No real systems were harmed or accessed.

---

## Author

**Rachael Kivuti**  

Offensive Security Enthusiast | Red Teaming 

[LinkedIn](#https://www.linkedin.com/in/rachael-kivuti-575056226/) • [Medium](#https://medium.com/@kivutingatha) • 

---

## Full Report

The complete PDF report includes:
- Screenshots of each phase
- Technical details of payloads and modules
- Python scripts used for encryption



