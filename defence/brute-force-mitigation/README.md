# Brute Force Mitigation

This section demonstrates defensive measures implemented to mitigate brute-force authentication attacks.

## Techniques Implemented
- Rate limiting via iptables
- IP-based blocking after repeated failed login attempts
- Service hardening through non-default ports

## Example iptables Rule

```bash
iptables -A INPUT -p tcp --dport 22 -m recent --seconds 60 --hitcount 4 -j DROP
```

## Outcome

- Automated brute-force login attempts were successfully blocked after exceeding defined thresholds
- The SSH service remained operational while the attacker’s IP address was denied access
- Network-layer enforcement prevented further authentication attempts without impacting legitimate services

## Evidence

### Brute-force attack attempt (pre-mitigation)
Automated SSH brute-force attack executed using Medusa before any defensive controls were applied.

<img width="729" height="311" alt="image" src="https://github.com/user-attachments/assets/c9b6c0d2-653d-4dd1-a5ac-1b7f7803011b" />

---

### Firewall rate-limiting rule applied
iptables rule configured to detect and block repeated SSH login attempts within a defined time window.

<img width="733" height="67" alt="image" src="https://github.com/user-attachments/assets/c6e410d8-429e-4c9f-84eb-625f5eecbd2b" />
---

### Firewall rule verification
Verification of active firewall rules confirming SSH rate-limiting and DROP actions are enforced.

<img width="720" height="296" alt="image" src="https://github.com/user-attachments/assets/105ec164-8def-4817-83dc-f75cfd900eca" />

---

### Brute-force attack blocked (post-mitigation)
Medusa unable to establish SSH connections after exceeding the rate limit threshold.

<img width="836" height="325" alt="image" src="https://github.com/user-attachments/assets/23c90a3c-881b-41f5-b809-c3dcd680b81c" />

---

### Manual SSH attempt from blocked attacker IP
Manual SSH connection hangs, confirming the SSH service remains operational while the attacker IP is denied access.

<img width="762" height="68" alt="image" src="https://github.com/user-attachments/assets/1859e428-1e4e-467c-bb92-6f9a00468220" />







