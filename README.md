# DebianS - PHP5.6-fpm (日本環境） #

オフィシャルのphp-fpmを元に日本環境の調整を行いました。

### 調整内容 ###

* locale設定 (ja.utf-8)
* タイムゾーン （Asia/Tokyo）
* 必要なツールのインストール  
※ less vim git zip unzip git
* 画像を扱うためのツールインストール  
※ libfreetype6-dev libjpeg62-turbo-dev libpng12-dev libmcrypt-dev
* PHPのオプションを追加  
※ docker-php-ext-install pdo_mysql mysqli mbstring gd iconv mcrypt zip xml
* php-composerインストール

### 使い方 ###

下記のコマンドにてコンテナを起動します

```
$ docker pull reflet/debian8-php56
$ docker run --rm -u "www-data" -it php bash
```

### メンテナンス ###

下記のコマンドにてソースのダウンロードとイメージの構築を実行します。

```
$ git clone git@bitbucket.org:reflet/docker-debian8-php56.git .
$ docker build -t reflet/debian8-php56 .
$ docker login
$ docker tag reflet/debian8-php56 reflet/debian8-php56:{タグ}
$ docker push reflet/debian8-php56
```
