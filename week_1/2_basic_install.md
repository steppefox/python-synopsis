Небольшой (не доконца доработанный) sh скрипт для быстрой установки базовых программ (запускать под root пользователем):

```
#!/bin/bash
server_status='Y'
read -p "Its server installation? [Y/n]:" server_status
echo "Updating source repositories"
sleep 1
apt-get update

echo "Starting installation"
sleep 1
echo "--------"
echo "0. Installing NGINX"
sleep 1
cd /home/
wget http://nginx.org/keys/nginx_signing.key
sudo apt-key add nginx_signing.key
cd /etc/apt/sources.list.d/
echo "deb http://nginx.org/packages/ubuntu/ trusty nginx" >> nginx.list
echo "deb-src http://nginx.org/packages/ubuntu/ trusty nginx" >> nginx.list
apt-get update
apt-get install nginx -y
rm /etc/nginx/conf.d/*.conf
# client_max_body_size 100M

echo "--------"
echo "1. Installing PHP5-FPM"
sleep 1
sudo apt-get install php5 php5-fpm php5-mysql php5-cli php5-json php5-curl php5-gd php-pear -y
cd /home/
curl -sS https://getcomposer.org/installer | php

echo "--------"
echo "2. Installing NANO"
sleep 1
sudo apt-get install nano -y

echo "--------"
echo "3. Installing GIT"
sleep 1
sudo apt-get install git -y

echo "--------"
echo "4. Installing Midnight Commander"
sleep 1
sudo apt-get install mc -y

echo "--------"
echo "5. Installing Mysql-server"
sleep 1
sudo apt-get install mysql-server -y

echo "--------"
echo "6. Installing Curl"
sleep 1
sudo apt-get install curl -y

echo "--------"
echo "7. Installing htop"
sleep 1
sudo apt-get install htop -y

# USUAL INSTALLING
if [ $server_status = 'n'  ] || [$server_status = 'N'];
	then

	echo "Installing whois"
	sleep 1
	sudo apt-get install whois -y


	echo "Installing nmap"
	sleep 1
	sudo apt-get install nmap -y


	# pdf generating tool from images
	echo "Installing PDF generator"
	sleep 1
	sudo apt-get install poppler-utils -y

	echo "Installing NodeJS"
	sleep 1
	curl -sL https://deb.nodesource.com/setup | sudo bash -
	sudo apt-get install nodejs -y
fi
```