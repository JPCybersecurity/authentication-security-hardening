# Brute Force Mitigation

This section demonstrates defensive measures implemented to mitigate brute-force authentication attacks.

## Techniques Implemented
- Rate limiting via iptables
- IP-based blocking after repeated failed login attempts
- Service hardening through non-default ports

## Example iptables Rule

```bash
iptables -A INPUT -p tcp --dport 22 -m recent --seconds 60 --hitcount 4 -j DROP

## Outcome

- Automated brute-force login attempts were successfully blocked after exceeding defined thresholds
- The SSH service remained operational while the attacker’s IP address was denied access
- Network-layer enforcement prevented further authentication attempts without impacting legitimate services

## Evidence

- Firewall logs indicating dropped packets after repeated login attempts
- SSH connection attempts hanging from the attacker machine
- Verification performed from an external attack host

See screenshots in the `/screenshots` directory.





