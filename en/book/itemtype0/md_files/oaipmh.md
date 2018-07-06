 <body>

 <div id="page">

 <div xmlns="http://www.w3.org/1999/xhtml" class="navheader">

 </div>

 <div xmlns="http://www.w3.org/1999/xhtml" class="chapter" lang="ja" id="oaipmh" xml:lang="ja">

 <div xmlns="" class="titlepage">

 <div>

 <div>

 <h2 xmlns="http://www.w3.org/1999/xhtml" class="title"><a id="oaipmh"></a>第21章 OAI-PMH</h2>

 </div>

 </div>

 </div>

 <p>OAI-PMHハーベスタからの要求に対し，メタデータを生成します</p>

 <div class="section" lang="ja" xml:lang="ja">

 <div xmlns="" class="titlepage">

 <div>

 <div>

 <h2 xmlns="http://www.w3.org/1999/xhtml" class="title" style="clear: both"><a id="OAI-PMH.abstract"></a>1. OAI-PMH処理</h2>

 </div>

 </div>

 </div>

 <p>アイテムタイプモジュールは以下のOAI-PMH要求に対応します．</p>

 <div class="section" lang="ja" xml:lang="ja">

 <div xmlns="" class="titlepage">

 <div>

 <div>

 <h3 xmlns="http://www.w3.org/1999/xhtml" class="title"><a id="OAI-PMH.SupportMetadataFormat"></a>1.1. 対応メタデータフォーマットの列挙</h3>

 </div>

 </div>

 </div>

 <p>以下の関数を定義し，アイテムタイプモジュールがメタデータフォーマットの生成に対応しているか否かを返します．</p>

 <div class="itemizedlist">

 <ul type="disc">

 <li>

 <p>function &lt;モジュール名&gt;SupportMetadataFormat( $metadataPrefix, $item_id )</p>

 <p>$item_idで指定されたアイテムのメタ情報を，$metadataPrefixで指定されるフォーマットで生成できるかを返します．</p>

 <div class="itemizedlist">

 <ul type="circle">

 <li>

 <p>戻り値 : true(生成可能)</p>

 </li>

 <li>

 <p>戻り値 : false(生成不可能)</p>

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

 <h3 xmlns="http://www.w3.org/1999/xhtml" class="title"><a id="OAI-PMH.GetMetadata"></a>1.2. メタデータの生成</h3>

 </div>

 </div>

 </div>

 <p>以下の関数を定義し，指定されたアイテムのメタデータを返します．</p>

 <div class="itemizedlist">

 <ul type="disc">

 <li>

 <p>function &lt;モジュール名&gt;GetMetadata( $metadataPrefix, $item_id )</p>

 <p>$item_idで指定されたアイテムのメタデータを，$metadataPrefixで指定されるフォーマットで生成して返します．&lt;metadata&gt;から&lt;/metadata&gt;までを生成て返します．</p>

 <div class="itemizedlist">

 <ul type="circle">

 <li>

 <p>戻り値 : メタデータテキスト(&lt;metadata&gt;から&lt;/metadata&gt;まで)</p>

 </li>

 <li>

 <p>戻り値 : false(生成失敗)</p>

 </li>

 </ul>

 </div>

 </li>

 </ul>

 </div>

 </div>

 </div>

 </div>

 <div xmlns="http://www.w3.org/1999/xhtml" class="navfooter">


 </div>

 </div>

 </body>


