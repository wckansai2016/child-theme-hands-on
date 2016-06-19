# 1. 子テーマを作ってみよう

子テーマを作るのに必要なものは3つだけ

* 1-1.子テーマフォルダの作成
* 1-2.style.cssの作成
* 1-3.functions.phpの作成

## 1-1.子テーマフォルダの作成

themeディレクトリ以下に子テーマ用フォルダを作成

```
* themes
  * twentysixteen
  + twentysixteen-child （追加）
```

### 子テーマフォルダを作る際の注意点

子テーマフォルダを作る際にいくつか注意点があります。

#### テーマ名は他のテーマと被らないようにしましょう

既にWordPressの公式テーマディレクトリに公開されているテーマ名とかぶった場合、  
そのテーマのアップデート通知がくる場合があります。

うっかり更新してしまうと、テーマがごそっと切り替わってしまうので注意しましょう。

[テーマディレクトリ](https://ja.wordpress.org/themes/)の「テーマを検索...」から、  
テーマ名を検索して既に存在しているかどうか調べましょう。

#### テーマ名の末尾に「-child」をつけることが推奨されています。

[WordPress Codexの子テーマのページ](https://wpdocs.osdn.jp/%E5%AD%90%E3%83%86%E3%83%BC%E3%83%9E#.E5.AD.90.E3.83.86.E3.83.BC.E3.83.9E.E3.81.AE.E4.BD.9C.E3.82.8A.E6.96.B9)で、末尾に「-child」をつけることが推奨と記載されています。

ただし、必須ではありません。  
例えば、作った子テーマを公式テーマディレクトリに申請したい場合は自由につけてOKです。

#### テーマのフォルダ名に空白は入れないように

空白を入れてしまうと、エラーになります。

テーマ名に空白を入れる場合は、フォルダ名では空白を、- （ハイフン）で繋ぎましょう。

```
× twentysixteen child
◯ twentysixteen-child
```
## 1-2.style.cssの作成

次に、style.cssを作りましょう

```
* themes
  * twentysixteen
  * twentysixteen-child
    + style.css （追加）
```

style.cssには以下を書きます。

```
/*
 Theme Name: 子テーマ名
 Template: 親テーマのディレクトリ名
*/
```

今回は「Twentysixteen」を親テーマにするので、  
以下を追記しましょう。

```
/*
 Theme Name: Twenty Sixteen Child
 Template: twentysixteen
*/
```

この状態でも子テーマを有効化することはできます。  
が、CSSが全く効いていない状態で表示されます。

そこで、functions.phpを作って、親テーマのCSSを読み込みます。

## 1-3.functions.phpの作成

さいごに、functions.phpを作ります。

```
* themes
  * twentysixteen
  * twentysixteen-child
    * style.css
    + functions.php （追加）
```

functions.phpでは親テーマのstyle.cssを読み込むコードを書きます。

```
<?php
add_action( 'wp_enqueue_scripts', 'theme_enqueue_styles' );
function theme_enqueue_styles() {
  wp_enqueue_style( ‘parent-style’,
    get_template_directory_uri() . '/style.css'
  );
}
```

このコードを書くと、親テーマのstyle.cssを読み込んだ後に、  
子テーマのstyle.cssを自動的に読み込みます。

もし、子テーマのstyle.cssが読み込まれない場合は、  
子テーマを読み込むコードも追加します。

```
<?php
add_action( 'wp_enqueue_scripts', 'theme_enqueue_styles' );
function theme_enqueue_styles() {
  wp_enqueue_style( 'parent-style',
  get_template_directory_uri() . '/style.css' );
  wp_enqueue_style( 'child-style',
  get_stylesheet_directory_uri() . '/style.css', array('parent-style')
  );
}
```

ちなみに、ネット上ではstyle.cssで親テーマのstyle.cssを  
読み込む方法が紹介されていることがありますが、今は**非推奨**です。


```
/*
 Theme Name: Twenty Sixteen Child
 Template: twentysixteen
*/
@import url( '../twentysixteen/style.css' );
```

## 子テーマを有効化！

「管理画面 > 外観 > テーマ」から、「Twenty Sixteen Child」の有効化をクリック。  

<img src="https://raw.githubusercontent.com/wckansai2016/child-theme-hands-on/doc/data/images/child-theme-handson-img1.png" width="600px">

有効化したらサイトの確認をしましょう。

## 試しに投稿

[サンプルテキスト](https://github.com/wckansai2016/child-theme-hands-on/blob/doc/data/text/dummytext.md)

[サンプル画像](https://github.com/wckansai2016/child-theme-hands-on/blob/doc/data/images/wc-thumbnail.png)

## ※親テーマのインストールについて

作ったテーマのアップロードの方法は2つあります。  
その方法によって親テーマが自動的にインストールされる場合とされない場合があります。

### 1.管理画面からzipファイルをアップロードする方法

管理画面の「外観 > テーマ > 新規追加 > テーマのアップロード」から、
zipファイルにした子テーマをアップロードする場合は、親テーマがなくても自動的にインストールされます。

<img src="https://raw.githubusercontent.com/wckansai2016/child-theme-hands-on/doc/data/images/child-theme-handson-img2.png" width="600px">

### 2.FTPでアップロードする方法

サーバーのthemesフォルダ内に子テーマをアップロードする方法です。  
この方法は親テーマを自分でインストールしておく必要があります。

親テーマがないとエラーがでます。

<img src="https://raw.githubusercontent.com/wckansai2016/child-theme-hands-on/doc/data/images/child-theme-handson-img3.png" width="600px">

このハンズオンで紹介している手順は、ローカル環境で2の方法をやっているようなものなので、親テーマのインストールが必要です。

## カスタマイザーで カスタマイズしてみよう

次はカスタマイザーを使ってカスタマイズしてみます。

[カスタマイザーで カスタマイズしてみよう](https://github.com/wckansai2016/child-theme-hands-on/blob/doc/child_theme_hands_on_2.md)
