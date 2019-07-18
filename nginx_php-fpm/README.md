# nginx + php-fpm
## 事前準備
### nginxの設定ファイルをホストへコピーします
```
docker run --name tmp-nginx-container -d nginx
docker cp 7c3f38e2d77f:/etc/nginx/conf.d/default.conf ./default.conf
```

### 設定する時の注意点
#### fastcgi の設定
- nginxのdefault.confのfastcgi_pass とfastcgi_parm の設定を変更することを忘れないようにする。
    - コピーした直後は、phpの設定がコメントアウトされているので有効にする
    - `php-fpm:9000`は`docker-compose.yml`で指定したサービス名を指定する
    - `default.conf`の設定例です。
``` 
    location ~ \.php$ {
        root    /usr/share/nginx/html;
        #fastcgi_pass   127.0.0.1:9000;
        fastcgi_pass    php-fpm:9000;
        fastcgi_index  index.php;
        #fastcgi_param  SCRIPT_FILENAME  /scripts$fastcgi_script_name;
        fastcgi_param  SCRIPT_FILENAME  $document_root$fastcgi_script_name;
        include        fastcgi_params;
    }
```