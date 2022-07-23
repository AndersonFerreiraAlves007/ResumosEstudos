# mysql correto:

  sudo nano /etc/mysql/mysql.conf.d/mysqld.cnf
  ...
  bind-address            = 0.0.0.0
  ...

  sudo systemctl restart mysql

  sudo mysql

  mysql -u root -p

  CREATE USER 'user'@'%' IDENTIFIED WITH mysql_native_password BY 'password';

  GRANT CREATE, ALTER, DROP, INSERT, UPDATE, DELETE, SELECT, REFERENCES, RELOAD on *.* TO 'user'@'%' WITH GRANT OPTION;

  FLUSH PRIVILEGES;

  exit

  sudo ufw allow 3306

# mysql:
  sudo apt update
  sudo apt install mysql-server
  sudo mysql_secure_installation

  SELECT user,authentication_string,plugin,host FROM mysql.user;
  sudo mysql
  ALTER USER 'root'@'localhost' IDENTIFIED WITH mysql_native_password BY 'password';
  FLUSH PRIVILEGES;
  SELECT user,authentication_string,plugin,host FROM mysql.user;
  exit

  mysql -u root -p
  DELETE FROM mysql.user where user = 'sartori';

  CREATE USER 'sartori'@'192.168.0.%' IDENTIFIED BY 'minha senha';
  GRANT ALL PRIVILEGES ON *.* TO 'sartori'@'192.168.0.%';

  CREATE USER 'sammy'@'localhost' IDENTIFIED BY 'password';
  GRANT ALL PRIVILEGES ON *.* TO 'sammy'@'localhost' WITH GRANT OPTION;
  exit

  systemctl status mysql.service
  sudo systemctl start mysql.

  sudo ufw allow 3306/tcp
