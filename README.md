# Laravel Framework 8.10.0
## setup
1. フォルダ作成
```sh
mkdir projectName
cd projectName
```
2. Laradockをclone
```sh
git clone https://github.com/laradock/laradock.git
```
3. laradock内の.env作成
```sh
cp laradock/env-example laradock/.env
```
4. dockerコンテナ立ち上げ
```sh
cd laradock
docker-compose up -d nginx php-fpm mysql workspace
```
5. 中に入る
```sh
docker-compose exec workspace bash
```
6. laravelインストーラーをインストール
```sh
composer require "laravel/installer"
```
7. プロジェクト作成
```sh
laravel new projectName
exit
```
8. 3で作成した.envパスを変更
```
# Point to the path of your applications code on your host
APP_CODE_PATH_HOST=../project
```
9. 起動コマンド
```sh
docker-compose up -d nginx php-fpm mysql workspace
```
10. laravelの.envのDB接続修正
```
DB_CONNECTION=mysql
DB_HOST=mysql
DB_PORT=3306
DB_DATABASE=default
DB_USERNAME=default
DB_PASSWORD=secret
```
