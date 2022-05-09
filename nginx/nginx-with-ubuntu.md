# Установка nginx c ubuntu 20.04

## Установить nginx

```
apt-get install nginx
```

Просмотр файлов конфигурации <code>ls -l /etc/nginx/</code>.

## Сборка nginx из исходного кода

```
sudo apt-get update
```

### Установка библиотеки для содания билдов

```
sudo apt-get install build-essential
```

На сайте wiki.nginx.org находим релиз [nginx-1.21.0](https://nginx.org/download/nginx-1.21.0.tar.gz?_ga=2.127663629.1431204307.1652003785-169768010.1652003785) или выше.

```
# download
wget url nginx-1.21.0

# unzip
tar -zxvf nginx-1.21.0.tar.gz

# go to folder
cd nginx-1.21.0/

```

### Устанавливаем набор библиотек

```
sudo apt-get install libpcre3 libpcre3-dev libpcrecpp0v libssl-dev zlib1g-dev
```

### Изменяем конфигурацию nginx

```
# go to folder
cd /etc/nginx/

# set error log path and other
./configure --sbin-path=/usr/bin/nginx - -conf-path=/etc/nginx/nginx.conf --error-log-path=/var/log/nginx/error.log --http-lo g-path=/var/log/nginx/access.log --with-debug --with-pcre --with-http_ssl_module

# instal
sudo make
sudo make install
```

- Смотреть дополнительные параметры [nginx configure](http://nginx.org/ru/docs/configure.html)
- Для проверки конфигурации: <code>ls -l /etc/nginx/</code>

### Запуск nginx с помощью команды nginx

```
nginx start
```
