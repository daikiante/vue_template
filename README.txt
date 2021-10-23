◎dockerで動かすvueテンプレート

■フォルダ構成
vue_template/docker/web/Dockerfile
            /server/app
            docker-compose.yml
            README.txt
※1アプリ1vue_templateを推奨

■使い方
１，vue_template直下に移動
	cd hoge/vue_template

２，イメージをビルドしてコンテナを起動
	# イメージのビルドとコンテナ起動を同時に行う --buildは強制ビルドするオプション
	docker-compose up -d --build

	# 別々に行う場合
	# イメージのビルド
	docker-compose build

	# コンテナの起動 -dはバックグラウンドで行うオプション
	docker-compose up -d

３，コンテナに入る
	docker-compose exec web /bin/sh

４，VueのデフォルトApp作成
	/app # vue init webpack

	# 色々聞かれるが以下を参考にして質問に答えれば良い
	? Author yamada
	? Vue build standalone
	? Install vue-router? Yes
	? Use ESLint to lint your code? Yes
	? Pick an ESLint preset Standard
	? Set up unit tests No
	? Setup e2e tests with Nightwatch? No
	? Should we run `npm install` for you after the project has been created? (recommended) npm

５，ホストを設定(vue_template/server/config/index.js)
	# 明示的に0.0.0.0に変更
	host: '0.0.0.0'

	※デフォルトだとlocalhost(127.0.0.1)になっている
