# flask_blog
簡易的なブログ投稿サイトです  

# Description
現在は投稿、編集、削除が可能  
  
# Requirement 
* python 3.8.2
* Flask 1.1.2
 
# Usage
## ①プロジェクトの作成
### [application](https://github.com/kamorits/study01/tree/feature/Flaskapp/application)  
リンクからファイルを自分のローカルに準備してください 
### 注意事項 

* pythonのバージョンが自身の環境と違う場合はpipfileの一部を変更することで対応できます  
* vsCodeを利用する場合はpythonのインタプリタを仮想環境に設定する必要があります  
  ※詳細は[Note](#note)を確認してください

## ②pipenvのインストール
```bash
$ pip install pipenv
```

## ③アプリケーションの初期設定
```bash
$ cd ①で配置したディレクトリ
$ pipenv install 
$ pipenv --venv
/Users/username/.local/share/virtualenvs/mypipenv-XXXXXXXX
```
* pipenv installでpipfileを元にライブラリなども含め環境を構築します  
* pipenv --venvで仮想環境のパスが確認できます

## ④仮想環境でのFlaskのインストール
```bash
$ pipenv shell
$ pipenv install Flask
```
* pipenv shellで仮想環境に入ります  
* 仮想環境内でFlaskをインストールしてください

## ⑤アプリケーションの起動
### 環境変数の設定
```bash
$ export FLASK_APP=flask_blog
$ export FLASK_ENV=development
```
* flaskコマンドラインにてアプリケーションを起動するためflask_blogを指定します  
* FLASK_ENVをdevelopmentに設定することで開発モードで実行します

### アプリケーションの起動
```bash
$ flask run
```
* ※server.pyは使用しません


# Note
## pythonのバージョンについて
* アプリケーションは現在python3.8で指定してますが、pipfile内のバージョンを書き換えることで自身の環境に合わせて利用可能です
```:Pipfile
[requires]
python_version = "3.8"
```

## vsCode利用について
### settings.jsonのpythonPath
* 自分の環境に合わせて設定してください
```json:.vscode/settings.json
{
    "python.pythonPath": "/Users/username/.local/share/virtualenvs/mypipenv-XXXXXXXX/bin/python"
}
```

### pylint
* vsCodeの使用なのかpylintエラーが発生するため、pylintrcファイルを用意してます
```:pylintrc
init-hook="./flask_blog"
```

## アプリケーション構成
トップ階層にあるファイル・フォルダの役割は以下のようになります 
- Pipfile/Pipfile.lock  
pythonライブラリの管理ファイル 
- manage.py  
スクリプトの管理ファイル 
- .coveragerc  
テストカバレッジの定義ファイル 
- htmlcov  
テストカバレッジレポートの格納フォルダ 
- flask_blog  
アプリケーションの本体フォルダ

flask_blogフォルダ以下のファイル・フォルダの役割は、以下のようになります
-  __init__.py  
アプリケーションの本体ファイル 
- config.py  
アプリケーションの設定ファイル 
- flask_blog.db  
データベースファイル 
- models  
モデルファイルが格納されるフォルダ 
- scripts  
スクリプト実行ファイルが格納されるフォルダ 
- static  
CSS、JSなどの静的ファイルが格納されるフォルダ 
- templates  
テンプレートファイルが格納されるフォルダ 
- views  
ビューファイルが格納されるフォルダ


 
# Author
* Masashi Kamosida
 
# references
* ゼロからFlaskがよくわかる本: Pythonで作るWebアプリケーション開発入門
* Takatomo Honda