# 仮想環境の作り方
mkdir djangogirls
cd djangogirls
D:\source\Python\Django_samples\djangogirls>python -m venv myvenv

# 仮想環境を起動
myvenv\Scripts\activate

# Djangoのインストール
python -m pip install --upgrade pip

# requirementsファイルによってパッケージをインストールする
pip install -r requirements.txt

# プロジェクトの作成
django-admin startproject mysite .

# データベースをセットアップする
python manage.py migrate

# ウェブサーバを起動する
python manage.py runserver

# 新しいアプリケーションの作成
python manage.py startapp blog

# データベースにモデルのためのテーブルを作成する
python manage.py makemigrations blog

python manage.py migrate blog

# superuser （サイトの全てを管理するユーザー）の作成
python manage.py createsuperuser

---------------------------------
git 関連

# Gitリポジトリを始める
$ git init
Initialized empty Git repository in ~/djangogirls/.git/
$ git config --global user.name "Your Name"
$ git config --global user.email you@example.com


# .gitignoreにコミットしないファイルを記載
*.pyc
*~
/.vscode
__pycache__
myvenv
db.sqlite3
/static
.DS_Store

# git status コマンドは、あらゆる追跡されていない/変更されている/ステージされている（untracked/modifed/staged）ファイルや、ブランチの状態などさまざまな情報を返します。
$ git status
On branch master

No commits yet

Untracked files:
  (use "git add <file>..." to include in what will be committed)

        .gitignore
        blog/
        manage.py
        mysite/
        requirements.txt

nothing added to commit but untracked files present (use "git add" to track)

# 変更内容を保存します
$ git add --all .
$ git commit -m "My Django Girls app, first commit"
 [...]
 13 files changed, 200 insertions(+)
 create mode 100644 .gitignore
 [...]
 create mode 100644 mysite/wsgi.py

# GitHubにコードをプッシュする
$ git remote add origin https://github.com/Yoshiyuki-Su/django-samples.git
$ git push -u origin master


---------------------------------


