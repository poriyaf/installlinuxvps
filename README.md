# installlinuxvps
-Necessary configurations before installing the program on a VPS server
- بعد از خرید و فعال شدن سرور لینوکس یک سری پیش نیاز باید نصب بشه ، کد زیر همه پیش نیاز ها را با هم نصب میکنه
```
#!/bin/bash


echo "Updating system packages..."
sudo apt update && sudo apt upgrade -y


echo "Installing Python3 and pip..."
sudo apt install -y python3 python3-pip


echo "Installing Go..."
sudo apt install -y golang


echo "Installing Node.js, npm, and yarn..."
sudo apt install -y nodejs npm
sudo npm install -g yarn


echo "Installing Docker and Docker-Compose..."
sudo apt install -y docker.io
sudo systemctl start docker
sudo systemctl enable docker
sudo groupadd docker
sudo usermod -aG docker $USER
sudo apt install -y docker-compose


echo "Installing lsof and ufw..."
sudo apt install -y lsof ufw


echo "Installing htop..."
sudo apt install -y htop


echo "All packages have been installed successfully. Please log out and log back in for Docker permissions to take effect."
```
