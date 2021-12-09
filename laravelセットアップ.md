## dockerコンテナ内にlaravelの開発環境を作成する
1. dockerコンテナの起動　
- `docker-compose up -d`

2. appコンテナ内にphp.iniファイルを作成(コンテナのメモリ容量を上げる為)
 - `docker-compose exec app vi /usr/local/etc/php/php.ini`
 - `memory_limit = -1`
 - `docker-compose exec app php -r "echo ini_get('memory_limit').PHP_EOL;"` (メモリ容量確認)
 
3. laravelのインストール
- `docker-compose exec app composer create-project laravel/laravel . "7.*" --prefer-dist`

4. ブラウザ(localhost:8000)でlaravelのトップ画面を確認
 
