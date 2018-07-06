 <body>

 <div id="page">

 <div xmlns="http://www.w3.org/1999/xhtml" class="navheader">

 </div>

 <div xmlns="http://www.w3.org/1999/xhtml" class="chapter" lang="ja" id="module_top" xml:lang="ja">

 <div xmlns="" class="titlepage">

 <div>

 <div>

 <h2 xmlns="http://www.w3.org/1999/xhtml" class="title"><a id="module_top"></a>第18章 XooNIpsモジュールのトップ画面</h2>

 </div>

 </div>

 </div>

 <p>XooNIpsモジュールのトップ画面の一部の小領域が個々のアイテムタイプに割り当てられます．

 アイテムタイプは割り当てられたその領域に表示するブロックを作成します．</p>

 <p>アイテムタイプモジュールの以下の関数にこの処理を定義してください．システムがこの関数をコールバックします．</p>

 <div class="itemizedlist">

 <ul type="disc">

 <li>

 <p>function &lt;モジュール名&gt;GetTopBlock( $itemtype )</p>

 <div class="itemizedlist">

 <ul type="circle">

 <li>

 <p>引数 : $itemtype (以下のキーを含む連想配列． item_type_id, mid, name, displayname, viewphp)</p>

 </li>

 <li>

 <p>戻り値 : アイテムタイプの概要を表す HTML</p>

 </li>

 </ul>

 </div>

 <p>XooNIpsモジュールのトップ画面に表示すべき HTML を作成して返してください．</p>

 </li>

 </ul>

 </div>

 <p>以下の関数も参照してください．</p>

 <div class="itemizedlist">

 <ul type="disc">

 <li>

 <p>xnpGetTopBlock</p>

 </li>

 </ul>

 </div>

 </div>

 <div xmlns="http://www.w3.org/1999/xhtml" class="navfooter">



 </div>

 </div>

 </body>




