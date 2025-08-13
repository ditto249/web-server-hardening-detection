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
Vulnerable app would output raw query, indicating possible SQLi vulnerability. <br>

## 4. Screenshots
Modsecurity off <br> <img width="613" height="141" alt="Screenshot 2025-08-06 172727" src="https://github.com/user-attachments/assets/db9cb2a3-8bb7-4d84-b2af-7d46123a0a87" /> <br>
Modsecurity on <br> <img width="603" height="155" alt="Screenshot 2025-08-06 174508" src="https://github.com/user-attachments/assets/1d86aa13-3ac5-4e75-aaff-583e85ce7d3d" />
