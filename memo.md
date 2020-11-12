■インストール内容
pip3 install django


# Djangoのプロジェクトを作成
# フォルダが全て作成される。 TopFolder/HelloWorldProject/HelloWorldProject が作成される。
django-admin startproject HelloWorldProject

# Djangoのプロジェクトを作成(.をつける)
# TodoAppProjectは自分で作成後実施 下記コマンドではフォルダは追加で作られない。(上のコマンドとは違う) TopFolder/TodoAppProject/todoproject が作成される。
django-admin startproject todoproject .

# サーバーの起動
python manage.py runserver

# アプリの追加
python manage.py startapp helloworldapp

# makemigrations
python manage.py makemigrations

# migrate
python manage.py migrate

# スーパーユーザーの作成
python manage.py createsuperuser



------------------------------------------------------------------------------------------------------------------------------
■Github等にシークレットキーを公開したくない場合は下記のプログラムを実施する。
HelloWorldProject\HelloWorldProject\gen_secrets.py
上記にある gen_secrets.pyを実行する。
python gen_secrets.py

その後、上記のプログラムで出来る「secrets.json」をバージョン管理対象外(.gitignore)に設定する。

