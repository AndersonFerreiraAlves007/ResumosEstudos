# mysql

sudo apt update
sudo apt install mysql-server
systemctl is-active mysql

sudo mysql
ALTER USER 'root'@'localhost' IDENTIFIED WITH mysql_native_password BY 'password';
FLUSH PRIVILEGES;
exit

systemctl status mysql.service
sudo systemctl start mysql.

sudo ufw allow 3306/tcp

sudo mysql_secure_installation

mysql -u root -p

sudo nano /etc/mysql/mysql.conf.d/mysqld.cnf
...
bind-address            = 0.0.0.0
...

sudo systemctl restart mysql

CREATE USER 'user'@'%' IDENTIFIED WITH mysql_native_password BY 'password';
GRANT ALL PRIVILEGES ON database_name.* TO 'username'@'%'; (database_name pode ser *, se for para todos)
FLUSH PRIVILEGES;

DELETE FROM mysql.user where user = 'sartori';

SELECT user,authentication_string,plugin,host FROM mysql.user;

# mysql workbench

sudo snap install mysql-workbench-community

sudo snap connect mysql-workbench-community:password-manager-service :password-manager-service

# backup

mysql -u [user name] –p [target_database_name] < [dumpfilename.sql]
mysql --host=dbfmylast --user=root --port=3306 -p sakila < D:\sakila.sql
mysql -u root -p < alldatabases.sql

mysqldump --host=dbfmylast --user=root --port=3306 -p sakila working_hours > D:\backup_working_hours_table.sql

# logs

general_log_file        = /var/log/mysql/mysql.log
general_log             = 1

log_slow_queries       = /var/log/mysql/mysql-slow.log
long_query_time = 2
log-queries-not-using-indexes

service mysql restart

mysql -u root -p

SET GLOBAL general_log = 'ON';
SET GLOBAL slow_query_log = 'ON';

