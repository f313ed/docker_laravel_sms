### docker_laravel_sms

# 環境

## ブランチ
- sample: サンプルです


## 環境構築方法
### 1. git clone
```
$ git clone https://5next.backlog.jp/git/SRE/docker_laravel.git
 or
$ git clone 5next@5next.git.backlog.jp:/SRE/docker_laravel.git

$ cd docker-laravel
```

ブランチ切替
```
$ git fetch && git checkout sample
```

### 2. セットアップ
```
$ docker-compose build && docker-compose up -d && docker-compose exec php laravel new laravel
```

### 3. 確認
```
$ curl http://localhost:8080
$ docker-compose exec php node -v
$ docker-compose exec php composer --version
$ docker-compose exec php php -v
$ mysql -h 0.0.0.0 --port 13306 -u homestead -psecret
$ mysql -h 0.0.0.0 --port 13306 -u root -proot
$ redis-cli -h 0.0.0.0 -p 16379
## .env書換え
DB_HOST=127.0.0.1  
  ↓↓↓ 
DB_HOST=mysql  
## php artisan migrateを実行確認
$ docker-compose exec php php ./laravel/artisan migrate
```

### 4. 削除
```
docker-compose down && docker rmi $(docker images -q)
rm -rf ./src
```

##参考
https://qiita.com/igayamaguchi/items/aec8f2b15b203946a2c4#%E6%AC%A1%E3%81%ABphp



# 環境
.gitを削除して新たに作成する