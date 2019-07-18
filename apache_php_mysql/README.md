# Apache+PHP+mysql
- PHPの拡張モジュールがインストールされてないものが多い。それらは、`docker-php-ext-install`でインストールする
- このサンプルでは、コンテナにbashでログインしてmysqlコマンドを実行したかったため、apt-getでmysq-clientのインストールをしています