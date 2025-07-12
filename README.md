# raspberrypi-homelab
My Raspberry Pi Home Lab for IT Support, Networking, and System Administration
# 🏠 Raspberry Pi Home Lab Server

This project showcases a fully configured Raspberry Pi server used to simulate real-world IT support, networking, system administration, and cybersecurity tasks. It was built as part of my personal portfolio to demonstrate hands-on skills after earning my Google IT Support Certificate.

---

## 🎯 Objectives

- Gain hands-on experience with Linux system administration
- Practice network configuration and troubleshooting
- Host and share services (web, file, FTP, DNS/DHCP)
- Secure a Linux server using firewalls and intrusion detection
- Build a live GitHub portfolio project

---

## 🧰 Hardware & Software Used

| Item             | Details                                       |
|------------------|-----------------------------------------------|
| Raspberry Pi     | Pi 4 (4GB RAM) running Ubuntu Server 22.04    |
| Client Device    | Windows 10 laptop (SSH & remote access)       |
| Tools Installed  | Apache, Samba, vsftpd, dnsmasq, OpenSSH, ufw, fail2ban |

---

## 🌐 Networking & Troubleshooting

- Configured static and dynamic IPs using Netplan
- Verified connectivity with `ping`, `traceroute`, `nslookup`, `netstat`
- Captured packets using **Wireshark**
- Simulated network issues (disconnected cable, misconfigured DNS)
- Documented all diagnostic steps

---

## 🖥 System Administration Tasks

- Created and managed users with `adduser`, `usermod`, and `/etc/sudoers`
- Scheduled tasks using `cron` (e.g., logging health checks every 30 minutes)
- Managed file systems and partitions using `lsblk`, `fdisk`, and `mount`
- Monitored performance using `top`, `htop`, `iotop`, and `du`

---

## 🧩 Services Configured

### 📁 Samba File Sharing

- Configured `/srv/samba/share` with guest access
- Shared files with Windows client via `\\raspberrypi.local\Shared`

### 🌐 Apache Web Server

- Installed Apache2 and hosted a custom HTML file
- Accessed via `http://<pi-ip>` from any browser on the network

### 📡 FTP Server

- Installed and configured `vsftpd` to allow secure FTP file transfers

### 📡 DHCP & DNS Server

- Used `dnsmasq` to provide DHCP and local DNS
- Tested with multiple devices to confirm IP assignment

---

## 🔐 Security

- Installed and configured `ufw` to limit access:
  ```bash
  sudo ufw allow OpenSSH
  sudo ufw allow 80/tcp
  sudo ufw allow Samba
  sudo ufw allow 20/tcp  # FTP Data
  sudo ufw allow 21/tcp  # FTP Control
  sudo ufw allow 53      # DNS
  sudo ufw allow 67:68/udp  # DHCP
  sudo ufw enable
