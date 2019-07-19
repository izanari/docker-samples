# Docker sample
## Apache 2.4.38
## Dockerfile
- gitとcurlをインストールしている。
- 他にも必要なファイルがあれば適宜追加をする
## docker-compose.yml
- htdocsとApacheの設定ファイルをマウントしています
### 起動方法
```
docker-compose -f "docker-compose.yml" up -d --build
```
### 停止方法
```
docker-compose -f "docker-compose.yml" down
```