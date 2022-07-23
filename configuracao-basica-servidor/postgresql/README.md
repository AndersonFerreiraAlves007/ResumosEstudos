# Postgresql
  1. sudo apt update sudo apt install postgresql postgresql-contrib
  2. service postgresql status
  3. sudo su postgres
  4. psql
  5. ALTER USER postgres WITH PASSWORD 'my_password';
  6. sudo vim /etc/postgresql/{version_postgres}/main/postgresql.conf 
  7. adicione o seguinte conteúdo 
    ```
      #listen_addresses = 'localhost'
      listen_addresses = '*'
    ```
  8. sudo nano /etc/postgresql/{version_postgres}/main/pg_hba.conf 
  9. adicone o seguinte conteúdo:
    ```
      # TYPE  DATABASE	USER	ADDRESS   	METHOD
      host    all     	all     0.0.0.0/0       md5
      host    all             all     :/0             md5
    ```
  10. sudo systemctl restart postgresql 
  11. sudo ufw allow 5432 
