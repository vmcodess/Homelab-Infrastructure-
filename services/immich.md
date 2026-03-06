# Immich

**Purpose:** Self-hosted photo and video backup (Google Photos alternative)

**Stack:**
- Immich Server
- Immich Machine Learning (facial recognition, object detection)
- PostgreSQL (database)
- Redis (caching)
- Cosmos (reverse proxy)

**Data location:** `/mnt/storage/photos` (RAID1)

**Access:** `http://100.78.x.x:PORT` via Tailscale

## Notes
- Machine learning container handles automatic facial recognition and 
  object tagging for searchable photo library
- PostgreSQL database backed up automatically via postgres-backup-local container
