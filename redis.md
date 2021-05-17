# apt update && apt upgrade -y && apt install firewalld -y && apt install redis -y && apt install redis-sentinel -y && systemctl stop sentinel
## systemctl stop redis
chown redis:redis /etc/redis/sentinel.conf
chown redis:redis /var/log/redis/redis-sentinel.log
ufw allow 6379 
ufw allow 26379
ufw allow 22
nano /etc/redis/redis.conf
bind 127.0.0.11 yourprivateip
protected-mode no
save and exit it
systemctl restart redis
#in slaves
apt update && apt upgrade -y && apt install firewalld -y && apt install redis -y && apt install redis-sentinel -y && systemctl stop sentinel
systemctl stop redis
chown redis:redis /etc/redis/sentinel.conf
chown redis:redis /var/log/redis/redis-sentinel.log
ufw allow 6379 
ufw allow 26379
ufw allow 22
nano /etc/redis/redis.conf
bind 127.0.0.11 yourprivateip
protected-mode no
# INLAST LINE ADD slaveof yourmasterprivateip
save and exit it
systemctl restart redis

