# Gobuster Directory Enumeration
## 1. Tool
[GoBuster](https://github.com/OJ/gobuster) - directory & file brute-forcer.
## 2. Command Used
```bash
gobuster dir -u http://<UBUNTU-IP> -w testlist.txt -b 403 -v
```
```bash
-u → Target URL (web server IP)
-w → Wordlist file
-b 403 → Ignore "Forbidden" responses to reduce noise
-v → Verbose mode
```
## 3. Expected Behaviour
If hidden directories exist, they appear in the output. <br>

## 4. Actual behaviour
If hidden directories exist, they appear in the output. <br>

## 5. Screenshots
Modsecurity off <img width="626" height="376" alt="Screenshot 2025-08-06 165922" src="https://github.com/user-attachments/assets/5e695464-e814-4634-b149-8dc7bb1bb9b5" />
Modsecurity on <img width="544" height="364" alt="Screenshot 2025-08-06 174522" src="https://github.com/user-attachments/assets/290abb09-4583-4220-985b-d1f447b5c4b9" />
