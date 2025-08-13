# Fail2Ban Setup
## 1. Install Fail2Ban
```bash
sudo apt install fail2ban -y
```
## 2. Create Local Jail Config
```bash
sudo nano /etc/fail2ban/jail.local
```
## 3. Add this for Apache:
```bash
[apache-auth]
enabled = true
port    = http,https
filter  = apache-auth
logpath = /var/log/apache2/error.log
maxretry = 3
```
## 4. Restart Fail2Ban
```bash
sudo systemctl restart fail2ban
sudo systemctl status fail2ban
```
