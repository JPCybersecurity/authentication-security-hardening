# Brute Force Mitigation

This section demonstrates defensive measures implemented to mitigate brute-force authentication attacks.

## Techniques Implemented
- Rate limiting via iptables
- IP-based blocking after repeated failed login attempts
- Service hardening through non-default ports

## Example iptables Rule

```bash
iptables -A INPUT -p tcp --dport 22 -m recent --seconds 60 --hitcount 4 -j DROP

