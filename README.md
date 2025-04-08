# installlinuxvps
-Necessary configurations before installing the program on a VPS server
- بعد از خرید و فعال شدن سرور لینوکس یک سری پیش نیاز باید نصب بشه ، کد زیر همه پیش نیاز ها را با هم نصب میکنه
    ```
#!/bin/bash

# به‌روزرسانی سیستم
echo "Updating system packages..."
sudo apt update && sudo apt upgrade -y

# نصب Python3 و pip
echo "Installing Python3 and pip..."
sudo apt install -y python3 python3-pip

# نصب GO
echo "Installing Go..."
sudo apt install -y golang

# نصب Node.js، npm و yarn
echo "Installing Node.js, npm, and yarn..."
sudo apt install -y nodejs npm
sudo npm install -g yarn

# نصب Docker و Docker-Compose
echo "Installing Docker and Docker-Compose..."
sudo apt install -y docker.io
sudo systemctl start docker
sudo systemctl enable docker
sudo groupadd docker
sudo usermod -aG docker $USER
sudo apt install -y docker-compose

# نصب lsof و ufw
echo "Installing lsof and ufw..."
sudo apt install -y lsof ufw

# نصب htop
echo "Installing htop..."
sudo apt install -y htop

# نمایش پیام پایان
echo "All packages have been installed successfully. Please log out and log back in for Docker permissions to take effect."

  ```
