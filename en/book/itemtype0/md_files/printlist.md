 <body>

 <div id="page">

 <div xmlns="http://www.w3.org/1999/xhtml" class="navheader">

 </div>

 <div xmlns="http://www.w3.org/1999/xhtml" class="chapter" lang="ja" id="printlist" xml:lang="ja">

 <div xmlns="" class="titlepage">

 <div>

 <div>

 <h2 xmlns="http://www.w3.org/1999/xhtml" class="title"><a id="printlist"></a>第10章 アイテム一覧印刷用画面</h2>

 </div>

 </div>

 </div>

 <p>アイテムの情報を印刷に適した形式に整形した HTML を作成します．</p>

 <p>アイテムタイプモジュールの以下の関数に処理を定義してください．システムは一覧印刷用画面が必要なときこの関数をコールバックします．</p>

 <div class="itemizedlist">

 <ul type="disc">

 <li>

 <p>function &lt;モジュール名&gt;GetPrinterFriendlyListBlock( $item_basic )</p>

 <div class="itemizedlist">

 <ul type="circle">

 <li>

 <p>引数 : $item_basic (アイテムの Basic Information)</p>

 </li>

 <li>

 <p>戻り値 : 印刷用の HTML</p>

 </li>

 </ul>

 </div>

 </li>

 </ul>

 </div>

 </div>

 <div xmlns="http://www.w3.org/1999/xhtml" class="navfooter">

 </div>

 </div>

 </body>



