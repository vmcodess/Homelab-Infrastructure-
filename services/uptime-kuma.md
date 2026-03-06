# Uptime Kuma

**Purpose:** Service uptime monitoring with alerting

**Stack:**
- Uptime Kuma
- Docker socket proxy (secure Docker access)

**Access:** `http://100.78.x.x:PORT` via Tailscale

## Monitored Services
- Nextcloud
- Immich
- Netdata
- Cosmos

## Alerting
- Discord webhook notifications on service down and recovery
- 60 second heartbeat interval per service

## Notes
- Uses socket proxy instead of exposing Docker socket directly for improved security

### Discord Alert
![test?](screenshots/discord_alert.png)
