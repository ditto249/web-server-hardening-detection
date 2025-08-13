# ModSecurity Setup
## 1. Install ModSecurity
```bash
sudo apt install libapache2-mod-security2 -y
```
## 2. Enable ModSecurity
```bash
sudo a2enmod security2
```
## 3. Switch the mode from DectectionOnly to On
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
Add these inside IfModule security2_module:
```bash
IncludeOptional /usr/share/coreruleset/crs-setup.conf
IncludeOptional /usr/share/coreruleset/rules/*.conf
```
I had a problem as i got an error saying that ModSecurity had found another rule with the same ID: <br>
<img width="793" height="54" alt="Screenshot 2025-07-02 111029" src="https://github.com/user-attachments/assets/b1b16492-9390-4717-aec1-b3b7d37063f2" /> <br>
When I changed the ID number, I got the same error on a different line, which then turned to a different file, so I had to fina another fix. I went in the security config file and I changed the file from: <br>
<img width="842" height="259" alt="Screenshot 2025-07-01 115004" src="https://github.com/user-attachments/assets/e2c623c0-5961-4c22-b759-622609f84ae2" /> <br>
To: <br>
<img width="719" height="390" alt="Screenshot 2025-07-07 120936" src="https://github.com/user-attachments/assets/c8571b84-8cb5-404b-b2b5-fa8a841138c0" /> <br>
Which fixed the situation as I think there were two sets of the same rules so the ID were dupicated so ModSecurity wasn't allowing it.

Restart Apache:
```bash
sudo systemctl restart apache2
```
