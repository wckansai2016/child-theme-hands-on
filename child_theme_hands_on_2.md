# カスタマイザーで カスタマイズしてみよう

カスタマイザーを使えば、管理画面から簡単なカスタマイズをすることができます。  
CSSを修正する必要もありません。

カスタマイザーの変更は、親テーマのアップデートに影響されません。  
また、カスタマイザーで変更できる内容はテーマによって違います。

## カスタマイザーを使ってみよう。

実際にカスタマイザーでカスタマイズしてみましょう。

「管理画面 > 外観」からカスタマイズをクリック。

この画面が表示されたら準備OKです。

<img src="https://raw.githubusercontent.com/wckansai2016/child-theme-hands-on/doc/data/images/child-theme-handson-img4.png" width="600px">

#### やること

* ヘッダー画像を追加してみよう
* Twentysixteenの枠線の色を変更

### 1.ヘッダー画像を追加してみよう

カスタマイザー左メニューの「ヘッダー画像」を選択。

<img src="https://raw.githubusercontent.com/wckansai2016/child-theme-hands-on/doc/data/images/child-theme-handson-img5.png" width="600px">

「新規画像を追加」をクリックすると、「画像選択」が表示されます。

[サンプル画像](https://github.com/wckansai2016/child-theme-hands-on/blob/doc/data/images/wc-head.jpg)をドラッグ&ドロップでアップロードします。


アップロードした画像を選択し、「選択して切り抜く」をクリックします。
<img src="https://raw.githubusercontent.com/wckansai2016/child-theme-hands-on/doc/data/images/child-theme-handson-img6.png" width="600px">

画像切り抜き画面で、切り抜きの位置や、切り抜きサイズを変更して、  
「画像切り抜き」をクリックします。

<img src="https://raw.githubusercontent.com/wckansai2016/child-theme-hands-on/doc/data/images/child-theme-handson-img7.png" width="600px">

ヘッダー画像を追加できました！

<img src="https://raw.githubusercontent.com/wckansai2016/child-theme-hands-on/doc/data/images/child-theme-handson-img8.png" width="600px">

ヘッダー画像を指定する場合、PHPファイルやCSSを編集する必要がありますが、
カスタマイザーを使えば簡単に設定できます。

変更に問題なければ、「保存」ボタンを忘れずに押しましょう。

### 2.Twentysixteenの枠線の色を変更

次に、Twentysixteenの特徴である枠線の色を変えてみましょう。

カスタマイザー左メニューの「色」を選択

<img src="https://raw.githubusercontent.com/wckansai2016/child-theme-hands-on/doc/data/images/child-theme-handson-img9.png" width="600px">

開くと、背景色やリンク色、テキストカラーを編集できることが分かります。

Twentysixteenの枠線の色は「背景色」の設定で変更できます。

<img src="https://raw.githubusercontent.com/wckansai2016/child-theme-hands-on/doc/data/images/child-theme-handson-img10.png" width="600px">

背景色の「色を選択」をクリックすると、  
カラーピッカーや16進数で色を設定するところが出てきます。

カラーピッカーを使って、好きな色に変更してみましょう。

<img src="https://raw.githubusercontent.com/wckansai2016/child-theme-hands-on/doc/data/images/child-theme-handson-img11.png" width="600px">

サンプルではWordCamp Kansai 2016のサイトに合わせて青にしてみました。

CSSで変更する必要がある色もカスタマイザーで簡単に変更できます。

※このハンズオンの進行上、白以外の色でお願いします。

### 3.メニューの追加

カスタマイザーでメニューを追加することもできます。  
Webサイトの上部によくあるナビゲーションのようなものです。

カスタマイザー左メニューの「メニュー」を選択。

初期状態ではメニューの設定がないので、  
「メニューを追加」選択します。

<img src="https://raw.githubusercontent.com/wckansai2016/child-theme-hands-on/doc/data/images/child-theme-handson-img12.png" width="600px">

テキスト入力エリアにメニュー名を入力して「メニューを作成」をクリック。  
今回はメニュー名を「navigation」としています。

<img src="https://raw.githubusercontent.com/wckansai2016/child-theme-hands-on/doc/data/images/child-theme-handson-img13.png" width="600px">

次に作ったメニューに追加する項目を選びます。

今回は「ホーム」とサンプルで用意されている「サンプル」という固定ページを追加しましょう。

<img src="https://raw.githubusercontent.com/wckansai2016/child-theme-hands-on/doc/data/images/child-theme-handson-img14.png" width="600px">

追加後、カスタマイザーのメニューに戻ると今作った「navigation」というメニューが作られています。

<img src="https://raw.githubusercontent.com/wckansai2016/child-theme-hands-on/doc/data/images/child-theme-handson-img15.png" width="600px">

今はメニューを作った段階なので、これを実際に配置します。

「メニューの位置」を選択してください。  
そして、メインメニューで「navigation」を選択します。

<img src="https://raw.githubusercontent.com/wckansai2016/child-theme-hands-on/doc/data/images/child-theme-handson-img16.png" width="600px">

すると、右上にメニューが追加されました。

<img src="https://raw.githubusercontent.com/wckansai2016/child-theme-hands-on/doc/data/images/child-theme-handson-img17.png" width="600px">



### 4.PC・タブレット・スマートフォンでの表示確認

カスタマイザー上でPC、タブレット、スマートフォンでの表示を確認することができます。

左下にあるアイコンから切り替えできます。  
PC表示は今まで見てきたものです。

タブレットを選択するとこうなります。

<img src="https://raw.githubusercontent.com/wckansai2016/child-theme-hands-on/doc/data/images/child-theme-handson-img18.png" width="600px">

メニューの表示が変わりましたね。  
メニューボタンをクリックすると、メニューが表示されます。

次に、スマートフォンを選択するとこうなります。

<img src="https://raw.githubusercontent.com/wckansai2016/child-theme-hands-on/doc/data/images/child-theme-handson-img19.png" width="600px">

スマートフォンでは枠線が消えました。


カスタマイザーを使えば、CSSを使わなくても簡単にカスタマイズできますね。

冒頭でも書きましたが、カスタマイザーでの変更は親テーマのアップデートに影響されないので安心です。

## CSSで カスタマイズしてみよう

次はCSSでカスタマイザーではできないカスタマイズをしてみます。
