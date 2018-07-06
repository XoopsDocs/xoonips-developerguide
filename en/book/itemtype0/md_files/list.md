 <body>

 <div id="page">

 <div xmlns="http://www.w3.org/1999/xhtml" class="navheader">

 </div>

 <div xmlns="http://www.w3.org/1999/xhtml" class="chapter" lang="ja" id="list" xml:lang="ja">

 <div xmlns="" class="titlepage">

 <div>

 <div>

 <h2 xmlns="http://www.w3.org/1999/xhtml" class="title"><a id="list"></a>第9章 アイテム一覧</h2>

 </div>

 </div>

 </div>

 <p>複数のアイテムを一覧表示する画面に各アイテムの概要を表示します．アイテム一覧画面の一部の小領域が個々のアイテムに割り当てられます．アイテムタイプは割り当てられたその領域に表示する概要を作成します．</p>

 <p>アイテムタイプモジュールの以下の関数にアイテム概要の HTML を生成する処理を定義してください．アイテム一覧表示を行なう際に，システムがこの関数をコールバックします．</p>

 <div class="itemizedlist">

 <ul type="disc">

 <li>

 <p>function &lt;モジュール名&gt;GetListBlock( $item_basic )</p>

 <div class="itemizedlist">

 <ul type="circle">

 <li>

 <p>引数 : $item_basic (アイテムの Basic Information)</p>

 </li>

 <li>

 <p>戻り値 : 概要の HTML</p>

 </li>

 </ul>

 </div>

 </li>

 </ul>

 </div>

 <div class="section" lang="ja" xml:lang="ja">

 <div xmlns="" class="titlepage">

 <div>

 <div>

 <h2 xmlns="http://www.w3.org/1999/xhtml" class="title" style="clear: both"><a id="list.summary"></a>1. アイテム概要の生成</h2>

 </div>

 </div>

 </div>

 <p>一覧表示に必要な HTML を作成します．引数 $item_basic に Basic Information が設定されているので，タイトルなどの Basic Information を表示するにはそちらを参照してください．$item_basic に設定されたアイテム ID を使って Detail Information を取得し，一覧表示に Detail Information を加えることも出来ます．</p>

 </div>

 </div>

 <div xmlns="http://www.w3.org/1999/xhtml" class="navfooter">



 </div>

 </div>

 </body>


