# Apache Setup

## 1. Install Apache
sudo apt update
sudo apt install apache2 -y

2. Enable and Start Apache
sudo systemctl enable apache2
sudo systemctl start apache2
sudo systemctl status apache2

3. Test Apache in Browser
Visit:
http://<UBUNTU-IP>
You should see the default Apache landing page.

4. Create a Hidden Directory
sudo mkdir /var/www/html/hidden
echo "Hidden file!" | sudo tee /var/www/html/hidden/index.html

5. Permissions
sudo chown -R www-data:www-data /var/www/html/hidden
sudo chmod -R 755 /var/www/html/hidden
