# Linux Server Hardening – SSH Security

## Objective
Hardened an Ubuntu 24.04 server by securing SSH, configuring a firewall, and implementing brute-force protection using Fail2Ban.

---

## 1️⃣ SSH Hardening

- Changed default SSH port from 22 → 2222
- Disabled password authentication
- Enabled key-based authentication
- Restarted SSH service

```bash
sudo nano /etc/ssh/sshd_config
sudo systemctl restart ssh

---

## 📸 Verification Screenshots

### SSH Listening on Port 2222
![SSH Port](screenshots/ssh-port-2222.png)

### UFW Active
![UFW](screenshots/ufw-active.png)

### Fail2Ban Running
![Fail2Ban](screenshots/fail2ban-running.png)

### SSH Jail Active
![Fail2Ban Jail](screenshots/fail2ban-sshd-jail.png)

---