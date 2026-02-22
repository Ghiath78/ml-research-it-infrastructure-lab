# Security Baseline – Management Node

## Objective

Establish a hardened management node (mgmt-lab)
serving as the secure control plane of the infrastructure.

---

## 1. SSH Hardening

- Disabled password authentication
- Disabled root login
- Enforced key-based authentication
- Changed default SSH port from 22 to 2222
- Disabled systemd socket activation for SSH
- Verified active listening port

---

## 2. Firewall Configuration

Tool: UFW

Configuration:

- Default deny incoming
- Default allow outgoing
- Allow TCP 2222 only

Result:
Reduced exposed attack surface.

---

## 3. Privilege Separation

- Daily operations via non-root admin user
- Sudo usage controlled and logged
- No direct root SSH access

---

## 4. Update Policy

- System fully updated
- Unattended security upgrades enabled

---

## Security Philosophy

Defense in Depth:
- Network Layer: Firewall
- Access Layer: SSH key-based auth
- Service Layer: Port minimization
- Operational Layer: Privilege separation

---

## Result

The management node now operates under a hardened security baseline
suitable for infrastructure orchestration tasks.
