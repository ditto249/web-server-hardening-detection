# Apache Setup

## 1. Install Apache <br>
```bash
sudo apt update 
sudo apt install apache2 -y 
```
(I installed Apache 2.4 on a Ubuntu VM) 

## 2. Enable and Start Apache <br>
```bash
sudo systemctl enable apache2 
sudo systemctl start apache2 
sudo systemctl status apache2 
```

## 3. Test Apache in Browser <br>
Visit: <br>
http:// UBUNTU-IP <br>
You should see the default Apache landing page. <br>
(I did not see it at first, but thats because I had to change the settings of my VM to a bridged adapter so I can see the page in my browser.)

## 4. Create a Hidden Directory <br>
```bash
sudo mkdir /var/www/html/hidden 
echo "Hidden file!" | sudo tee /var/www/html/hidden/index.html 
```

## 5. Permissions <br>
```bash
sudo chown -R www-data:www-data /var/www/html/hidden 
sudo chmod -R 755 /var/www/html/hidden 
```
