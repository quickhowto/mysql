# Allow Remote Computer to Connect & Administer MySQL 

## Ubuntu 18, MySQL 14

1. `$ sudo nano /etc/mysql/mysql.conf.d/mysqld.cnf`
   1. Either change to, or create a line that reads `bind-address = 0.0.0.0`
1. `$ sudo ufw allow from 192.168.0.50 to any port 3306` to allow that IP to connect
1. `$ mysql -u root -p` where *root* is mysql user
   1. On `$ Enter password:` enter *root*'s password
   1. `mysql>GRANT ALL ON *.* TO root@'192.168.0.50' IDENTIFIED BY 'root';`
   1. mysql>FLUSH PRIVILEGES;
   1. mysql>EXIT
1. `$ sudo systemctl restart mysql`

Tags: MySQL, Ubuntu, Linux
