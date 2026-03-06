# Home Lab Infrastructure

A self-hosted home server built to gain hands-on experience with Linux 
systems administration, containerization, storage management, and secure networking.

## Hardware

| Component | Details |
|-----------|---------|
| OS Drive | 500GB SSD |
| Storage | 2x 4TB HDD in RAID1 (3.6TB usable) |
| Backup | 1TB HDD |
| RAM | 16GB |

## Architecture
```
Devices (PC / Phone)
        │
   Tailscale VPN
        │
   Ubuntu Server 24.04
        │
      Docker
        │
      Cosmos (Reverse Proxy)
        ├── Nextcloud (Personal Cloud Storage)
        ├── Immich (Photo Backup)
        ├── Uptime Kuma (Service Monitoring)
        └── Netdata (System Metrics)
```

## Services

| Service | Purpose | Status |
|---------|---------|--------|
| Nextcloud | Personal cloud storage | ✅ Running |
| Immich | Photo & video backup | ✅ Running |
| Uptime Kuma | Uptime monitoring + Discord alerts | ✅ Running |
| Netdata | Real-time system metrics | ✅ Running |

## Storage Layout

- `/` — 500GB SSD (OS + Docker)
- `/mnt/storage` — 3.6TB RAID1 (all application data)
- `/mnt/backup` — 1TB HDD (Restic automated backups)

## Security

- Remote access via Tailscale VPN (no exposed public ports)
- Network-wide DNS filtering via AdGuard Home
- Automated offsite-style backups with Restic

## Lessons Learned

- Diagnosed Cosmos reverse proxy failures caused by host-network mode 
  preventing Docker hostname resolution
- Resolved Redis authentication mismatches between containers after 
  network sandbox corruption
- Learned the importance of separating OS storage from application data
- Understood security implications of exposing Docker sockets vs 
  using a socket proxy

## Planned Additions

- [ ] IoT air quality monitoring (SCD41 + PM2.5 sensor on Raspberry Pi)
- [ ] Grafana + InfluxDB dashboards for sensor data
- [ ] Home Assistant integration
- [ ] Vaultwarden password manager
