<body>

 <div id="page">

 <div xmlns="http://www.w3.org/1999/xhtml" class="navheader">

 </div>

 <div xmlns="http://www.w3.org/1999/xhtml" class="chapter" lang="ja" id="metainfo" xml:lang="ja">

 <div xmlns="" class="titlepage">

 <div>

 <div>

 <h2 xmlns="http://www.w3.org/1999/xhtml" class="title"><a id="metainfo"></a>第14章 メタ情報</h2>

 </div>

 </div>

 </div>

 <p>システムはユーザからの添付ファイルのダウンロード要求に対して，添付ファイルが属するアイテムの情報 (メタ情報) と添付ファイルを含んだ ZIP 書庫ファイルを出力します．</p>

 <p>このときシステムはアイテムタイプモジュールに対してメタ情報を要求します．</p>

 <p>アイテムタイプモジュールの以下の関数にメタ情報作成処理を定義してください． </p>

 <div class="itemizedlist">

 <ul type="disc">

 <li>

 <p>function &lt;モジュール名&gt;GetMetaInformation ( $item_id )</p>

 <div class="itemizedlist">

 <ul type="circle">

 <li>

 <p>引数 : アイテム ID</p>

 </li>

 <li>

 <p>戻り値 : メタ情報 (Basic Information と Detail Information の両方を含む)の連想配列</p>

 <div class="itemizedlist">

 <ul type="square">

 <li>

 <p>連想配列の構造は以下の通りです．</p>

 <div class="blockquote">

 <blockquote class="blockquote">

 <pre class="programlisting">array( key1 =&gt; value1, key2 =&gt; value2, ... )</pre>

 </blockquote>

 </div>

 </li>

 <li>

 <p>この情報は以下の形式で ZIP 書庫ファイルに添付されます．</p>

 <div class="blockquote">

 <blockquote class="blockquote">

 <pre class="programlisting">key1: value1

key2: value2

...</pre>

 </blockquote>

 </div>

 </li>

 </ul>

 </div>

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

 <h2 xmlns="http://www.w3.org/1999/xhtml" class="title" style="clear: both"><a id="metainfo.basic"></a>1. BasicInformation のメタ情報</h2>

 </div>

 </div>

 </div>

 <p>共通ライブラリにメタ情報生成用に Basic Information を取得する関数が定義されているのでそれを利用します．</p>

 <p>以下の項目も参照してください．</p>

 <div class="itemizedlist">

 <ul type="disc">

 <li>

 <p>xnpGetBasicInformationArray</p>

 </li>

 </ul>

 </div>

 </div>

 <div class="section" lang="ja" xml:lang="ja">

 <div xmlns="" class="titlepage">

 <div>

 <div>

 <h2 xmlns="http://www.w3.org/1999/xhtml" class="title" style="clear: both"><a id="metainfo.detail"></a>2. Detail Information のメタ情報</h2>

 </div>

 </div>

 </div>

 <p>Detail Information のメタ情報はアイテムタイプモジュールが自由に定義できます．</p>

 </div>

 </div>

 <div xmlns="http://www.w3.org/1999/xhtml" class="navfooter">



 </div>


 </div>

 </body>


