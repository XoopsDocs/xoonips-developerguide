 <body>

 <div id="page">

 <div xmlns="http://www.w3.org/1999/xhtml" class="chapter" lang="ja" id="delete" xml:lang="ja">

 <div xmlns="" class="titlepage">

 <div>

 <div>

 <h2 xmlns="http://www.w3.org/1999/xhtml" class="title"><a id="delete"></a>第13章 アイテム削除</h2>

 </div>

 </div>

 </div>

 <p>アイテムタイプモジュールの以下の関数に削除処理を定義してください．システムはアイテムを削除するときこの関数をコールバックします．</p>

 <div class="itemizedlist">

 <ul type="disc">

 <li>

 <p>function &lt;モジュール名&gt;DeleteItem( $item_id )</p>

 <div class="itemizedlist">

 <ul type="circle">

 <li>

 <p>引数 : アイテム ID</p>

 </li>

 <li>

 <p>戻り値 : true (成功)，false (失敗)</p>

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

 <h2 xmlns="http://www.w3.org/1999/xhtml" class="title" style="clear: both"><a id="delete.basic"></a>1. Basic Information の削除</h2>

 </div>

 </div>

 </div>

 <p>共通ライブラリに削除関数が定義されているのでそれを呼び出します．</p>

 </div>

 <div class="section" lang="ja" xml:lang="ja">

 <div xmlns="" class="titlepage">

 <div>

 <div>

 <h2 xmlns="http://www.w3.org/1999/xhtml" class="title" style="clear: both"><a id="delete.detail"></a>2. Detail Information の削除</h2>

 </div>

 </div>

 </div>

 <p>削除処理はアイテムタイプが独自に定義します．共通ライブラリの機能を利用して登録した画像，添付ファイル，テキスト，インデックスは明示的に削除する必要はありません (Basic Information の削除と同時に削除されます)． </p>

 <p>以下の項目も参照してください．</p>

 <div class="itemizedlist">

 <ul type="disc">

 <li>
 <p>xnpDeleteBasicInformation</p>

 </li>

 </ul>

 </div>

 </div>

 </div>

 <div xmlns="http://www.w3.org/1999/xhtml" class="navfooter">



 </div>

 </div>

 </body>
