 <body>

 <div id="page">

 <div xmlns="http://www.w3.org/1999/xhtml" class="navheader">

 </div>

 <div xmlns="http://www.w3.org/1999/xhtml" class="chapter" lang="ja" id="export" xml:lang="ja">

 <div xmlns="" class="titlepage">

 <div>

 <div>

 <h2 xmlns="http://www.w3.org/1999/xhtml" class="title"><a id="export"></a>第19章 Export</h2>

 </div>

 </div>

 </div>

 <p>アイテム，インデックスをXMLで表現してExportします．Exportに対応したいアイテムタイプモジュールには，かならず以下の関数を定義してください．</p>

 <div class="section" lang="ja" xml:lang="ja">

 <div xmlns="" class="titlepage">

 <div>

 <div>

 <h2 xmlns="http://www.w3.org/1999/xhtml" class="title" style="clear: both"><a id="export.license"></a>1. ライセンスの合意</h2>

 </div>

 </div>

 </div>

 <p>Exportするにあたりライセンスの合意が必要か否か，およびそのライセンス文をXooNIpsに返す必要があります．アイテムタイプに以下の関数を定義してください．</p>

 <div class="itemizedlist">

 <ul type="disc">

 <li>

 <p>function &lt;モジュール名&gt;GetLicenseRequired ( $item_id )</p>

 <div class="itemizedlist">

 <ul type="circle">

 <li>

 <p>引数 : item_id (アイテム ID)</p>

 </li>

 <li>

 <p>戻り値 : 合意が必要ならtrue</p>

 </li>

 </ul>

 </div>

 </li>

 <li>

 <p>function &lt;モジュール名&gt;GetLicenseStatement ( $item_id )</p>

 <div class="itemizedlist">

 <ul type="circle">

 <li>

 <p>引数 : item_id (アイテム ID)</p>

 </li>

 <li>

 <p>戻り値 : array( ライセンス文, use_cc )．Creative Commonsのライセンスを使用する場合は，ライセンス文をhtmlにしてuse_ccを非falseにする．ライセンスが無い場合は戻り値をNULLにする．</p>

 </li>

 </ul>

 </div>

 </li>

 </ul>

 </div>

 </div>

 <div class="section" lang="ja" xml:lang="ja">

 <div xmlns="" class="titlepage">

 <div>

 <div>

 <h2 xmlns="http://www.w3.org/1999/xhtml" class="title" style="clear: both"><a id="export.detail"></a>2. Detail Information の Export</h2>

 </div>

 </div>

 </div>

 <p>アイテムタイプのDetail InformationをXMLで表現した文字列をファイルに出力します．&lt;DETAIL&gt;で始まり，&lt;/DETAIL&gt;で終わるタグの中に，アイテムタイプ独自のタグを定義できます．</p>

 <div class="itemizedlist">

 <ul type="disc">

 <li>

 <p>function &lt;モジュール名&gt;ExportItem ( $export_path, $fhdl, $item_id, $attachment )</p>

 <div class="itemizedlist">

 <ul type="circle">

 <li>

 <p>引数 : export_path (添付ファイルをエクスポートする時，この引数をxnpExportFileの第1引数に渡してください)</p>

 </li>

 <li>

 <p>引数 : fhdl (出力先ファイルハンドル)</p>

 </li>

 <li>

 <p>引数 : item_id (アイテム ID)</p>

 </li>

 <li>

 <p>引数 : attachment (添付ファイルをExportするならtrue．しないならfalse．)</p>

 </li>

 <li>

 <p>戻り値 : 成功なら true ．失敗なら false ．</p>

 </li>

 </ul>

 </div>

 </li>

 </ul>

 </div>

 <p>以下の関数も参照してください．</p>

 <div class="itemizedlist">

 <ul type="disc">

 <li>

 <p>xnpExportFile</p>

 </li>

 </ul>

 </div>

 </div>

 </div>

 <div xmlns="http://www.w3.org/1999/xhtml" class="navfooter">



 </div>

 </div>

 </body>


