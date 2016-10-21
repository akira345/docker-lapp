DockerでLAPP環境を作成する
====

DockerでLAPPでの開発環境を作成するスクリプトです。

PHP7+Adminar+PostgreSQL9.6の環境が作成されますので、
簡単に開発環境を作成することが出来ます。

composerもインストールされています。
```bash
git clone https://github.com/akira345/docker-lapp.git
cd docker-lapp/
docker-compose up -d
```

phpPgAdminの代わりにadminarをインストールしています。

/adminarでアクセスできます。

|    |    |
|---------|---------|
|データベース種類|PostgreSQL|
|サーバ|pgsql|
|ユーザ名|postgres|
|パスワード|passwd|

Dockerコンテナに入り、composerなど動かしたい場合は、

```bash
docker exec -it <コンテナID> bash
```
な感じで。