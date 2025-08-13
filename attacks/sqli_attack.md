# SQL Injection Test
## 1. Setup
Created a vulnerable PHP page on the server: <br>
```bash
sudo nano /var/www/html/search.php
```
```php
<?php
if (isset($_POST['query'])){
    $q = $_POST['query'];
    echo "You searched for: " . $q;
}
?>
```
## 2. Attack Command
```bash
curl -X POST http://<UBUNTU-IP>/search.php --data "query=' OR 1=1 --"
```
## 3. Expected Behaviour
Vulnerable server would output raw query, indicating possible SQLi vulnerability. <br>

## 4. Screenshots
<img width="613" height="141" alt="Screenshot 2025-08-06 172727" src="https://github.com/user-attachments/assets/db9cb2a3-8bb7-4d84-b2af-7d46123a0a87" /> <br>
You can see that with it off, you can get the raw code for the php page and the vunberable dummy file I made. An SQL Injection attack can lead to: Theft, modification, or even destruction of sensitive data such as personally identifiable information and usernames and passwords. It can even lead to elevation of privileges at the application, database, or even operating system level. <br>
<img width="603" height="155" alt="Screenshot 2025-08-06 174508" src="https://github.com/user-attachments/assets/1d86aa13-3ac5-4e75-aaff-583e85ce7d3d" /> <br>
This was the most impressive part for me because with ModSecurity on, the actual contents of the form is hidden in a great way and gives confidence that you are protected. 
