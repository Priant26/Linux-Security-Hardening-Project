# 🛡️ Linux Security Hardening Project – By Priant Singh

This is a small Linux security hardening project I did on my Ubuntu virtual machine. I used simple security steps to make the system safer. I updated the system, created a secure user, secured SSH, set up the firewall, installed Fail2Ban, and checked open ports.

---

## 🔧 What I Did

### 1. Updated and Upgraded the System
**Command:**
- **sudo apt update && sudo apt upgrade -y**
- This checks for updates and installs them. Keeping the system updated fixes vulnerabilities.

### 2. Created a New Non-Root User (Least Privilege)
**Commands:**
- **sudo adduser secureuser**
- **sudo usermod -aG sudo secureuser**
- Using a normal user instead of root is safer.

### 3. Installed OpenSSH Server
**Command:**
- **sudo apt install openssh-server -y**
- I installed SSH so I can secure it.

### 4. Disabled Root Login for SSH
**Command:**
**sudo nano /etc/ssh/sshd_config**
- Changed:
- PermitRootLogin no
- Restart SSH:
- **sudo systemctl restart ssh**
- This blocks attackers from logging in as root.

### 5. Enabled UFW Firewall
**Commands:**
- **sudo ufw enable**
- **sudo ufw allow OpenSSH**
- **sudo ufw allow 80**
- **sudo ufw status**
- Firewall blocks unwanted traffic.

### 6. Installed Fail2Ban (Brute Force Protection)
**Commands:**
- **sudo apt install fail2ban -y**
- **sudo systemctl start fail2ban**
- **sudo systemctl enable fail2ban**
- **sudo cp /etc/fail2ban/jail.conf /etc/fail2ban/jail.local**
- Fail2Ban blocks IPs that try too many wrong passwords.

### 7. Checked Open Ports
**Command:**
- **sudo ss -tulnp**
- Shows all open/listening ports and services.

---

## 📄 Full Documentation
Full PDF report with screenshots is included in this repo.

---

## ⭐ What I Learned
- How to reduce attack surface  
- How to secure SSH properly  
- How to set up firewall rules  
- How to block brute-force attacks  
- How to check open ports and services  

This project helped me understand Linux security in a simple and hands-on way.
