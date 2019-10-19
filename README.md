# How To Install LAMP On CentOS7

# Step One—Install Apache:
```
yum install httpd

service httpd start
```
To check if Apache is installed, direct your browser to your server’s IP address (eg. http://12.34.56.789). The page should display 

# Step Two—Install MySQL:
```
yum update

wget http://repo.mysql.com/mysql57-community-release-el7-8.noarch.rpm

yum install mysql57-community-release-el7-8.noarch.rpm

yum install mysql-server

service start mysqld

mysql_secure_installation
```
 
# Step Three—Install PHP:
```
yum install php php-mysql
  
yum search php
  
yum info php-fpm
  
yum install php-fpm
```
To set this up, first create a new file:
```
vi /var/www/html/info.php
```
# Add in the following line:
```
<?php
phpinfo();
?>
```
press ESC and input:wq!,enter
Restart apache so that all of the changes take effect on your virtual server
```
service httpd restart
```
Finish up by visiting your php info page (make sure you replace the example ip address with your correct one): http://12.34.56.789/info.php
