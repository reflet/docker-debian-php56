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
※ docker-php-ext-install gd exif gmp mysql mysqli pdo_mysql pdo_pgsql pgsql dba mcrypt zip bz2 soap sockets xsl bcmath calendar pcntl wddx gettext opcache tidy
* memcached enabled
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
$ git clone git@github.com:reflet/docker-debian-php56.git .
$ docker build -t reflet/debian8-php56 .
$ docker login
$ docker tag reflet/debian8-php56 reflet/debian8-php56:{タグ}
$ docker push reflet/debian8-php56
```
