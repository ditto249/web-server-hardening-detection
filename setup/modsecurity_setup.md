# ModSecurity Setup
## 1. Install ModSecurity
```bash
sudo apt install libapache2-mod-security2 -y
```
## 2. Enable ModSecurity
```bash
sudo a2enmod security2
```
## 3. Switch to DetectionOnly Mode (optional during testing)
Edit: <br>
```bash
sudo nano /etc/modsecurity/modsecurity.conf
```
Set: <br>
```graphql
SecRuleEngine On
```
## 4. Install OWASP Core Rule Set (CRS)
```bash
cd /usr/share
sudo git clone https://github.com/coreruleset/coreruleset.git
cd coreruleset
sudo cp crs-setup.conf.example crs-setup.conf
```
Edit Apache config: <br>
```bash
sudo nano /etc/apache2/mods-enabled/security2.conf
```
Add these inside <IfModule security2_module>:
```bash
IncludeOptional /usr/share/coreruleset/crs-setup.conf
IncludeOptional /usr/share/coreruleset/rules/*.conf
```
Restart Apache:
```bash
sudo systemctl restart apache2
```
