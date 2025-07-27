# Raspberry Pi 5 NAS & Self-Hosted Server Setup

This repository documents my complete Raspberry Pi 5 setup used to build a personal NAS, Docker stack, remote access system, and GUI dashboard using CasaOS.

## 🧰 Hardware

- Raspberry Pi 5 (4GB RAM)
- 1TB Kioxia G3 Plus NVMe SSD (5000 MB/s)
- GeeekPi N04 M.2 NVMe HAT
- USB 3.0 SSD external drive (for shared storage)

## ⚙️ Installed Components

- **Ubuntu OS (Server/Desktop)**
- **CasaOS** – Modern self-hosted app dashboard
- **Docker + Docker Compose**
- **Portainer** – Docker container manager
- **Cockpit** – Full system monitoring and admin
- **Nextcloud** – Personal cloud storage (Dockerized)
- **Watchtower** – Auto-updater for Docker containers
- **Fail2Ban / Firewall** – Network protection
- **Tailscale** – Remote access VPN
- **Mounted Storage** – `/mnt/ssd/shared` for Nextcloud and more

## Included Services

| Service     | Description                                | Port |
|-------------|--------------------------------------------|------|
| CasaOS      | GUI Dashboard                              | 80   |
| Nextcloud   | Private cloud storage                      | 10443|
| Portainer   | Docker GUI Manager                         | 9000 |


## 📦 Docker Setup

Each service has its own Docker Compose or single container YAML:
- [`docker/nextcloud-compose.yml`](docker/nextcloud-compose.yml)
- [`docker/watchtower.yml`](docker/watchtower.yml)
- [`docker/portainer.yml`](docker/portainer.yml)
- [`docker/cockpit.yml`](docker/cockpit.yml)

## 🌐 Remote Access with Tailscale

Tailscale is used to securely access the Pi over the internet without needing port forwarding. The [CasaOS custom app JSON](casaos/custom_apps/tailscale.json) allows easy dashboard access.

## 🔒 Firewall Configuration

UFW or equivalent is used to lock down open ports:
```bash
sudo ufw allow OpenSSH
sudo ufw allow 80,443/tcp
sudo ufw enable
