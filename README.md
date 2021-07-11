# dockerImageLaravel

## 環境
・Docker<br>
※ Docker Desktopをinstall<br>
https://docs.docker.com/desktop/

## 構成
```
◆Infra(アプリケーション構成群)
・DB
・Nginx
・PHP
◆Docker-compose.yml(アプリケーション構成群記述ファイル)
◆Backend(アプリケーション格納場所)
```

## 構成スペック
```
・DB
- MySQL v8
・Nginx
- v1.2
・PHP
- v8.0
・Laravel
- v8.0
```

## 環境構築
```
① git clone {this repository} cd {this repository}

② docker compose up -d --build

③ docker compose exec app bash

④ composer install

⑤ cp .env.example .env

⑥ php artisan key:generate

⑦ (option)chmod -R 777 storage bootstrap/cache

⑧ (option)php artisan storage:link

⑨ php artisan migrate

⑩ exit
```

## アクセス
```
http://127.0.0.1:8080/
```

## Dockerコマンド
```
・Dockerfileの書き換えなどのビルド処理の変更をイメージに反映させる
docker-compose up --build
・イメージを元にコンテナを起動する(Dockerfileの変更がなければこっちでOK)
docker-compose up
・option -d
デタッチ、バックグラウンド起動
・コンテナを落とす
docker-compose down
・コンテナに入る
docker compose exec app bash
appはService名
docker compose psで確認可能
```


