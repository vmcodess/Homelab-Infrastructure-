# Homelab Infrastructure Project

This project documents the design and deployment of a self-hosted infrastructure environment built to gain hands-on experience with Linux systems, containerization, storage management, and secure networking.

## Technologies

- Ubuntu Server
- Docker
- RAID (mdadm)
- Cosmos
- Immich
- Tailscale
- Uptime Kuma

## Architecture

Laptop / Phone

        ↓
        
   Tailscale VPN
        ↓
   Ubuntu Server
        ↓
      Docker
        ↓
      Cosmos
   ├── Immich (Photo backup)
   └── Uptime Kuma (Monitoring)

## Storage

500GB SSD
→ OS

RAID1 (2×4TB)
→ Application storage
→ Photo uploads

1TB HDD
→ Database backups
