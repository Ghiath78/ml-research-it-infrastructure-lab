# Backup Strategy

## 1. Objective

Design a reliable and scalable backup strategy
for a single-node Proxmox-based ML research infrastructure.

The strategy must address:

- Virtual machine backups
- Container backups
- Research data protection
- Disaster recovery
- Hardware failure scenarios

---

## 2. Infrastructure Constraints

- Single physical disk (1TB SSD)
- No RAID
- Limited RAM (4GB)
- Lab environment

Implication:
Backup design must compensate for lack of hardware redundancy.

---

## 3. Backup Philosophy

The backup architecture follows a multi-layer approach:

1. Hypervisor-level backups (vzdump)
2. File-level incremental backups (rsync)
3. Snapshot before critical system changes
4. Future external storage integration

---

## 4. Backup Layers

### Layer 1 – Proxmox-Level Backups

Tool: vzdump

Scope:
- LXC containers
- VMs

Storage Target:
- Dedicated backup directory (local storage)

Frequency:
- Weekly full backup
- Manual backup before major changes

---

### Layer 2 – File-Level Backups

Tool: rsync

Scope:
- Research data
- Configuration files
- Critical project data

Strategy:
- Incremental sync
- Versioned backups

---

### Layer 3 – Future External Backup

Planned:
- External HDD (500GB)
- Offline USB cold backup
- Periodic export of critical data

---

## 5. Restore Strategy

Backup without restore testing is invalid.

Restore scenarios:

- Restore single container
- Restore single file
- Full infrastructure rebuild from backup

---

## 6. Risk Assessment

Single Disk Failure:
- Total data loss

Mitigation:
- External backup (future)
- Regular export

Human Error:
- File deletion
- Misconfiguration

Mitigation:
- Incremental backups
- Snapshots

---

## 7. Professional Considerations

In production environment, this architecture would be extended with:

- RAID or ZFS mirror
- Off-site backup
- Automated backup verification
- Monitoring and alerting
