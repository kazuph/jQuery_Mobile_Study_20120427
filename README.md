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

jQuery Mobile
=====================
beyonde bad know-how
![jQuery Mobile](http://jquerymobile.com/wp-content/uploads/2011/06/jquery-mobile-devices-beta.png)

Agenda（15分）
----------------
 * jQM(jQuery Mobile)(5分)
 * スタートアップガイド
 * 60点のその先

jQM
==============

jQM(jQuery Mobile)とは
------------------
 * スマフォのために用意されたjQuery製のフレームワーク
 * 簡単にスマフォアプリのような外観と挙動を付加するすることができる
  * ボタンやフォームなどがスマフォでのタッチ操作に最適化されている
 * HTMLの初心者でもある程度までの実装が容易
 * サポートされているプラットフォームが多い
  * ※ただしCSSとJSの知識がないと60点のサイトしかつくれない

デザイン & UI
------------------
 * ヘッダ・フッタ
 * リスト
 * ダイアログ
 * スライド
 * 他にも超たくさん
 * [本家サイトによるDEMO](http://jquerymobile.com/demos/1.1.0/)
 * [jQM1.1の新機能](http://screw-axis.com/2012/04/20/jquery-mobile-1-1-0/)
 * [国内での適用事例](http://ascii.jp/elem/000/000/674/674677/)

スタートアップガイド
==================

導入方法
------------------
 * 以下をheadに追加
<script src="https://gist.github.com/2501207.js?file=gistfile1.txt"></script>

魔法の呪文(Zencoding)
-----------------
<script src="https://gist.github.com/2501353.js?file=gistfile1.html"></script>

※書いててZencoding使えない人にはなんの意味もないことに気づいたw

[生成されるCODE](https://gist.github.com/2504014)

jQM初期設定
---------------
<script src="https://gist.github.com/2504175.js?file=gistfile1.html"></script>

DEMO
--------------

レイアウトを作成する便利ツール
------------------
[GUIでコーディングできる『Codiqa』](http://www.codiqa.com/)
![Codiqa](http://codiqa.com/static/images/v3/home/cta_image_right_builder.png)

ほら簡単でしょ？
--------------

でもデザインが・・・
-----------------
 * HTMLしかいじれないとどれも同じ見た目になってしまう
 * でもデザイン性のあるCSSを書くのは敷居が高い
  * デザインロールという解決策もある
   * [GUIでcssを変更できる『ThemeRoller for jQuery Mobile』](http://jquerymobile.com/themeroller/)

60点のその先
================
 * その先のデザイン
 * バッドノウハウを犯す前に・・・

独自にCSSを適用する
-----------------
 * 実際に弊社のプロダクトの変わっていく様

伝家の宝刀<br/>でーたえーじゃっくすふぉーるす！
------------------
 * jQMを使うとしばしばよくわからないバグが発生する
  * jQueryMobileでAjaxスライドする実装をしたら元々動いていたjsがbindされまくって挙動がおかしくなる
 * 何かJSでトラブってたらとりあえずaタグやformに以下を追加・・・?
```
data-ajax="false"
```
 * 問題がこれで解消されることが多いが根本的な解決になっていない
 * スライド遷移が使えなくなるのでjQMらしさがそこなわれる
 * jQMを使う意味を見失う

そもそもAjaxを使わないようにする方法もあるが…
------------------
 * 設定方法
```
jQuery(document).bind("mobileinit", function(){
　　jQuery.mobile.ajaxEnabled = false;
});
```
もっと根本的に解決したい！

jQMでのルールを覚える
-----------------
 * jQueryMobile != jQuery
 * jQM用に用意されたメソッド(関数｜手段)がたくさんあるよ！
  * Ajax遷移が完了したら実行される[関数](http://d.hatena.ne.jp/pikotea/20120405/1333631161)
```
$(document).delegate('#page1',  'pageshow',  function(){
///
});
```
  * Ajaxで要素を追加するときに、jQMのcssを適用する[関数](http://hisasann.com/housetect/2011/06/jquerymobile_1.html)
  * 画面を予め読み込んでおく関数
  * 生成されたDOMをキャッシュしておく関数

続きはWebで!
--------------------
 * 4/13に[最新のjQMに対応している説明資料](http://msto.jp/th2/)があった(^q^)
 * [日本語リファレンス](http://dev.screw-axis.com/doc/jquery_mobile/)もかなり充実



Any Questions?
================
