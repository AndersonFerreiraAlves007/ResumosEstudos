# Redis

sudo apt update
sudo apt install redis-server

sudo systemctl restart redis.service
sudo systemctl status redis
sudo systemctl disable redis

redis-cli
CONFIG SET requirepass "mypass"
AUTH mypass
