Moodle on AWS -- RAVI KUMAR
=========

## Click below link to install and configure Moodle on AWS Instance

Checkout [Moodle using CFT Template](https://github.com/imraviarora/moodle-on-aws/tree/main/Automate%20Moodle%20Using%20AWS%20CFT)

## Commands used to automate moodle installation

Installation of PHP
```
sudo su
yum module install php:7.2 -y
systemctl enable --now php-fpm
systemctl status php-fpm
```

Installation and configuration of Apache Server and MySQL
```
yum install mysql mysql-server wget unzip httpd php-mysqli php-zip php-gd php-intl php-xmlrpc php-soap -y
systemctl enable --now mysqld.service
systemctl status mysqld.service
systemctl status httpd
systemctl start httpd

mysql -u root -e "create database moodle;"
mysql -u root -e "show databases;"
```

Download Moodle stable zip, and unzip inside html directory
```
wget https://download.moodle.org/stable310/moodle-3.10.zip
chmod 777 /var/www/
unzip moodle-3.10.zip -d /var/www/html/
setenforce 0
systemctl reload httpd
```

Configure localhost SSL using mod_ssl
```
dnf install mod_ssl -y 
systemctl restart httpd
apachectl -M | grep ssl
sed -i 's+#SSLCACertificateFile /etc/pki/tls/certs/ca-bundle.crt+SSLCACertificateFile /etc/pki/tls/certs/ca-bundle.crt+g' /etc/httpd/conf.d/ssl.conf
systemctl reload httpd
```
