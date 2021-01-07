# django-samples
Djangoで作成されたサンプル群

# djangogirls
Django Girls のチュートリアルを実施したプログラム
> https://tutorial.djangogirls.org/ja/  

# プログラム作成時利用コマンドまとめ
## 仮想環境の作り方
```bash
mkdir djangogirls
cd djangogirls

djangogirls>python -m venv myvenv
```

## 仮想環境を起動
```bash
djangogirls>myvenv\Scripts\activate

(myvenv) djangogirls>
```

## 仮想環境の停止
```bash
(myvenv) djangogirls>yvenv\Scripts\deactivate
```

## pipのバージョンアップ
```bash
(myvenv) djangogirls>python -m pip install --upgrade pip
```
## requirementsファイルによってパッケージをインストールする
```bash
(myvenv) djangogirls>pip install -r requirements.txt
```

## Djangoのプロジェクトを作成方法
### フォルダが全て作成される。 
/HelloWorldProject/HelloWorldProject が作成される。
```bash
(myvenv) djangogirls>django-admin startproject HelloWorldProject
```


### djangogirlsは自分で作成しフォルダ移動後に実施。
#### 下記コマンドではアプリケーションのフォルダは追加で作られない。 
/djangogirls/mysite が作成される。  
プロジェクト作成時に自分でアプリケーション名を決めてフォルダを作成することが出来る。
```bash
(myvenv) djangogirls>django-admin startproject mysite .
```

## makemigrations
```bash
(myvenv) djangogirls>python manage.py makemigrations
```

## データベースをセットアップする
```bash
(myvenv) djangogirls>python manage.py migrate
```

## ウェブサーバを起動する
```bash
(myvenv) djangogirls>python manage.py runserver
```

## 新しいアプリケーションの作成
```bash
(myvenv) djangogirls>python manage.py startapp blog
```

## データベースにモデルのためのテーブルを作成する
```bash
(myvenv) djangogirls>python manage.py makemigrations blog

↓ 上記のコマンド実施後下記を実施

(myvenv) djangogirls>python manage.py migrate blog
```

## superuser （サイトの全てを管理するユーザー）の作成
```bash
(myvenv) djangogirls>python manage.py createsuperuser
```

# プログラム作成時利用Gitコマンドまとめ
## Gitの開始
```bash
(myvenv) djangogirls>git init
Initialized empty Git repository in ~/djangogirls/.git/

(myvenv) djangogirls>git config --global user.name "Your Name"
(myvenv) djangogirls>git config --global user.email you@example.com
```

## .gitignoreにコミットしないファイルを記載
.gitignore内
```txt
*.pyc
*~
/.vscode
__pycache__
myvenv
db.sqlite3
/static
.DS_Store
```


## git status コマンド
### git statusは、あらゆる追跡されていない/変更されている/ステージされている（untracked/modifed/staged）ファイルや、ブランチの状態などさまざまな情報を返します。
```bash
(myvenv) djangogirls>git status
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
```

## 変更内容を保存します
```bash
(myvenv) djangogirls>git add --all .
(myvenv) djangogirls>git commit -m "My Django Girls app, first commit"
 [...]
 13 files changed, 200 insertions(+)
 create mode 100644 .gitignore
 [...]
 create mode 100644 mysite/wsgi.py
```

## GitHubにコードをプッシュする
```bash
(myvenv) djangogirls>git remote add origin https://github.com/Yoshiyuki-Su/django-samples.git
(myvenv) djangogirls>git push -u origin master
```

# Github等にシークレットキーを公開したくない場合は下記のプログラムを実施する。
```bash
(myvenv) djangogirls>python ./mysite/gen_secrets.py
その後、上記のプログラムで出来る「secrets.json」をバージョン管理対象外(.gitignore)に設定する。
```
