# Docker sample
## Apache + PHP-FPM
別々のコンテナを使って連携させた場合
### 注意点
- httpd.conf に `ProxyPassMatch ^(.*\.php(/.*)?)$ fcgi://php-fpm:9000/usr/local/apache2/htdocs/$1` を追記し、必要なモジュールをloadするように修正してあります。
  - LoadModule proxy_module modules/mod_proxy.so
  - LoadModule proxy_fcgi_module modules/mod_proxy_fcgi.so
### 起動方法
```
docker-compose -f "apache/docker-compose.yml" up -d --build
```
### 停止方法
```
docker-compose -f "apache/docker-compose.yml" down
```