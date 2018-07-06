 <body>

 <div id="page">

 <div xmlns="http://www.w3.org/1999/xhtml" class="navheader">

 </div>

 <div xmlns="http://www.w3.org/1999/xhtml" class="chapter" lang="ja" id="print" xml:lang="ja">

 <div xmlns="" class="titlepage">

 <div>

 <div>

 <h2 xmlns="http://www.w3.org/1999/xhtml" class="title"><a id="print"></a>第12章 アイテム詳細印刷用画面</h2>

 </div>

 </div>

 </div>

 <p>アイテムの情報を印刷に適した形式に整形した HTML を作成します．</p>

 <p>アイテムタイプモジュールの以下の関数に処理を定義してください．システムは印刷用画面が必要なときこの関数をコールバックします．</p>

 <div class="itemizedlist">

 <ul type="disc">

 <li>

 <p>function &lt;モジュール名&gt;GetPrinterFriendlyDetailBlock( $item_id )</p>

 <div class="itemizedlist">

 <ul type="circle">

 <li>

 <p>引数 : アイテム ID</p>

 </li>

 <li>

 <p>戻り値 : 印刷用の HTML</p>

 </li>

 </ul>

 </div>

 </li>

 </ul>

 </div>

 <p>以下の項目も参照してください．</p>

 <div class="itemizedlist">

 <ul type="disc">

 <li>

 <p>xnpGetBasicInformationPrinterFriendlyBlock</p>

 </li>

 <li>

 <p>xnpGetPreviewPrinterFriendlyBlock</p>

 </li>

 <li>

 <p>xnpGetAttachmentPrinterFriendlyBlock</p>

 </li>

 <li>

 <p>xnpGetTextFilePrinterFriendlyBlock</p>

 </li>

 <li>

 <p>xnpGetRightsPrinterFriendlyBlock</p>

 </li>

 <li>

 <p>xnpGetIndexPrinterFriendlyBlock</p>

 </li>

 </ul>

 </div>

 </div>

 <div xmlns="http://www.w3.org/1999/xhtml" class="navfooter">

 </div>

 </div>

 </body>




