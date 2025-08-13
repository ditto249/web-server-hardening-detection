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

## 4. Screenshots
<img width="626" height="376" alt="Screenshot 2025-08-06 165922" src="https://github.com/user-attachments/assets/5e695464-e814-4634-b149-8dc7bb1bb9b5" /> <br>
This screenshot shows the gobuster command in my Kali Linux VM, and with ModSecurity off, you can see the hidden file, testdir, which is a problem as you files that maybe you weren't meant to see, and attackers can use this to get in. 
<img width="544" height="364" alt="Screenshot 2025-08-06 174522" src="https://github.com/user-attachments/assets/290abb09-4583-4220-985b-d1f447b5c4b9" /> <br>
This screenshot is with ModSecurity on, and you can see that it missed testdir.

## 5. Notes
I was struggling for a long time to actually get gobuster working as it kept missing, and I realised that ModSecurity was doing its job right, so only when i turned it off is when i realised have importnat hardening web servers are. 
