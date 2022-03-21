# Flutterに関するメモ

## 環境構築
以下に環境構築の手順を記載する。  
基本的に [公式の手順](https://docs.flutter.dev/get-started/install/macos#update-your-path) に沿って環境構築をする。

### FlutterSDKの入手
以下からOSにあったstableのFlutterSDKをダウンロードする。  
* [Get the Flutter SDK](https://docs.flutter.dev/get-started/install/macos#get-sdk)

ダウンロードしたFlutterSDK(zipファイル)を以下のように解凍する。

```
$ cd ~/development
$ unzip ~/Downloads/flutter_macos_2.10.3-stable.zip
```

※ `~/development`がなければ自分で作成する。


### Flutterのパスを通す

```
$ export PATH="$PATH:`pwd`/flutter/bin"
```

上記の場合だと、現在開いているTerminalのみパスが通ルため、永続的にパスを通す必要がある。
永続的にパスを通す方法は以下である。

何のシェルを使用しているかを確認する。

```
$ echo $SHELL
```

* Bashを使用している場合: `$HOME/.bash_profile` もしくは`$HOME/.bashrc`を編集する。
* Z shellを使用している場合: `$HOME/.zshrc`を編集する。

上記のファイルに以下を記載する。

```
export PATH="$PATH:$HOME/development/flutter/bin"
```

編集したパスを有効にする。
```
$ source $HOME/.<rc file>
```

PATHにFlutterのパスがあれば成功である。
```
$ echo $PATH
```

Flutterコマンドが使えるかの確認をする。
```
$ which flutter
````

dartのパスを同様に通る。
```
$ which flutter dart
````
  
### Flutterプロジェクトの作成

以下のコマンドでFlutterプロジェクトを作成する。 
```
$ flutter create my_app
```

### .gitignoreの追加

[.gitignoreの中身はこれを参考にする](https://github.com/nowvilla-physi/flutter-tutorial/blob/master/.gitignore)


## コマンド集

プロジェクトのクリーン
```
$ flutter clean
```

繋がっている端末の確認
```
$ flutter devices
```

iOSのプロダクト版でのビルド
```
$ flutter build ios --release
```

プロダクト版での実行
```
$ flutter run --release
```

iOSのプロダクト版でのビルド
```
$ flutter build ios --release
```

Androidのプロダクト版のバンドル作成  
`/build/app/outputs/bundle/release/xxxx.aab`に出力される。
```
$ flutter build appbundle
```

freezedによる自動生成
```
$ flutter pub run build_runner build --delete-conflicting-outputs
```

## アプリリリース

### 各アプリをストアに登録する手順

#### 1. AppIDの登録

* apple developerの「Identifiers」の「＋」ボタンをクリックする。
* `Register a new identifier > App IDs`にチェックが入っていることを確認して「Countine」ボタンをクリックする。
* `Register a new identifier > Select a type > App`を選択して「Countine」ボタンをクリックする。
* 以下の項目を埋めて、「Register」ボタンをクリックする。
    * `Description`: 任意の文字列(XXXXXX YYYYYY ZZZZZZ)
    * `Bundle ID`: アプリのパッケージ名を入れる。(com.physi.nowvilla.xxxxYyyyZzzz)

#### 2.Profileの作成

* apple developerの「Profile」の「＋」ボタンをクリックする。
* `App Store`にチェックを入れて「Countine」ボタンをクリックする。
* `Generate a Provisioning Profile > Select Certificates`でチェックして「Continue」ボタンをクリックする。
* `Provisioning Profile Name`に「XXXXXX YYYYYY Profile」と入力して「Generate」ボタンをクリックする。
* 「Download」をクリックして、ダウンロードしたファイルをダブルクリックする。
    * Xcodeに自動で設定される。

#### 3.App Store Connectにアプリを追加

* [App Store Connect](https://appstoreconnect.apple.com/) にアクセスする。
* `My App`をクリックして、App横の「＋」ボタンをクリックする。
* 「新規App」をクリックする。
* 以下の項目を入力して「作成」ボタンをクリックする。
  * 名前: アプリの名前
  * プライマリ言語: 日本語
  * バンドルID: 手順1で追加してものを選択する。
  * SKU: バンドルIDと同じで良い。
  * ユーザアクセス: アクセス制限なし

### 必要な端末のスクショ

#### iOS

* 6.5インチ: iPhone 11 Pro Max
* 5.5インチ: iPhone 8 Plus
* 12.9インチ: iPad Pro 5th
* 12.9インチ: iPad Pro 5th

#### Android

TODO
