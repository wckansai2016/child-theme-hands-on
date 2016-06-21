# CSSでカスタマイズしてみよう

CSSを編集すれば、カスタマイザーではできない自由なカスタマイズができます。

**※CSSが分かる方は、自由にカスタマイズしてみましょう**

## CSS編集のやりかた（CSS分からない人向け）

最初に作ったstyle.cssにコードを追加していきます。

```
@charset "UTF-8";
/*
Theme Name: Twenty Sixteen child
Template: twentysixteen
*/

/* ここにコードを追加していく。 */
```

では、実際にstyle.cssにコードを追加してみましょう。

## CSSでカスタマイズしてみよう

まずは、以下をコピーして貼り付けてください。
```
.entry-title {
  border-bottom: 3px solid #333;
}
```

すると、ブログ記事本文のタイトルに下線が追加されました。

<img src="https://raw.githubusercontent.com/wckansai2016/child-theme-hands-on/doc/data/images/child-theme-handson-img20.png" width="600px">

「border-bottom」は、下線を追加してくれるCSSプロパティです。

CSSは「ある部分」に対して、スタイルを指定します。

```
/* css基本形 */
セレクタ {プロパティ: 値;}

/* headerという部分に対して、背景色を青にする。 */
header {background-color: blue;}
```

プロパティの種類については覚えるしかないですが、  
セレクタに関しては、調べないと分からない場合があります。

まずは、そのセレクタを調べる方法を紹介します。

例えば、サイドメニューの黒い区切り線を、枠線の青色と同じ色にしたいとします。

<img src="https://raw.githubusercontent.com/wckansai2016/child-theme-hands-on/doc/data/images/child-theme-handson-img21.png" width="600px">

### 1.枠線が何色か調べてみる

ブラウザごとに「開発者ツール」と呼ばれる機能があります。  
以下で開くことができます。

* Chrome:ブラウザ上で右クリック→「検証」
* Firefox:ブラウザ上で右クリック→「要素を調査」
* Internet Explorer: 「F12」をクリック

Chromeの開発者ツール

<img src="https://raw.githubusercontent.com/wckansai2016/child-theme-hands-on/doc/data/images/child-theme-handson-img22.png" width="600px">

また、調べたいところで右クリックをすると、  
開発者ツールでそのタグが選択されます。

今回調べたいのは枠線の色なので、枠線の上で右クリックをし、
開発者ツールを開きます。

<img src="https://raw.githubusercontent.com/wckansai2016/child-theme-hands-on/doc/data/images/child-theme-handson-img23.png" width="600px">

するとbodyが選択された状態になりました。  
枠線と思ってた色は、実はbodyに指定されていた色でした。

さらにCSSの方をみると「body.custom-background」というセレクタに対して、  
「background-color: #1e7bcc;」が指定されているのが分かります。

<img src="https://raw.githubusercontent.com/wckansai2016/child-theme-hands-on/doc/data/images/child-theme-handson-img24.png" width="600px">

青色はカラーコードでいうと「#1e7bcc」というのが分かりました。

### 2.サイトタイトルの色を枠線の色と同じ色にする

次に、1で調べたカラーコードをサイドメニューの区切り線に指定しましょう。

どのセレクタに指定すればいいかは、1でやったのと同じ要領で、  
区切り線上で右クリックします。

<img src="https://raw.githubusercontent.com/wckansai2016/child-theme-hands-on/doc/data/images/child-theme-handson-img25.png" width="600px">

すると、sectionタグについた「widget」というclassに、  
「border-top: 4px solid #1a1a1a;」が指定されているのが分かります。  
（stylesタブを下に少しスクロールするとあります）

この#1a1a1aが枠線に指定されている黒のカラーコードです。

開発者ツールを使えば、ブラウザ上でスタイルの変更を確認できます。

<img src="https://raw.githubusercontent.com/wckansai2016/child-theme-hands-on/doc/data/images/child-theme-handson-img26.png" width="600px">

変更したいところをクリックすると、編集ができて、  
先ほど調べたカラーコード「#1e7bcc」に変更すると...

<img src="https://raw.githubusercontent.com/wckansai2016/child-theme-hands-on/doc/data/images/child-theme-handson-img27.png" width="600px">

ブラウザ上で色が変わりました。

ただ、これでstyle.cssが変更された訳ではないので、  
同じコードをstyle.cssにも書きます。

```
.widget {
  border-top: 4px solid #1e7bcc;
}
```

保存してブラウザをリロードすると、色が変わっているはずです。

CSSでカスタマイズをする時は、  
カスタマイズしたいところにどんなCSSが指定されているかを調べて、  
上書きの繰り返しとなります。

### 3.本文中の2カラムを1カラムに

記事本文と、記事を書いた日付が横並びになっているところを、  
縦に並べてみましょう。

before

<img src="https://raw.githubusercontent.com/wckansai2016/child-theme-hands-on/doc/data/images/child-theme-handson-img28.png" width="600px">

after

<img src="https://raw.githubusercontent.com/wckansai2016/child-theme-hands-on/doc/data/images/child-theme-handson-img29.png" width="600px">

普段、CSSを触っていない人にとっては少し難しいかもしれませんが、  
要領は先ほどと同じです。

もし分からなかった時のコードは下の方に掲載しています。

### 4.時間があれば、自由にカスタマイズしましょう。

時間があれば、カスタマイザーやCSSを使って、自由にカスタマイズしてみましょう。

#### サンプルコード

CSSはちょっと分からないという方は、  
コードをコピーして変化を確認してみるといいかもです。

上の余白
```
.site-header {
  padding-top: 40px;
}
```

サイドバーのリスト
```
.widget li {
  list-style: none;
}
```

ロゴ
```
.site-branding .site-title a {
  color: #1e7bcc;
  font-size: 40px;
}
```

メインビジュアル
```
.site-header {
  padding-left: 0;
  padding-right: 0;
}

.site-header-main {
  padding: 0 4.5455%;
}

.header-image img {
  width: 100%;
}
```

記事本文中を、2カラムから1カラムに
```
body:not(.search-results) article:not(.type-page) .entry-content {
  float: inherit;
  width: 100%;
}

body:not(.search-results) article:not(.type-page) .entry-footer {
  float: inherit;
  width: 100%;
  margin-top: 40px;
  margin-right: 0;
  margin-left: 0;
}

.entry-content {
  margin-left: 0;
  margin-right: 0;
}
```
