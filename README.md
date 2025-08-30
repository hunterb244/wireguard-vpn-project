# wireguard-vpn-project
Self-hosted VPN project using DigitalOcean and WireGuard to bypass geolocation restrictions.”
# 🌐 Self-Hosted VPN Project (DigitalOcean + WireGuard)

## 🎯 Objective
Set up a self-hosted VPN on a DigitalOcean Droplet to allow a remote user to bypass geolocation restrictions and securely access U.S.-only streaming content (Peacock – Love Island Season 7).

---

## 🛠️ Tools & Tech
- DigitalOcean Droplet (Ubuntu 22.04, $6/month plan)
- SSH (remote server management)
- WireGuard VPN
- Linux firewall (UFW)

---

## 📋 Steps Taken
1. **Provision Droplet**
   - Created Ubuntu 22.04 Droplet on DigitalOcean in a U.S. datacenter.
   - Selected Premium CPU option (shared, NVMe SSD).

2. **Server Access**
   - Connected via SSH:
     ```bash
     ssh root@<droplet-ip>
     ```
   - Verified port 22 access using `Test-NetConnection`.

3. **System Updates**
   ```bash
   apt update && apt upgrade -y

bash <(curl -s https://raw.githubusercontent.com/Nyr/wireguard-install/master/wireguard-install.sh)

scp root@<droplet-ip>:/root/peacock.conf .
