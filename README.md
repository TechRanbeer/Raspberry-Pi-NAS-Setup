# Raspberry Pi NAS Setup with CasaOS

This project sets up a self-hosted NAS on Raspberry Pi 5 (4GB RAM) using:
- **CasaOS** for GUI and container management
- **Docker** for services like Nextcloud and Portainer
- **Tailscale** for secure remote access
- **Firewall** hardening
- **External SSD** mounting
- **Auto-updates** with Watchtower

## Included Services

| Service     | Description                                | Port |
|-------------|--------------------------------------------|------|
| CasaOS      | GUI Dashboard                              | 80   |
| Nextcloud   | Private cloud storage                      | 10443|
| Portainer   | Docker GUI Manager                         | 9000 |
| Watchtower  | Docker container auto-updater              | N/A  |
| Tailscale   | VPN for secure remote access               | N/A  |

## Setup Notes

1. **Install Docker**
2. **Run Docker Compose files from `docker/`**
3. **Configure firewall using `firewall/setup-firewall.sh`**
4. **Mount SSD via `mount/ssd-mount-guide.txt`**
5. **Add Tailscale app in CasaOS using JSON in `casaos/custom-apps`**
