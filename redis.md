## REDIS-SENTINEL REPLICATION WITH TWO SLAVES
### INSTALL INSTRUCTIONS FOR UBUNTU 20.04

### ASSUMPTIONS
|Role|Machine Name|IP Address|Operating System|
|-|-|-|-|
|Master |Aws|10.0.0.1|Ubuntu 20.04|
|Slave 1 |Aws|10.0.0.1|Ubuntu 20.04|
|Slave 2 |Aws|10.0.0.2|Ubuntu 20.04|
### On Master 
###### UPDATE AND INSTALL PACKAGES
'''
apt update 
apt upgrade -y
apt install redis -y
apt install redis-sentinel -y 
apt install firewalld -y
'''
###### Configure Replication Settings
'''
systemctl stop sentinel
chown redis:redis /etc/redis/sentinel.conf
chown redis:redis /var/log/redis/redis-sentinel.log
ufw allow 6379
ufw allow 26379
ufw allow 22
'''
###### Edit REDIS.CONF FILE
nano /etc/redis/redis.conf
bind 127.0.0.11 10.0.0.1

protected-mode no

save and exit;
###### Start Redis Replication
'''
systemctl restart redis
'''

