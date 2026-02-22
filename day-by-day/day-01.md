# Day 01 – Management Node Initialization

## Objective

Establish a secure and structured management node inside Proxmox
as the operational control center of the infrastructure.

---

## Actions Performed

- Created unprivileged LXC container (Debian 12)
- Assigned 1 CPU core, 512MB RAM
- Configured network via DHCP
- Created non-root administrative user
- Installed minimal core toolset (vim, git, curl)
- Generated SSH key (ed25519)
- Configured SSH agent with passphrase support
- Established secure GitHub authentication

---

## Security Measures

- Privilege separation (no daily root usage)
- SSH-based authentication
- Passphrase-protected private key
- Host-based Git identity

---

## Core Competencies Covered

### Security Concept
- Secure SSH authentication model
- Proper privilege separation

### Linux Troubleshooting
- SSH key validation
- Debugging publickey authentication issues

---

## Engineering Reflection

The management node is designed as a controlled operational layer.
All future infrastructure changes will be executed from this node.

This ensures consistency, traceability and professional workflow discipline.
