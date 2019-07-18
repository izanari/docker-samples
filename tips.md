# TIPS
## コンテナ内のファイルを見たい
```
docker run --name tmp-nginx-container -d nginx
docker exec コンテナID more /etc/nginx/conf.d/default.conf
```
## コンテナ内のファイルをホストへコピーする
```
docker run --name tmp-nginx-container -d nginx
docker cp コンテナID mp-nginx-container:/etc/nginx/nginx.conf ./nginx.conf
```
## コンテナにログインする
```
docker exec -t -i コンテナID bash
```
bashで使えるコマンドが全て使えるわけではないのですよ。
## ログを確認する
```
docker logs -f コンテナID
```
