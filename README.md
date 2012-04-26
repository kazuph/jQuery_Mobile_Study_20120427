jQuery Mobileで</br>やるスマフォ最適化
============
@kazuph

2012/04/27

自己紹介
------------
 * @kazuph
 * 2年目エンジニア
 * 使用言語：
  * 主にPerl(そんなころもありました)
  * 今はJava(Android), Objective-C(iPhone)
  * 仕事以外では何故かJavaScript(Processing.js, easelJS)
 * 仕様エディタ:
  * Vim(EclipseとXcodeのキーバインドも当然Vim)
 * 成果物:
  * [全体会議用タイマー](https://github.com/kazuph/TeiClock)
  * [Unity疾走アプリ：CADash!](http://www.tspaa.jp/nominate.html)
  * [International Space Apps Challenge Tokyo 提出作品：LinkAStar(第2位！)](http://fumit.blogspot.jp/2012/04/international-space-app-challenge-nasa.html)

提供
--------------
 * impress.js
  * [https://github.com/bartaz/impress.js/](https://github.com/bartaz/impress.js/)
 * markdown2impress
  * https://github.com/yoshiki/markdown2impress
 * 実際にはこれらを書き換えて使っていますYO( ･`д･´)


Agenda（15分）
----------------
 * jQM(jQuery Mobile)ってなに？
 * どこがすごいの？
 * なにがダメなの？
 * じゃあどうすればいいの？

jQuery Mobile
=====================
beyonde bad know-how
![jQuery Mobile](http://jquerymobile.com/wp-content/uploads/2011/06/jquery-mobile-devices-beta.png)

概要
------------------
 * 簡単にスマフォ向けのデザインを適用できる
 * 簡単にスマフォアプリみたいな挙動を付加するすることができる
 * HTMLの初心者でもある程度簡単に実装が可能
 * ※ただしCSSとJSの知識がないと60点のサイトしかつくれない→まさに俺

スマフォ向けデザイン
------------------
 * スマフォでの利便性

デザイン
------------------
 * ヘッダ・フッタ
 * リスト
 * ダイアログ
 * 他にも超たくさん
 * [本家サイトによるDEMO](http://jquerymobile.com/demos/1.1.0/)

導入方法
------------------
```
<!-- 以下をheadに追加 -->
<link rel="stylesheet" href="http://code.jquery.com/mobile/1.1.0/jquery.mobile-1.1.0.min.css" />
<script src="http://code.jquery.com/jquery-1.6.4.min.js"></script>
<script src="http://code.jquery.com/mobile/1.1.0/jquery.mobile-1.1.0.min.js"></script>
```

魔法の呪文(Zencoding)
-----------------
```
html:5>div[data-role=page]>(div[data-role=header][data-position=fixed]>h1{jQueryMobile}))+(ul[data-role=listview]>li[data-role=list-divider]{HOGE}+li*30>legend+a{(」・ω・)」うー！(／・ω・)／にゃー！}>img[src=praykazu.png][width=100px])+(div[data-role=footer][data-position=fixed]>h1{I am Footer})
```

魔法の呪文(Zencoding)
-----------------

  * スマフォらしい挙動
   * スライド
   * 移動するヘッダ（6min）
  * デザインおえー
   * 見た目がどれも一緒じゃない？
   * デザインロール
    * CSS適用
    * 実際に弊社のプロダクト紹介（10min)
    * 他jQMを使っているサイト
  * 挙動おえー
    * とりあえずajax-false?
    * 他に使えそうな便利な関数紹介
    * Ajaxの時につかう、デザイン適用関数
  * なんか最後に面白そうな話（20min）

jQMの注意点
------------------



Ajaxを使わないようにする方法もあるが…
------------------
 * 設定方法
```
jQuery(document).bind("mobileinit", function(){
```
```
　　jQuery.mobile.ajaxEnabled = false;
```
```
　　jQuery.mobile.ajaxLinksEnabled = false;
```
```
　　jQuery.mobile.ajaxFormsEnabled = false;
```
```
　　jQuery.mobile.hashListeningEnabled = false;
```
```
});
```
 * 実際にはもっとちゃんとした解決策がある（らしい）
  *

便利ツール
------------------
[GUIでコーディングできる『Codiqa』](http://www.codiqa.com/)
![Codiqa](http://codiqa.com/static/images/v3/home/cta_image_right_builder.png)
[GUIでcssを変更できる『ThemeRoller for jQuery Mobile』](http://jquerymobile.com/themeroller/)

