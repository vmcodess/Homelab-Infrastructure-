# Nextcloud

**Purpose:** Personal cloud storage (self-hosted Google Drive alternative)

**Stack:**
- Nextcloud (app)
- MariaDB (database)
- Redis (caching)
- Cosmos (reverse proxy)

**Data location:** `/mnt/storage/nextcloud-data` (RAID1)

**Access:** `http://100.x.x.x:PORT` via Tailscale

## Issues Encountered
- Reverse proxy couldn't resolve Docker hostnames due to host-network mode
- Fixed by exposing container port directly to host and updating proxy target
