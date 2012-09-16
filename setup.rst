セットアップ
===========================

ローカル環境へのインストール
---------------------------

動作環境
~~~~~~~~~~~~~
以下のソフトウェアのインストールが必要です。

* Ruby 1.8.7 / 1.9.3
* RubyGems 1.4.2 or later
* Bundler 1.0.7 or later
* PostgreSQL 9.0 or later

インストール
~~~~~~~~~~~~~

::

    $ bundle install --path .bundle
    $ bundle exec rake assets:precompile
    $ bundle exec rake db:migrate
    $ vi conf/database.yml

起動
~~~~~~~~~~~~~

::

    $ bundle exec rake rails s -e production

Heroku へのデプロイ
-------------------

Heroku Toolbelt のインストール及び、ログインが完了している状態で
以下のコマンドを実行してください。

::

    $ heroku create
    $ heroku addons:add heroku-postgresql:dev
    $ git push heroku master
    $ heroku run rake db:migrate
    $ heroku restart

