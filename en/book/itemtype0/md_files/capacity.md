

 <body>

 <div id="page">

 <div xmlns="http://www.w3.org/1999/xhtml" class="navheader">

 </div>

 <div xmlns="http://www.w3.org/1999/xhtml" class="chapter" lang="ja" id="capacity" xml:lang="ja">

 <div xmlns="" class="titlepage">

 <div>

 <div>

 <h2 xmlns="http://www.w3.org/1999/xhtml" class="title"><a id="capacity"></a>第17章 アイテム容量</h2>

 </div>

 </div>

 </div>

 <p>システムは，ユーザが作成できるアイテムの数，インデックスの数，アイテムの添付ファイルの総容量を制限します．ユーザが作成したこれらの数量，容量を計算するため，システムは各アイテムタイプにたいしてアイテムの添付ファイルのサイズを要求します．</p>

 <p>アイテムタイプモジュールの以下の関数にこの処理を定義してください．システムがこの関数をコールバックします．</p>

 <div class="itemizedlist">

 <ul type="disc">

 <li>

 <p>function &lt;モジュール名&gt;GetDetailInformationTotalSize( $iids )</p>

 <div class="itemizedlist">

 <ul type="circle">

 <li>

 <p>引数 : $iids (アイテム ID の配列)</p>

 </li>

 <li>

 <p>戻り値 : $iids で指定されるアイテムの添付ファイルの合計</p>

 </li>

 </ul>

 </div>

 <p>$iids にアイテム ID が与えられます．アイテムタイプモジュールでそのアイテム ID に添付されたファイルの容量を求め，その合計を返してください．単位は Byte です．</p>

 </li>

 </ul>

 </div>

 <p>以下の関数も参照してください．</p>

 <div class="itemizedlist">

 <ul type="disc">

 <li>

 <p>xnpGetTotalFileSize</p>

 </li>

 </ul>

 </div>

 </div>

 <div xmlns="http://www.w3.org/1999/xhtml" class="navfooter">

 </div>

 <div class="lastupdated">Last updated: 2010/04/15</div>

 </div>

 </body>

</html>


