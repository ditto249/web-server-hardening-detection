# Apache Setup

## 1. Install Apache <br>
sudo apt update <br>
sudo apt install apache2 -y <br>

2. Enable and Start Apache <br>
sudo systemctl enable apache2 <br>
sudo systemctl start apache2 <br>
sudo systemctl status apache2 <br>

3. Test Apache in Browser <br>
Visit: <br>
http://<UBUNTU-IP> <br>
You should see the default Apache landing page. <br>

4. Create a Hidden Directory <br>
sudo mkdir /var/www/html/hidden <br>
echo "Hidden file!" | sudo tee /var/www/html/hidden/index.html <br>

5. Permissions <br>
sudo chown -R www-data:www-data /var/www/html/hidden <br>
sudo chmod -R 755 /var/www/html/hidden <br>
