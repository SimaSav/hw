# Task 1
## Устанавливаем репо zabbix
```
wget https://repo.zabbix.com/zabbix/7.4/release/ubuntu/pool/main/z/zabbix-release/zabbix-release_latest_7.4+ubuntu22.04_all.deb
dpkg -i zabbix-release_latest_7.4+ubuntu22.04_all.deb
apt update 
```

## Устанавливаем postgres
```
sudo apt install postgresql postgresql-contrib -y
```

## Устанавливаем компоненты - сервер, агент, фронт 
```
apt install zabbix-server-pgsql zabbix-frontend-php php8.1-pgsql zabbix-apache-conf zabbix-sql-scripts zabbix-agent
```
## Создаем пользователя и БД
```
sudo -u postgres createuser --pwprompt zabbix

enter <pass> 

sudo -u postgres createdb -O zabbix zabbix
```
## Инициализируем схему БД
```
zcat /usr/share/zabbix/sql-scripts/postgresql/server.sql.gz | sudo -u zabbix psql zabbix 
```

## Добавляем пароль в конфиг сервера
```
sudo nano /etc/zabbix/zabbix_server.conf
...
DBPassword=<pass>
```

## Заходим http://<ip>/zabbix настраевам через мастер установки

# Task 2
## Устанавливаем репо zabbix
```
wget https://repo.zabbix.com/zabbix/7.4/release/ubuntu/pool/main/z/zabbix-release/zabbix-release_latest_7.4+ubuntu22.04_all.deb
dpkg -i zabbix-release_latest_7.4+ubuntu22.04_all.deb
apt update 
```
# Устанавливаем агент
```
sudo apt install zabbix-agent -y
```
# Меняем конфиг - указываем ip сервера zabbix
```
sudo nano /etc/zabbix/zabbix_agentd.conf
Server=<ip>
```
