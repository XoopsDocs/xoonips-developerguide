 <body>

 <div id="page">

 <div xmlns="http://www.w3.org/1999/xhtml" class="navheader">

 </div>

 <div xmlns="http://www.w3.org/1999/xhtml" class="chapter" lang="ja" id="import" xml:lang="ja">

 <div xmlns="" class="titlepage">

 <div>

 <div>

 <h2 xmlns="http://www.w3.org/1999/xhtml" class="title"><a id="import"></a>第20章 Import</h2>

 </div>

 </div>

 </div>

 <p>ImportされるXMLファイルに記録されたアイテムの情報を解析しデータベースに登録します．システムはインポートに必要な以下のクラスを提供します．各アイテムタイプはこれらのクラスを継承し，インポートに必要なメソッドをオーバーライドしアイテムタイプ独自のインポート処理を定義します．</p>

 <div class="section" lang="ja" xml:lang="ja">

 <div xmlns="" class="titlepage">

 <div>

 <div>

 <h2 xmlns="http://www.w3.org/1999/xhtml" class="title" style="clear: both"><a id="import.classstructure"></a>1. クラス</h2>

 </div>

 </div>

 </div>

 <p>システムが提供するクラスは以下の通りです．</p>

 <div class="itemizedlist">

 <ul type="disc">

 <li>

 <p>インポートアイテムクラス</p>

 <div class="itemizedlist">

 <ul type="circle">

 <li>

 <p>クラス名：XooNIpsImportItem</p>

 </li>

 <li>

 <p>概要：インポートするアイテムの情報を保持するクラス</p>

 </li>

 </ul>

 </div>

 </li>

 <li>

 <p>インポートアイテムハンドラクラス</p>

 <div class="itemizedlist">

 <ul type="circle">

 <li>

 <p>クラス名：XooNIpsImportItemHandler</p>

 </li>

 <li>

 <p>概要：インポートアイテムクラスのインポート

 処理を実装するクラス．XooNIpsImportItemHandlerクラスは，

 アイテムのインポート処理を実装します．アイテムタイプは

 XooNIpsImportItemHandlerクラスを継承し，アイテムタイプ

 独自のインポート処理を実装（オーバーライド）できます．

 </p>

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

 <h2 xmlns="http://www.w3.org/1999/xhtml" class="title" style="clear: both"><a id="import.implement.classname"></a>2. クラス名</h2>

 </div>

 </div>

 </div>

 <p>クラス名はアイテムタイプ名に基づいて以下のように決まっています．</p>

 <div class="itemizedlist">

 <ul type="disc">

 <li>

 <p>class &lt;アイテムタイプ名&gt;ImportItem</p>

 <p>(例：XNPBookImportItem，XNPDataImportItem,...）</p>

 </li>

 <li>

 <p>class &lt;アイテムタイプ名&gt;ImportItemHandler</p>

 <p>(例：XNPBookImportItemHandler，XNPDataImportItemHandler,...）</p>

 </li>

 <li>

 <p>先頭から4文字は大文字です</p>

 </li>

 </ul>

 </div>

 </div>

 <div class="section" lang="ja" xml:lang="ja">

 <div xmlns="" class="titlepage">

 <div>

 <div>

 <h2 xmlns="http://www.w3.org/1999/xhtml" class="title" style="clear: both"><a id="import.filename"></a>3. ファイル名，ファイルパス</h2>

 </div>

 </div>

 </div>

 <p>クラスを定義するPHPファイルのファイル名とパスは，以下の通りです．</p>

 <div class="itemizedlist">

 <ul type="disc">

 <li>

 <p>ファイルパス：modules/モジュール名/class/</p>

 </li>

 <li>

 <p>ファイル名：&lt;アイテムタイプ名&gt;_import_item.class.php</p>

 <p>(例：xnpbook_import_item.class.php，xnpdata_import_item.class.php,...）</p>

 </li>

 <li>

 <p>ファイル名は全て小文字です</p>

 </li>

 </ul>

 </div>

 </div>

 <div class="section" lang="ja" xml:lang="ja">

 <div xmlns="" class="titlepage">

 <div>

 <div>

 <h2 xmlns="http://www.w3.org/1999/xhtml" class="title" style="clear: both"><a id="import.implement.importitem"></a>4. インポートアイテムクラスの実装</h2>

 </div>

 </div>

 </div>

 <p></p>

 <div class="section" lang="ja" xml:lang="ja">

 <div xmlns="" class="titlepage">

 <div>

 <div>

 <h3 xmlns="http://www.w3.org/1999/xhtml" class="title"><a id="import.implement.importitem.members"></a>4.1. 定義済みのメンバー変数</h3>

 </div>

 </div>

 </div>

 <p>インポートアイテムでは以下のメンバー変数を使用します．

 </p>

 <div class="table">

 <a id="table.import.implement.importitem.members"></a>

 <p class="title">

 <b>表 20.1. メンバー変数一覧</b>

 </p>

 <div class="table-contents">

 <table summary="メンバー変数一覧" cellspacing="0" cellpadding="5" border="0" style="border-collapse: collapse;border-top: 0.5pt solid ; border-bottom: 0.5pt solid ; border-left: 0.5pt solid ; border-right: 0.5pt solid ; ">

 <colgroup>

 <col />

 <col />

 </colgroup>

 <thead>

 <tr>

 <th style="border-right: 0.5pt solid ; border-bottom: 0.5pt solid ; " align="left">メンバー</th>

 <th style="border-bottom: 0.5pt solid ; " align="left">備考</th>

 </tr>

 </thead>

 <tbody>

 <tr>

 <td style="border-right: 0.5pt solid ; " align="left">XooNIpsItemCompo _item</td>

 <td style="" align="left">アイテム情報を保持するオブジェクト．このオブジェクトはコンストラクタで作成します．</td>

 </tr>

 </tbody>

 </table>

 </div>

 </div>

 <p><br class="table-break" />

 </p>

 </div>

 <div class="section" lang="ja" xml:lang="ja">

 <div xmlns="" class="titlepage">

 <div>

 <div>

 <h3 xmlns="http://www.w3.org/1999/xhtml" class="title"><a id="import.implement.importitem.override"></a>4.2. オーバーライドするメソッド</h3>

 </div>

 </div>

 </div>

 <p>アイテムタイプがオーバーライドするメソッドは以下の通りです．

 </p>

 <div class="table">

 <a id="table.import.implement.importitem.override"></a>

 <p class="title">

 <b>表 20.2. メソッド一覧</b>

 </p>

 <div class="table-contents">

 <table summary="メソッド一覧" cellspacing="0" cellpadding="5" border="0" style="border-collapse: collapse;border-top: 0.5pt solid ; border-bottom: 0.5pt solid ; border-left: 0.5pt solid ; border-right: 0.5pt solid ; ">

 <colgroup>

 <col />

 <col />

 </colgroup>

 <thead>

 <tr>

 <th style="border-right: 0.5pt solid ; border-bottom: 0.5pt solid ; " align="left">メソッド</th>

 <th style="border-bottom: 0.5pt solid ; " align="left">備考</th>

 </tr>

 </thead>

 <tbody>

 <tr>

 <td style="border-right: 0.5pt solid ; border-bottom: 0.5pt solid ; " align="left">int getTotalFileSize()</td>

 <td style="border-bottom: 0.5pt solid ; " align="left">アイテムに添付されたファイルの合計サイズ(単位：バイト)を返す</td>

 </tr>

 <tr>

 <td style="border-right: 0.5pt solid ; " align="left">XooNIpsImportItem &amp;getClone()</td>

 <td style="" align="left">インポートアイテムオブジェクトの複製(クローン)を作成し，そのリファレンスを返す</td>

 </tr>

 </tbody>

 </table>

 </div>

 </div>

 <p><br class="table-break" />

 </p>

 </div>

 <div class="section" lang="ja" xml:lang="ja">

 <div xmlns="" class="titlepage">

 <div>

 <div>

 <h3 xmlns="http://www.w3.org/1999/xhtml" class="title"><a id="import.implement.importitem.constructor"></a>4.3. コンストラクタ</h3>

 </div>

 </div>

 </div>

 <p>メンバー変数$_itemを初期化します．アイテムタイプごとに定義されたORMオブジェクトを作成し，リファレンスを代入します．以下はDataタイプのコンストラクタの例です．</p>

 <pre class="programlisting">

 function XNPDataImportItem(){

 $handler =&amp; xoonips_getormcompohandler( 'xnpdata', 'item' );

 $this -&gt; _item =&amp; $handler -&gt; create();

 }

</pre>

 </div>

 </div>

 <div class="section" lang="ja" xml:lang="ja">

 <div xmlns="" class="titlepage">

 <div>

 <div>

 <h2 xmlns="http://www.w3.org/1999/xhtml" class="title" style="clear: both"><a id="import.implement.importitemhandler"></a>5. インポートアイテムハンドラクラスの実装</h2>

 </div>

 </div>

 </div>

 <p></p>

 <div class="section" lang="ja" xml:lang="ja">

 <div xmlns="" class="titlepage">

 <div>

 <div>

 <h3 xmlns="http://www.w3.org/1999/xhtml" class="title"><a id="import.implement.importitemhandler.members"></a>5.1. 定義済みのメンバー変数</h3>

 </div>

 </div>

 </div>

 <p>インポートアイテムハンドラでは以下のメンバー変数を使用します．

 </p>

 <div class="table">

 <a id="table.import.implement.importitemhandler.members"></a>

 <p class="title">

 <b>表 20.3. メンバー変数一覧</b>

 </p>

 <div class="table-contents">

 <table summary="メンバー変数一覧" cellspacing="0" cellpadding="5" border="0" style="border-collapse: collapse;border-top: 0.5pt solid ; border-bottom: 0.5pt solid ; border-left: 0.5pt solid ; border-right: 0.5pt solid ; ">

 <colgroup>

 <col />

 <col />

 </colgroup>

 <thead>

 <tr>

 <th style="border-right: 0.5pt solid ; border-bottom: 0.5pt solid ; " align="left">メンバー</th>

 <th style="border-bottom: 0.5pt solid ; " align="left">備考</th>

 </tr>

 </thead>

 <tbody>

 <tr>

 <td style="border-right: 0.5pt solid ; border-bottom: 0.5pt solid ; " align="left">string[] _tag_stack</td>

 <td style="border-bottom: 0.5pt solid ; " align="left">解析中のXMLの要素名を管理するスタック．配列の先頭にルートの要素名が，最後に現在解析中の要素名が記録されます．</td>

 </tr>

 <tr>

 <td style="border-right: 0.5pt solid ; border-bottom: 0.5pt solid ; " align="left">string _cdata</td>

 <td style="border-bottom: 0.5pt solid ; " align="left">現在解析中の要素のCDATA部の文字列が格納されます．ただし，xmlEndElementHandler(<a href="import.html#import.implement.importitemhandler.endelementhandler" title="5.5. 終了要素ハンドラ(xmlEndElementHandler)">項5.5. 「終了要素ハンドラ(xmlEndElementHandler)」</a>)が呼ばれるまで，このメンバーの値は確定しませんので注意してください．</td>

 </tr>

 <tr>

 <td style="border-right: 0.5pt solid ; border-bottom: 0.5pt solid ; " align="left">XooNIpsImportItem _import_item</td>

 <td style="border-bottom: 0.5pt solid ; " align="left">インポートアイテムオブジェクト．XMLを解析して得られたアイテムの情報をこのオブジェクトにセットします．このオブジェクトはコンストラクタで作成します．</td>

 </tr>

 <tr>

 <td style="border-right: 0.5pt solid ; " align="left">string _attachment_dir</td>

 <td style="" align="left">インポートされる添付ファイルが一時保存されているファイルパス(絶対パス)．</td>

 </tr>

 </tbody>

 </table>

 </div>

 </div>

 <p><br class="table-break" />

 </p>

 </div>

 <div class="section" lang="ja" xml:lang="ja">

 <div xmlns="" class="titlepage">

 <div>

 <div>

 <h3 xmlns="http://www.w3.org/1999/xhtml" class="title"><a id="import.implement.importitemhandler.override"></a>5.2. オーバーライドするメソッド</h3>

 </div>

 </div>

 </div>

 <p>アイテムタイプがオーバーライドするメソッドは以下の通りです．

 </p>

 <div class="table">

 <a id="table.import.implement.importitemhandler.override"></a>

 <p class="title">

 <b>表 20.4. メソッド一覧</b>

 </p>

 <div class="table-contents">

 <table summary="メソッド一覧" cellspacing="0" cellpadding="5" border="0" style="border-collapse: collapse;border-top: 0.5pt solid ; border-bottom: 0.5pt solid ; border-left: 0.5pt solid ; border-right: 0.5pt solid ; ">

 <colgroup>

 <col />

 <col />

 </colgroup>

 <thead>

 <tr>

 <th style="border-right: 0.5pt solid ; border-bottom: 0.5pt solid ; " align="left">メソッド</th>

 <th style="border-bottom: 0.5pt solid ; " align="left">備考</th>

 </tr>

 </thead>

 <tbody>

 <tr>

 <td style="border-right: 0.5pt solid ; border-bottom: 0.5pt solid ; " align="left">XooNIpsImportItem create()</td>

 <td style="border-bottom: 0.5pt solid ; " align="left">アイテムタイプに応じたインポートアイテムオブジェクトを作成して返します．</td>

 </tr>

 <tr>

 <td style="border-right: 0.5pt solid ; border-bottom: 0.5pt solid ; " align="left">void xmlStartElementHandler( $parser , $name , $attribs )</td>

 <td style="border-bottom: 0.5pt solid ; " align="left">XMLファイルの開始要素を解析するときにコールバックされます．Detail Informationの開始要素の解析処理を定義します．</td>

 </tr>

 <tr>

 <td style="border-right: 0.5pt solid ; border-bottom: 0.5pt solid ; " align="left">void xmlEndElementHandler( $parser ,$name )</td>

 <td style="border-bottom: 0.5pt solid ; " align="left">XMLファイルの終了要素を解析するときにコールバックされます．Detail Informationの終了要素の解析処理を定義します．</td>

 </tr>

 <tr>

 <td style="border-right: 0.5pt solid ; border-bottom: 0.5pt solid ; " align="left">void onImportFinished( &amp;$item, &amp;$import_items )</td>

 <td style="border-bottom: 0.5pt solid ; " align="left">インポート成功後のアイテムの操作を定義します．</td>

 </tr>

 <tr>

 <td style="border-right: 0.5pt solid ; border-bottom: 0.5pt solid ; " align="left">bool insert( &amp;$item )</td>

 <td style="border-bottom: 0.5pt solid ; " align="left">アイテムオブジェクトのinsertを実行します．</td>

 </tr>

 <tr>

 <td style="border-right: 0.5pt solid ; border-bottom: 0.5pt solid ; " align="left">viod setNew( &amp;$item )</td>

 <td style="border-bottom: 0.5pt solid ; " align="left">アイテムオブジェクトのsetNewを実行します．</td>

 </tr>

 <tr>

 <td style="border-right: 0.5pt solid ; border-bottom: 0.5pt solid ; " align="left">viod unsetNew( &amp;$item ) </td>

 <td style="border-bottom: 0.5pt solid ; " align="left">アイテムオブジェクトのunsetNewを実行します．</td>

 </tr>

 <tr>

 <td style="border-right: 0.5pt solid ; border-bottom: 0.5pt solid ; " align="left">viod setDirty( &amp;$item ) </td>

 <td style="border-bottom: 0.5pt solid ; " align="left">アイテムオブジェクトのsetDirtyを実行します．</td>

 </tr>

 <tr>

 <td style="border-right: 0.5pt solid ; border-bottom: 0.5pt solid ; " align="left">viod unsetDirty( &amp;$item )</td>

 <td style="border-bottom: 0.5pt solid ; " align="left">アイテムオブジェクトのunsetDirtyを実行します．</td>

 </tr>

 <tr>

 <td style="border-right: 0.5pt solid ; border-bottom: 0.5pt solid ; " align="left">string getImportLog($import_item)</td>

 <td style="border-bottom: 0.5pt solid ; " align="left">インポート結果のログを作成します．</td>

 </tr>

 <tr>

 <td style="border-right: 0.5pt solid ; " align="left">void import(&amp;$item)</td>

 <td style="" align="left">インポートを実行します．</td>

 </tr>

 </tbody>

 </table>

 </div>

 </div>

 <p><br class="table-break" />

 </p>

 </div>

 <div class="section" lang="ja" xml:lang="ja">

 <div xmlns="" class="titlepage">

 <div>

 <div>

 <h3 xmlns="http://www.w3.org/1999/xhtml" class="title"><a id="import.implement.importitemhandler.constructor"></a>5.3. コンストラクタ</h3>

 </div>

 </div>

 </div>

 <p>スーパークラスのコンストラクタを呼び出します．以下はDataタイプのコンストラクタの例です．</p>

 <pre class="programlisting">

function XNPDataImportItemHandler(){

 parent::XooNIpsImportItemHandler();

}

</pre>

 </div>

 <div class="section" lang="ja" xml:lang="ja">

 <div xmlns="" class="titlepage">

 <div>

 <div>

 <h3 xmlns="http://www.w3.org/1999/xhtml" class="title"><a id="import.implement.importitemhandler.startelementhandler"></a>5.4. 開始要素ハンドラ(xmlStartElementHandler)</h3>

 </div>

 </div>

 </div>

 <p>

 </p>

 <pre class="programlisting">void xmlStartElementHandler( $parser , $name , $attribs )</pre>

 <p>

 </p>

 <p>インポートするXMLファイルをシステムが解析し，開始要素を見つけたときにコールバックされます．要素の属性値を必要とする処理はここに定義します．アイテムタイプはこの関数で以下の処理を行います．</p>

 <div class="itemizedlist">

 <ul type="disc">

 <li>

 <p>スーパークラスのxmlStartElementHandlerを呼び出す</p>

 </li>

 <li>

 <p>開始要素の解析を行う</p>

 </li>

 </ul>

 </div>

 <p>開始要素に付いての情報は引数で与えられます．引数は以下のとおりです．</p>

 <div class="itemizedlist">

 <ul type="disc">

 <li>

 <p>$parser：XMLパーザのリファレンス</p>

 </li>

 <li>

 <p>$name：要素名</p>

 </li>

 <li>

 <p>$attribs：属性の連想配列</p>

 </li>

 </ul>

 </div>

 <p>$parserはxml_parser_createで作成されるXMLパーザのリファレンスです．XMLの解析に関連する情報(解析中の行番号など)が必要な場合はこのリファレンスを使用できます．詳細はPHPのXML関数についての情報を参照してください．</p>

 <p>$nameは要素名の文字列です．XMLファイル中の書き方に拘わらず，要素名は大文字に変換されます．</p>

 <p>$attribは開始要素に定義された属性名と属性値を連想配列の形で保持します．</p>

 <p>以上の引数は全て，PHPのXML関数が提供する開始要素ハンドラと同じです．詳細はPHPのXML関数(xml_set_element_handlerなど)についての情報を参照してください．</p>

 <p>戻り値はありません．</p>

 <p>処理中のエラーはすべて，_import_itemメンバーのsetErrorsメソッドを使用して記録します．詳しくはXooNIpsImportItemを参照してください．</p>

 <div class="section" lang="ja" xml:lang="ja">

 <div xmlns="" class="titlepage">

 <div>

 <div>

 <h4 xmlns="http://www.w3.org/1999/xhtml" class="title"><a id="import.implement.importitemhandler.startelementhandler.callsuper"></a>5.4.1. スーパークラスの開始要素ハンドラを呼び出す</h4>

 </div>

 </div>

 </div>

 <pre class="programlisting">parent::xmlStartElementHandler($parser, $name, $attribs);</pre>

 <p>開始要素ハンドラの冒頭で，上のようにしてスーパークラスの開始要素ハンドラを呼び出します．必ず呼び出してください．</p>

 </div>

 <div class="section" lang="ja" xml:lang="ja">

 <div xmlns="" class="titlepage">

 <div>

 <div>

 <h4 xmlns="http://www.w3.org/1999/xhtml" class="title"><a id="import.implement.importitemhandler.startelementhandler.detailinformation"></a>5.4.2. 開始要素の解析を行う</h4>

 </div>

 </div>

 </div>

 <p>メンバー変数_tag_stackを参照し，現在の解析対象要素を判断し，要素にあった処理を定義します</p>

 <p>以下は，要素ごとの処理を定義するサンプルです．</p>

 <pre class="programlisting">

switch( implode( '/', $this -&gt; _tag_stack ) ){

case "ITEM/DETAIL":

 //&lt;item&gt;&lt;detail&gt;タグの処理をここに定義します．

 break;

case "ITEM/DETAIL/FOO":

 //&lt;item&gt;&lt;detail&gt;&lt;foo&gt;タグの処理をここに定義します．

 break;

}

 </pre>

 </div>

 </div>

 <div class="section" lang="ja" xml:lang="ja">

 <div xmlns="" class="titlepage">

 <div>

 <div>

 <h3 xmlns="http://www.w3.org/1999/xhtml" class="title"><a id="import.implement.importitemhandler.endelementhandler"></a>5.5. 終了要素ハンドラ(xmlEndElementHandler)</h3>

 </div>

 </div>

 </div>

 <p>

 </p>

 <pre class="programlisting">void xmlEndElementHandler( $parser ,$name )</pre>

 <p>

 </p>

 <p>インポートするXMLファイルをシステムが解析し，終了要素を見つけたときにコールバックされます．要素のCDATAを参照する処理はこのメソッドに定義します．アイテムタイプはこの関数で以下の処理を行います．</p>

 <div class="itemizedlist">

 <ul type="disc">

 <li>

 <p>終了要素の解析を行う</p>

 </li>

 <li>

 <p>スーパークラスのxmlEndElementHandlerを呼び出す</p>

 </li>

 </ul>

 </div>

 <p>終了要素についての情報は引数で与えられます．引数は以下の

 とおりです．引数の解説は

 <a href="import.html#import.implement.importitemhandler.startelementhandler" title="5.4. 開始要素ハンドラ(xmlStartElementHandler)">項5.4. 「開始要素ハンドラ(xmlStartElementHandler)」</a>

 を参照してください．

 </p>

 <div class="itemizedlist">

 <ul type="disc">

 <li>

 <p>$parser：XMLパーザのリファレンス</p>

 </li>

 <li>

 <p>$name：要素名</p>

 </li>

 </ul>

 </div>

 <p>戻り値はありません．</p>

 <div class="section" lang="ja" xml:lang="ja">

 <div xmlns="" class="titlepage">

 <div>

 <div>

 <h4 xmlns="http://www.w3.org/1999/xhtml" class="title"><a id="import.implement.importitemhandler.endelementhandler.detailinformation"></a>5.5.1. 終了要素の解析を行う</h4>

 </div>

 </div>

 </div>

 <p>メンバー変数_tag_stackを参照し，現在の解析対象要素を判断し，要素にあった処理を定義します</p>

 <p>以下は，要素ごとの処理を定義するサンプルです．</p>

 <pre class="programlisting">

switch( implode( '/', $this -&gt; _tag_stack ) ){

case "ITEM/DETAIL":

 //&lt;item&gt;&lt;detail&gt;タグの処理をここに定義します．

 break;

case "ITEM/DETAIL/FOO":

 //&lt;item&gt;&lt;detail&gt;&lt;foo&gt;タグの処理をここに定義します．

 break;

}

 </pre>

 </div>

 <div class="section" lang="ja" xml:lang="ja">

 <div xmlns="" class="titlepage">

 <div>

 <div>

 <h4 xmlns="http://www.w3.org/1999/xhtml" class="title"><a id="import.implement.importitemhandler.endelementhandler.callsuper"></a>5.5.2. スーパークラスの終了要素ハンドラを呼び出す</h4>

 </div>

 </div>

 </div>

 <pre class="programlisting">

parent::xmlEndElementHandler($parser, $name);

 </pre>

 <p>終了要素ハンドラの最後に，上のようにしてスーパークラスの終了要素ハンドラを呼び出します．必ず呼び出してください．</p>

 </div>

 </div>

 <div class="section" lang="ja" xml:lang="ja">

 <div xmlns="" class="titlepage">

 <div>

 <div>

 <h3 xmlns="http://www.w3.org/1999/xhtml" class="title"><a id="import.implement.importitemhandler.insert"></a>5.6. アイテムのインサート(insert)</h3>

 </div>

 </div>

 </div>

 <p>

 </p>

 <pre class="programlisting">bool insert( &amp;$item )</pre>

 <p>

 </p>

 <p>XMLを解析して得られたアイテムをデータベースにインサートし，その成否を返します．処理はXooNIpsItemCompoHandlerへ委譲します．</p>

 <pre class="programlisting">

function insert( &amp;$item ){

 $handler =&amp; xoonips_getormcompohandler( 'xnpdata', 'item' );

 return $handler -&gt; insert($item);

}

</pre>

 </div>

 <div class="section" lang="ja" xml:lang="ja">

 <div xmlns="" class="titlepage">

 <div>

 <div>

 <h3 xmlns="http://www.w3.org/1999/xhtml" class="title"><a id="import.implement.importitemhandler.setnew"></a>5.7. アイテムのnewフラグセット(setNew)</h3>

 </div>

 </div>

 </div>

 <p>

 </p>

 <pre class="programlisting">void setNew( &amp;$item )</pre>

 <p>

 </p>

 <p>インポートするアイテムオブジェクトに，新規アイテムを表すnewフラグをセットします．処理はXooNIpsItemCompoHandlerへ委譲します．</p>

 <pre class="programlisting">

function setNew( &amp;$item ){

 $handler =&amp; xoonips_getormcompohandler( 'xnpdata', 'item' );

 $handler -&gt; setNew($item);

}

 </pre>

 </div>

 <div class="section" lang="ja" xml:lang="ja">

 <div xmlns="" class="titlepage">

 <div>

 <div>

 <h3 xmlns="http://www.w3.org/1999/xhtml" class="title"><a id="import.implement.importitemhandler.unsetnew"></a>5.8. アイテムのnewフラグ解除(unsetNew)</h3>

 </div>

 </div>

 </div>

 <p>

 </p>

 <pre class="programlisting">void unsetNew( &amp;$item )</pre>

 <p>

 </p>

 <p>インポートするアイテムオブジェクトのnewフラグを解除します．処理はXooNIpsItemCompoHandlerへ委譲します．</p>

 <pre class="programlisting">

function unsetNew( &amp;$item ){

 $handler =&amp; xoonips_getormcompohandler( 'xnpdata', 'item' );

 $handler -&gt; unsetNew($item);

}

 </pre>

 </div>

 <div class="section" lang="ja" xml:lang="ja">

 <div xmlns="" class="titlepage">

 <div>

 <div>

 <h3 xmlns="http://www.w3.org/1999/xhtml" class="title"><a id="import.implement.importitemhandler.setdirty"></a>5.9. アイテムのdirtyフラグセット(setDirty)</h3>

 </div>

 </div>

 </div>

 <p>

 </p>

 <pre class="programlisting">void setDirty( &amp;$item )</pre>

 <p>

 </p>

 <p>インポートするアイテムオブジェクトに，内容が変更されたことを表すdirtyフラグをセットします．処理はXooNIpsItemCompoHandlerへ委譲します．</p>

 <pre class="programlisting">

function setDirty( &amp;$item ){

 $handler =&amp; xoonips_getormcompohandler( 'xnpdata', 'item' );

 $handler -&gt; setDirty($item);

}

 </pre>

 </div>

 <div class="section" lang="ja" xml:lang="ja">

 <div xmlns="" class="titlepage">

 <div>

 <div>

 <h3 xmlns="http://www.w3.org/1999/xhtml" class="title"><a id="import.implement.importitemhandler.unsetdirty"></a>5.10. アイテムのdirtyフラグ解除(unsetDirty)</h3>

 </div>

 </div>

 </div>

 <p>

 </p>

 <pre class="programlisting">void unsetDirty( &amp;$item )</pre>

 <p>

 </p>

 <p>インポートするアイテムオブジェクトのdirtyフラグを解除します．処理はXooNIpsItemCompoHandlerへ委譲します．</p>

 <pre class="programlisting">

function unsetDirty( &amp;$item ){

 $handler =&amp; xoonips_getormcompohandler( 'xnpdata', 'item' );

 $handler -&gt; unsetDirty($item);

}

 </pre>

 </div>

 <div class="section" lang="ja" xml:lang="ja">

 <div xmlns="" class="titlepage">

 <div>

 <div>

 <h3 xmlns="http://www.w3.org/1999/xhtml" class="title"><a id="import.implement.importitemhandler.getimportlog"></a>5.11. インポートログの作成(getImportLog)</h3>

 </div>

 </div>

 </div>

 <p>

 </p>

 <pre class="programlisting">string getImportLog($import_item)</pre>

 <p>

 </p>

 <p>インポート処理中のアイテムに関する情報をログ形式の文字列にして返します．以下の手順で処理を行います．</p>

 <div class="itemizedlist">

 <ul type="disc">

 <li>

 <p>スーパークラスのgetImportLogを呼び出す</p>

 </li>

 <li>

 <p>アイテムタイプ独自のログを追加する</p>

 </li>

 </ul>

 </div>

 <div class="section" lang="ja" xml:lang="ja">

 <div xmlns="" class="titlepage">

 <div>

 <div>

 <h4 xmlns="http://www.w3.org/1999/xhtml" class="title"><a id="import.implement.importitemhandler.getimportlog.callsuper"></a>5.11.1. スーパークラスのgetImportLogを呼び出す</h4>

 </div>

 </div>

 </div>

 <p>スーパークラスのgetImportLogを呼び出し，Basic Informationについてのインポートログを取得します．取得した文字列に，アイテムタイプ独自のログを追加します．</p>

 <pre class="programlisting">$text = parent::getImportLog($import_item);</pre>

 <p>Basic Informationのログは，以下の書式で生成されます．</p>

 <pre class="programlisting">basic.&lt;フィールド名&gt; &lt;値&gt;(改行)</pre>

 <p>フィールド名とその値は以下の通りです．</p>

 <p>

 </p>

 <div class="table">

 <a id="table.import.implement.importitemhandler.getimportlog.fields"></a>

 <p class="title">

 <b>表 20.5. フィールド一覧</b>

 </p>

 <div class="table-contents">

 <table summary="フィールド一覧" cellspacing="0" cellpadding="5" border="0" style="border-collapse: collapse;border-top: 0.5pt solid ; border-bottom: 0.5pt solid ; border-left: 0.5pt solid ; border-right: 0.5pt solid ; ">

 <colgroup>

 <col />

 <col />

 </colgroup>

 <thead>

 <tr>

 <th style="border-right: 0.5pt solid ; border-bottom: 0.5pt solid ; " align="left">フィールド名</th>

 <th style="border-bottom: 0.5pt solid ; " align="left">内容</th>

 </tr>

 </thead>

 <tbody>

 <tr>

 <td style="border-right: 0.5pt solid ; border-bottom: 0.5pt solid ; " align="left">id</td>

 <td style="border-bottom: 0.5pt solid ; " align="left">アイテムID(仮)</td>

 </tr>

 <tr>

 <td style="border-right: 0.5pt solid ; border-bottom: 0.5pt solid ; " align="left">title</td>

 <td style="border-bottom: 0.5pt solid ; " align="left">タイトル</td>

 </tr>

 <tr>

 <td style="border-right: 0.5pt solid ; border-bottom: 0.5pt solid ; " align="left">contributor</td>

 <td style="border-bottom: 0.5pt solid ; " align="left">作成者のUID</td>

 </tr>

 <tr>

 <td style="border-right: 0.5pt solid ; border-bottom: 0.5pt solid ; " align="left">itemtype</td>

 <td style="border-bottom: 0.5pt solid ; " align="left">アイテムタイプID</td>

 </tr>

 <tr>

 <td style="border-right: 0.5pt solid ; border-bottom: 0.5pt solid ; " align="left">keyword</td>

 <td style="border-bottom: 0.5pt solid ; " align="left">キーワード</td>

 </tr>

 <tr>

 <td style="border-right: 0.5pt solid ; border-bottom: 0.5pt solid ; " align="left">description</td>

 <td style="border-bottom: 0.5pt solid ; " align="left">コメント</td>

 </tr>

 <tr>

 <td style="border-right: 0.5pt solid ; border-bottom: 0.5pt solid ; " align="left">doi</td>

 <td style="border-bottom: 0.5pt solid ; " align="left">ID</td>

 </tr>

 <tr>

 <td style="border-right: 0.5pt solid ; border-bottom: 0.5pt solid ; " align="left">last_update_date</td>

 <td style="border-bottom: 0.5pt solid ; " align="left">最終更新日の整数表現</td>

 </tr>

 <tr>

 <td style="border-right: 0.5pt solid ; border-bottom: 0.5pt solid ; " align="left">creation_date</td>

 <td style="border-bottom: 0.5pt solid ; " align="left">作成日の整数表現</td>

 </tr>

 <tr>

 <td style="border-right: 0.5pt solid ; border-bottom: 0.5pt solid ; " align="left">publication_year</td>

 <td style="border-bottom: 0.5pt solid ; " align="left">発行年</td>

 </tr>

 <tr>

 <td style="border-right: 0.5pt solid ; border-bottom: 0.5pt solid ; " align="left">publication_month</td>

 <td style="border-bottom: 0.5pt solid ; " align="left">発行月</td>

 </tr>

 <tr>

 <td style="border-right: 0.5pt solid ; border-bottom: 0.5pt solid ; " align="left">publication_mday</td>

 <td style="border-bottom: 0.5pt solid ; " align="left">発行日</td>

 </tr>

 <tr>

 <td style="border-right: 0.5pt solid ; border-bottom: 0.5pt solid ; " align="left">lang</td>

 <td style="border-bottom: 0.5pt solid ; " align="left">言語</td>

 </tr>

 <tr>

 <td style="border-right: 0.5pt solid ; border-bottom: 0.5pt solid ; " align="left">filename</td>

 <td style="border-bottom: 0.5pt solid ; " align="left">インポートファイルのXMLファイル名</td>

 </tr>

 <tr>

 <td style="border-right: 0.5pt solid ; border-bottom: 0.5pt solid ; " align="left">url</td>

 <td style="border-bottom: 0.5pt solid ; " align="left">インポートしたアイテムの詳細画面のURL(インポート失敗時やテスト実行時は空文字列)</td>

 </tr>

 <tr>

 <td style="border-right: 0.5pt solid ; border-bottom: 0.5pt solid ; " align="left">related_to</td>

 <td style="border-bottom: 0.5pt solid ; " align="left">関連アイテムのID(テスト実行時は仮アイテムID)</td>

 </tr>

 <tr>

 <td style="border-right: 0.5pt solid ; " align="left">index</td>

 <td style="" align="left">インポート先インデックスID</td>

 </tr>

 </tbody>

 </table>

 </div>

 </div>

 <p><br class="table-break" />

 </p>

 </div>

 <div class="section" lang="ja" xml:lang="ja">

 <div xmlns="" class="titlepage">

 <div>

 <div>

 <h4 xmlns="http://www.w3.org/1999/xhtml" class="title"><a id="import.implement.importitemhandler.getimportlog.detailinformation"></a>5.11.2. アイテムタイプ独自のログを追加する</h4>

 </div>

 </div>

 </div>

 <p>アイテムタイプ独自のログを追加します．Detail Informationの情報を以下の書式に従って作成します．</p>

 <pre class="programlisting">detail.&lt;フィールド名&gt; &lt;値&gt;(改行)</pre>

 <p>フィールド値に特殊文字を含む場合は下表のとおり，\記号によるエスケープが必要です．</p>

 <div class="table">

 <a id="table.import.implement.importitemhandler.getimportlog.detailinformation.escape"></a>

 <p class="title">

 <b>表 20.6. エスケープ規則</b>

 </p>

 <div class="table-contents">

 <table summary="エスケープ規則" cellspacing="0" cellpadding="5" border="0" style="border-collapse: collapse;border-top: 0.5pt solid ; border-bottom: 0.5pt solid ; border-left: 0.5pt solid ; border-right: 0.5pt solid ; ">

 <colgroup>

 <col />

 <col />

 </colgroup>

 <thead>

 <tr>

 <th style="border-right: 0.5pt solid ; border-bottom: 0.5pt solid ; " align="left">エスケープ前</th>

 <th style="border-bottom: 0.5pt solid ; " align="left">エスケープ後</th>

 </tr>

 </thead>

 <tbody>

 <tr>

 <td style="border-right: 0.5pt solid ; border-bottom: 0.5pt solid ; " align="left">\</td>

 <td style="border-bottom: 0.5pt solid ; " align="left">\\</td>

 </tr>

 <tr>

 <td style="border-right: 0.5pt solid ; " align="left">(改行文字)</td>

 <td style="" align="left">\n</td>

 </tr>

 </tbody>

 </table>

 </div>

 </div>

 <br class="table-break" />

 <p>以下に，例を示します．</p>

 <pre class="programlisting">

$detail =&amp; $import_item -&gt; getVar( 'detail' );

$text .= "\ndetail.readme " . mb_ereg_replace(

 '\n', '\n', mb_ereg_replace(

 '\\\\', '\\\\', $detail -&gt; getVar( 'readme', 'n' )));

 </pre>

 </div>

 </div>

 <div class="section" lang="ja" xml:lang="ja">

 <div xmlns="" class="titlepage">

 <div>

 <div>

 <h3 xmlns="http://www.w3.org/1999/xhtml" class="title"><a id="import.implement.importitemhandler.attachment"></a>5.12. 添付ファイルへの対応</h3>

 </div>

 </div>

 </div>

 <p>アイテムタイプが添付ファイルを持つ場合は，以下の定義も必要です．</p>

 <div class="itemizedlist">

 <ul type="disc">

 <li>

 <p>メンバー変数の定義</p>

 </li>

 <li>

 <p>開始要素ハンドラの定義</p>

 </li>

 <li>

 <p>終了要素ハンドラの定義</p>

 </li>

 <li>

 <p>インポート終了イベント処理メソッドの定義</p>

 </li>

 </ul>

 </div>

 <div class="section" lang="ja" xml:lang="ja">

 <div xmlns="" class="titlepage">

 <div>

 <div>

 <h4 xmlns="http://www.w3.org/1999/xhtml" class="title"><a id="import.implement.importitemhandler.attachment.members"></a>5.12.1. メンバー変数の定義</h4>

 </div>

 </div>

 </div>

 <p>添付ファイルを取り扱うため，インポートアイテムハンドラにファイルオブジェクトを保持するメンバー変数を宣言します．</p>

 </div>

 <div class="section" lang="ja" xml:lang="ja">

 <div xmlns="" class="titlepage">

 <div>

 <div>

 <h4 xmlns="http://www.w3.org/1999/xhtml" class="title"><a id="import.implement.importitemhandler.attachment.startelementhandler"></a>5.12.2. 開始要素ハンドラの定義</h4>

 </div>

 </div>

 </div>

 <p>開始要素ハンドラに添付ファイルの処理を追加します．</p>

 <p>添付ファイルの情報はFILE要素で定義されます．開始要素ハ

 ンドラは，FILE要素の解析で以下の処理を行います．</p>

 <div class="itemizedlist">

 <ul type="disc">

 <li>

 <p>ファイルオブジェクトを作成し，メンバー変数にセット</p>

 </li>

 <li>

 <p>添付ファイルのパスをファイルオブジェクトにセット</p>

 </li>

 <li>

 <p>ファイルのメタ情報をファイルオブジェクトにセット</p>

 </li>

 </ul>

 </div>

 <p>始めにファイルオブジェクトを作成します．セッションID，ファイルタイプIDもセットします．ファイルタイプIDは，属性FILE_TYPE_NAMEの値に対応するファイルタイプIDをデータベースに問い合わせて取得できます．</p>

 <pre class="programlisting">

$file_type_handler =&amp; xoonips_getormhandler( 'xoonips', 'file_type' );

$criteria = new Criteria( 'name', addslashes( $attribs['FILE_TYPE_NAME'] ) );

$file_type =&amp; $file_type_handler -&gt; getObjects( $criteria );

$file_handler =&amp; xoonips_getormhandler( 'xoonips', 'file' );

$this -&gt; _file_member =&amp; $file_handler -&gt; create();

$this -&gt; _file_member -&gt; set( 'sess_id', session_id() );

$this -&gt; _file_member -&gt; set( 'file_type_id', $file_type[0] -&gt; get( 'file_type_id' ) );

 </pre>

 <p>次に，添付ファイルが置かれたパスをファイルオブジェクト

 にセットします．添付ファイルはシステムが確保した一時フォル

 ダに保存されます．一時フォルダのパスはメンバー変

 数_attachment_dirで取得できます．添付ファイル名はFILE_NAME

 属性で得られます．以下のようにして，ファイルオブジェクトに

 添付ファイルのパスをセットしてください．

 </p>

 <pre class="programlisting">

$this -&gt; _file_member -&gt; setFilepath( $this -&gt; _attachment_dir . '/' . $attribs['FILE_NAME'] );

 </pre>

 <p>最後に，FILE要素からファイルに関する属性を取得し，ファイルオブジェクトにセットします．ファイルオブジェクトに以下の情報をセットしてください．</p>

 <div class="table">

 <a id="table.import.implement.importitemhandler.attachment.startelementhandler.attribute"></a>

 <p class="title">

 <b>表 20.7. 属性一覧</b>

 </p>

 <div class="table-contents">

 <table summary="属性一覧" cellspacing="0" cellpadding="5" border="0" style="border-collapse: collapse;border-top: 0.5pt solid ; border-bottom: 0.5pt solid ; border-left: 0.5pt solid ; border-right: 0.5pt solid ; ">

 <colgroup>

 <col />

 <col />

 </colgroup>

 <thead>

 <tr>

 <th style="border-right: 0.5pt solid ; border-bottom: 0.5pt solid ; " align="left">属性名</th>

 <th style="border-bottom: 0.5pt solid ; " align="left">備考</th>

 </tr>

 </thead>

 <tbody>

 <tr>

 <td style="border-right: 0.5pt solid ; border-bottom: 0.5pt solid ; " align="left">ORIGINAL_FILE_NAME</td>

 <td style="border-bottom: 0.5pt solid ; " align="left">オリジナルファイル名</td>

 </tr>

 <tr>

 <td style="border-right: 0.5pt solid ; border-bottom: 0.5pt solid ; " align="left">MIME_TYPE</td>

 <td style="border-bottom: 0.5pt solid ; " align="left">mime-type</td>

 </tr>

 <tr>

 <td style="border-right: 0.5pt solid ; " align="left">FILE_SIZE</td>

 <td style="" align="left">ファイルサイズ(バイト)</td>

 </tr>

 </tbody>

 </table>

 </div>

 </div>

 <br class="table-break" />

 </div>

 <div class="section" lang="ja" xml:lang="ja">

 <div xmlns="" class="titlepage">

 <div>

 <div>

 <h4 xmlns="http://www.w3.org/1999/xhtml" class="title"><a id="import.implement.importitemhandler.attachment.endelementhandler"></a>5.12.3. 終了要素ハンドラの定義</h4>

 </div>

 </div>

 </div>

 <p>開始要素ハンドラと同様に，終了要素ハンドラに添付ファイ

 ルの処理を追加します．終了要素ハンドラでは以下の処理を行います．

 </p>

 <div class="itemizedlist">

 <ul type="disc">

 <li>

 <p>キャプションの解析</p>

 </li>

 <li>

 <p>サムネイル画像の解析</p>

 </li>

 <li>

 <p>ファイルをデータベースへ記録</p>

 </li>

 </ul>

 </div>

 <div class="section" lang="ja" xml:lang="ja">

 <div xmlns="" class="titlepage">

 <div>

 <div>

 <h5 xmlns="http://www.w3.org/1999/xhtml" class="title"><a id="import.implement.importitemhandler.attachment.endelementhandler.caption"></a>5.12.3.1. キャプションの解析</h5>

 </div>

 </div>

 </div>

 <p>添付ファイルがプレビュー画像の場合，画像のキャプションを取得します．キャプションはFILEの子要素のCAPTIONで定義されるので，CAPTIONの終了要素の解析で_cdataメンバー変数からキャプションを取得します．取得したキャプションはファイルオブジェクトにセットします．</p>

 <pre class="programlisting">

case 'ITEM/DETAIL/FILE/CAPTION':

 $unicode =&amp; xoonips_getutility( 'unicode' );

 $this -&gt; _file_member -&gt; set(

 'caption',

 $unicode-&gt;decode_utf8(

 $this -&gt; _cdata ,xoonips_get_server_charset(),'h') );

 }

 break;

 </pre>

 </div>

 <div class="section" lang="ja" xml:lang="ja">

 <div xmlns="" class="titlepage">

 <div>

 <div>

 <h5 xmlns="http://www.w3.org/1999/xhtml" class="title"><a id="import.implement.importitemhandler.attachment.endelementhandler.thumbnail"></a>5.12.3.2. サムネイル画像の解析</h5>

 </div>

 </div>

 </div>

 <p>添付ファイルがプレビュー画像の場合，画像のサムネイル画像を取得します．サムネイル画像はFILEの子要素のCAPTIONで定義されるので，CAPTIONの終了要素の解析で_cdataメンバー変数からサムネイル画像を取得します．取得したサムネイル画像はbase64でエンコードされた文字列なので，デコードした上でファイルオブジェクトにセットします．</p>

 <pre class="programlisting">

case 'ITEM/DETAIL/FILE/THUMBNAIL':

 $this -&gt; _file_member -&gt; set( 'thumbnail_file',

 base64_decode( $this -&gt; _cdata ) );

 break;

</pre>

 </div>

 <div class="section" lang="ja" xml:lang="ja">

 <div xmlns="" class="titlepage">

 <div>

 <div>

 <h5 xmlns="http://www.w3.org/1999/xhtml" class="title"><a id="import.implement.importitemhandler.attachment.endelementhandler.insert"></a>5.12.3.3. ファイルをデータベースへ記録</h5>

 </div>

 </div>

 </div>

 <p>FILEの終了要素の解析で，ファイルオブジェクトの内容をデータベースに記録します．記録したファイルオブジェクトを，インポートアイテムオブジェクトにセットします．</p>

 <p>この時点でアイテムIDは確定していないため，記録されるファイルオブジェクトにもアイテムIDは記録されません．アイテムのインポートが成功しアイテムIDが確定した後，ファイルオブジェクトのアイテムIDを更新します．アイテムIDの更新は，インポート終了イベント処理メソッド(<a href="import.html#import.implement.importitemhandler.attachment.onimportfinished" title="5.12.4. インポート終了イベント処理メソッドの定義">項5.12.4. 「インポート終了イベント処理メソッドの定義」</a>)で行います．</p>

 <pre class="programlisting">

case "ITEM/DETAIL/FILE":

 $file_handler =&amp; xoonips_getormhandler( 'xoonips', 'file' );

 if( !$file_handler -&gt; insert( $this -&gt; _file_member ) ){

 $this -&gt; _import_item -&gt; setErrors(

 E_XOONIPS_DB_QUERY,

 "can't insert attachment file:"

 . $this -&gt; _file_member -&gt; get( 'original_file_name' )

 . $this -&gt; _get_parser_error_at() );

 }

 $this -&gt; _file_member = $file_handler -&gt; get(

 $this -&gt; _file_member -&gt; get( 'file_id' ) );

 $this -&gt; _import_item -&gt; setVar( 'file_member',

 $this -&gt; _file_member );

 $this -&gt; _import_item -&gt; setHasDataFile();

 break;

 </pre>

 </div>

 </div>

 <div class="section" lang="ja" xml:lang="ja">

 <div xmlns="" class="titlepage">

 <div>

 <div>

 <h4 xmlns="http://www.w3.org/1999/xhtml" class="title"><a id="import.implement.importitemhandler.attachment.onimportfinished"></a>5.12.4. インポート終了イベント処理メソッドの定義</h4>

 </div>

 </div>

 </div>

 <p>

 </p>

 <pre class="programlisting">void onImportFinished( &amp;$item, &amp;$import_items )</pre>

 <p>

 </p>

 <p>要求されたインポートが全て成功した場合に限り，システ

 ムは，インポート終了イベント処理メソッド関数をコールバッ

 クします．インポートされた各アイテム毎に，このメソッ

 ドがコールバックされます．

 </p>

 <pre class="programlisting">

//コールバック処理のイメージ

//(実際にはそれぞれのアイテムタイプに対応した

//インポートアイテムハンドラのメソッドをコールバックします．)

foreach( $import_items as $item ){

 $handler-&gt;onImportFinished($item, $import_items);

}

 </pre>

 <p>

 </p>

 <p>引数は以下の通りです．</p>

 <div class="itemizedlist">

 <ul type="disc">

 <li>

 <p>$item：インポートされたアイテム</p>

 </li>

 <li>

 <p>$import_items：インポートされた全てのアイテムの配列</p>

 </li>

 </ul>

 </div>

 <p>このメソッドでは以下の処理を定義します．</p>

 <div class="itemizedlist">

 <ul type="disc">

 <li>

 <p>既存の添付ファイルの削除</p>

 </li>

 <li>

 <p>添付ファイル情報の更新</p>

 </li>

 <li>

 <p>全文検索インデックスの作成</p>

 </li>

 <li>

 <p>スーパークラスの呼び出し</p>

 </li>

 </ul>

 </div>

 <div class="section" lang="ja" xml:lang="ja">

 <div xmlns="" class="titlepage">

 <div>

 <div>

 <h5 xmlns="http://www.w3.org/1999/xhtml" class="title"><a id="import.implement.importitemhandler.attachment.onimportfinished.deleleteoldattachment"></a>5.12.4.1. 既存の添付ファイルの削除</h5>

 </div>

 </div>

 </div>

 <p>既存アイテムに上書きインポートした場合に限り，以前

 添付されていたファイルを削除します．この処理はスーパー

 クラスのメソッドとして定義されています．以下のように呼

 び出してください．呼び出し側で，上書きインポートである

 か否かをチェックする必要はありません．</p>

 <pre class="programlisting">

$this -&gt; _set_file_delete_flag($item);

 </pre>

 </div>

 <div class="section" lang="ja" xml:lang="ja">

 <div xmlns="" class="titlepage">

 <div>

 <div>

 <h5 xmlns="http://www.w3.org/1999/xhtml" class="title"><a id="import.implement.importitemhandler.attachment.onimportfinished.updateattachment"></a>5.12.4.2. 添付ファイル情報の更新</h5>

 </div>

 </div>

 </div>

 <p>

 <a href="import.html#import.implement.importitemhandler.attachment.endelementhandler.insert" title="5.12.3.3. ファイルをデータベースへ記録">項5.12.3.3. 「ファイルをデータベースへ記録」</a>

 で述べたように，インポートの成功によって確定したアイテム

 IDを添付ファイルにセットします．処理はスーパークラスのメ

 ソッドとして定義されているので，以下のように呼び出してく

 ださい．$itemはこのメソッドの第一引数で与えられたインポー

 トアイテムオブジェクトです．

 </p>

 <pre class="programlisting">

$file_member =&amp; $item -&gt; getVar( 'file_member' );

$this -&gt; _fix_item_id_of_file( $item, $file_member );

 </pre>

 </div>

 <div class="section" lang="ja" xml:lang="ja">

 <div xmlns="" class="titlepage">

 <div>

 <div>

 <h5 xmlns="http://www.w3.org/1999/xhtml" class="title"><a id="import.implement.importitemhandler.attachment.onimportfinished.createtextsearchindex"></a>5.12.4.3. 全文検索インデックスの作成</h5>

 </div>

 </div>

 </div>

 <p>

 添付ファイルの内容を検索可能にするため，全文検索インデッ

 クスを作成します．処理はスーパークラスのメソッドとして定

 義されているので，以下のように呼び出してください．$itemは

 このメソッドの第一引数で与えられたインポートアイテムオブ

 ジェクトです．$itemから添付ファイルのオブジェクトを取得し，

 それをメソッドの引数に指定してください．

 </p>

 <pre class="programlisting">

$file_member =&amp; $item -&gt; getVar( 'file_member' );

$this -&gt; _create_text_search_index( $file_member );

 </pre>

 </div>

 <div class="section" lang="ja" xml:lang="ja">

 <div xmlns="" class="titlepage">

 <div>

 <div>

 <h5 xmlns="http://www.w3.org/1999/xhtml" class="title"><a id="import.implement.importitemhandler.attachment.onimportfinished.callsuper"></a>5.12.4.4. スーパークラスの呼び出し</h5>

 </div>

 </div>

 </div>

 <p>

 最後に，スーパークラスの同名のメソッドを呼び出します．

 スーパークラスでは，インポートしたアイテム同士の関連ア

 イテムを構築するため，確定したアイテムIDを関連アイテム

 情報にセットしています．

 </p>

 <pre class="programlisting">

parent::onImportFinished( $item, $import_items );

 </pre>

 </div>

 </div>

 </div>

 </div>

 <div class="section" lang="ja" xml:lang="ja">

 <div xmlns="" class="titlepage">

 <div>

 <div>

 <h2 xmlns="http://www.w3.org/1999/xhtml" class="title" style="clear: both"><a id="import.implement.functions"></a>6. そのほかの関数</h2>

 </div>

 </div>

 </div>

 <div class="section" lang="ja" xml:lang="ja">

 <div xmlns="" class="titlepage">

 <div>

 <div>

 <h3 xmlns="http://www.w3.org/1999/xhtml" class="title"><a id="import.implement.functions.seterrors"></a>6.1. エラー関数(setErrors)</h3>

 </div>

 </div>

 </div>

 <p>

 </p>

 <pre class="programlisting">XooNIpsImportItem::setErrors($err_code, $err_str)</pre>

 <p>

 </p>

 <p>処理中にエラーが発生した場合は，このメソッドを使ってエラー情報を記録します．システムがこの情報を参照し，処理の成否の判断，エラー情報の出力などを行います．インポートアイテムハンドラの処理中にエラーが発生したばあいは，以下のように_import_itemメンバー変数にoエラー情報をセットします．</p>

 <pre class="programlisting">

$this -&gt; _import_item -&gt; setErrors( E_XOONIPS_ATTACHMENT_HAS_REDUNDANT,

 "multiple attachment is not allowed" );

 </pre>

 <p>引数は以下のとおりです．</p>

 <div class="itemizedlist">

 <ul type="disc">

 <li>

 <p>$err_code：エラーコード</p>

 </li>

 <li>

 <p>$err_str：エラー内容を表すテキスト</p>

 </li>

 </ul>

 </div>

 <p>$err_codeはあらかじめ定められた以下のエラーコードから適当なコードを一つ選んで使用します．これらはcondefs.hで定義されます．

 </p>

 <div class="table">

 <a id="table.import.implement.functions.seterrors.errorcodes"></a>

 <p class="title">

 <b>表 20.8. エラーコード一覧</b>

 </p>

 <div class="table-contents">

 <table summary="エラーコード一覧" cellspacing="0" cellpadding="5" border="0" style="border-collapse: collapse;border-top: 0.5pt solid ; border-bottom: 0.5pt solid ; border-left: 0.5pt solid ; border-right: 0.5pt solid ; ">

 <colgroup>

 <col />

 <col />

 <col />

 </colgroup>

 <thead>

 <tr>

 <th style="border-right: 0.5pt solid ; border-bottom: 0.5pt solid ; " align="left">エラーコード定義名</th>

 <th style="border-right: 0.5pt solid ; border-bottom: 0.5pt solid ; " align="left">値</th>

 <th style="border-bottom: 0.5pt solid ; " align="left">概要</th>

 </tr>

 </thead>

 <tbody>

 <tr>

 <td style="border-right: 0.5pt solid ; border-bottom: 0.5pt solid ; " align="left">E_XOONIPS_SUCCESS</td>

 <td style="border-right: 0.5pt solid ; border-bottom: 0.5pt solid ; " align="left">E0000</td>

 <td style="border-bottom: 0.5pt solid ; " align="left">成功</td>

 </tr>

 <tr>

 <td style="border-right: 0.5pt solid ; border-bottom: 0.5pt solid ; " align="left">E_XOONIPS_ERROR</td>

 <td style="border-right: 0.5pt solid ; border-bottom: 0.5pt solid ; " align="left">E0001</td>

 <td style="border-bottom: 0.5pt solid ; " align="left">エラー</td>

 </tr>

 <tr>

 <td style="border-right: 0.5pt solid ; border-bottom: 0.5pt solid ; " align="left">E_XOONIPS_PARSER</td>

 <td style="border-right: 0.5pt solid ; border-bottom: 0.5pt solid ; " align="left">E0002</td>

 <td style="border-bottom: 0.5pt solid ; " align="left">XMLパース処理のエラー</td>

 </tr>

 <tr>

 <td style="border-right: 0.5pt solid ; border-bottom: 0.5pt solid ; " align="left">E_XOONIPS_USER_NOT_FOUND</td>

 <td style="border-right: 0.5pt solid ; border-bottom: 0.5pt solid ; " align="left">E0003</td>

 <td style="border-bottom: 0.5pt solid ; " align="left">ユーザが見つからない</td>

 </tr>

 <tr>

 <td style="border-right: 0.5pt solid ; border-bottom: 0.5pt solid ; " align="left">E_XOONIPS_DB_QUERY</td>

 <td style="border-right: 0.5pt solid ; border-bottom: 0.5pt solid ; " align="left">E0004</td>

 <td style="border-bottom: 0.5pt solid ; " align="left">DB操作中のエラー</td>

 </tr>

 <tr>

 <td style="border-right: 0.5pt solid ; border-bottom: 0.5pt solid ; " align="left">E_XOONIPS_ATTR_REDUNDANT</td>

 <td style="border-right: 0.5pt solid ; border-bottom: 0.5pt solid ; " align="left">E0005</td>

 <td style="border-bottom: 0.5pt solid ; " align="left">冗長(排他使用の属性が両方指定されているなど)</td>

 </tr>

 <tr>

 <td style="border-right: 0.5pt solid ; border-bottom: 0.5pt solid ; " align="left">E_XOONIPS_ATTR_NOT_FOUND</td>

 <td style="border-right: 0.5pt solid ; border-bottom: 0.5pt solid ; " align="left">E0006</td>

 <td style="border-bottom: 0.5pt solid ; " align="left">属性が定義されていない</td>

 </tr>

 <tr>

 <td style="border-right: 0.5pt solid ; border-bottom: 0.5pt solid ; " align="left">E_XOONIPS_ATTR_INVALID_VALUE</td>

 <td style="border-right: 0.5pt solid ; border-bottom: 0.5pt solid ; " align="left">E0007</td>

 <td style="border-bottom: 0.5pt solid ; " align="left">属性値が無効(形式異常，未知の属性値など)</td>

 </tr>

 <tr>

 <td style="border-right: 0.5pt solid ; border-bottom: 0.5pt solid ; " align="left">E_XOONIPS_DATA_TOO_LONG</td>

 <td style="border-right: 0.5pt solid ; border-bottom: 0.5pt solid ; " align="left">E0008</td>

 <td style="border-bottom: 0.5pt solid ; " align="left">指定されたデータが長すぎる</td>

 </tr>

 <tr>

 <td style="border-right: 0.5pt solid ; border-bottom: 0.5pt solid ; " align="left">E_XOONIPS_INDEX_NOT_FOUND</td>

 <td style="border-right: 0.5pt solid ; border-bottom: 0.5pt solid ; " align="left">E0009</td>

 <td style="border-bottom: 0.5pt solid ; " align="left">指定インデックスが存在しない</td>

 </tr>

 <tr>

 <td style="border-right: 0.5pt solid ; border-bottom: 0.5pt solid ; " align="left">E_XOONIPS_OPEN_FILE</td>

 <td style="border-right: 0.5pt solid ; border-bottom: 0.5pt solid ; " align="left">E0010</td>

 <td style="border-bottom: 0.5pt solid ; " align="left">ファイルのオープンに失敗</td>

 </tr>

 <tr>

 <td style="border-right: 0.5pt solid ; border-bottom: 0.5pt solid ; " align="left">E_XOONIPS_RELATED_ITEM_IS_NOT_FOUND</td>

 <td style="border-right: 0.5pt solid ; border-bottom: 0.5pt solid ; " align="left">E0011</td>

 <td style="border-bottom: 0.5pt solid ; " align="left">指定された関連アイテムが見つからない</td>

 </tr>

 <tr>

 <td style="border-right: 0.5pt solid ; border-bottom: 0.5pt solid ; " align="left">E_XOONIPS_FILE_SYSTEM</td>

 <td style="border-right: 0.5pt solid ; border-bottom: 0.5pt solid ; " align="left">E0012</td>

 <td style="border-bottom: 0.5pt solid ; " align="left">ファイルシステム全般</td>

 </tr>

 <tr>

 <td style="border-right: 0.5pt solid ; border-bottom: 0.5pt solid ; " align="left">E_XOONIPS_IMPORT</td>

 <td style="border-right: 0.5pt solid ; border-bottom: 0.5pt solid ; " align="left">E0013</td>

 <td style="border-bottom: 0.5pt solid ; " align="left">インポート操作のエラー</td>

 </tr>

 <tr>

 <td style="border-right: 0.5pt solid ; border-bottom: 0.5pt solid ; " align="left">E_XOONIPS_INVALID_VALUE</td>

 <td style="border-right: 0.5pt solid ; border-bottom: 0.5pt solid ; " align="left">E0014</td>

 <td style="border-bottom: 0.5pt solid ; " align="left">CDATA値の形式異常，未知の値</td>

 </tr>

 <tr>

 <td style="border-right: 0.5pt solid ; border-bottom: 0.5pt solid ; " align="left">E_XOONIPS_VALUE_IS_REQUIRED</td>

 <td style="border-right: 0.5pt solid ; border-bottom: 0.5pt solid ; " align="left">E0015</td>

 <td style="border-bottom: 0.5pt solid ; " align="left">必須の値が指定されていない</td>

 </tr>

 <tr>

 <td style="border-right: 0.5pt solid ; border-bottom: 0.5pt solid ; " align="left">E_XOONIPS_NO_PRIVATE_INDEX</td>

 <td style="border-right: 0.5pt solid ; border-bottom: 0.5pt solid ; " align="left">E0016</td>

 <td style="border-bottom: 0.5pt solid ; " align="left">インポートするアイテムがプライベートインデックスに登録されない</td>

 </tr>

 <tr>

 <td style="border-right: 0.5pt solid ; border-bottom: 0.5pt solid ; " align="left">E_XOONIPS_ATTACHMENT_HAS_REDUNDANT</td>

 <td style="border-right: 0.5pt solid ; border-bottom: 0.5pt solid ; " align="left">E0017</td>

 <td style="border-bottom: 0.5pt solid ; " align="left">必要以上の添付ファイルをインポートしようとした</td>

 </tr>

 <tr>

 <td style="border-right: 0.5pt solid ; border-bottom: 0.5pt solid ; " align="left">E_XOONIPS_NOT_PERMITTED_ACCESS</td>

 <td style="border-right: 0.5pt solid ; border-bottom: 0.5pt solid ; " align="left">E0018</td>

 <td style="border-bottom: 0.5pt solid ; " align="left">アイテム，インデックスなどへのアクセス権限がない</td>

 </tr>

 <tr>

 <td style="border-right: 0.5pt solid ; border-bottom: 0.5pt solid ; " align="left">E_XOONIPS_TAG_NOT_FOUND</td>

 <td style="border-right: 0.5pt solid ; border-bottom: 0.5pt solid ; " align="left">E0019</td>

 <td style="border-bottom: 0.5pt solid ; " align="left">省略できないXMLタグが見つからない</td>

 </tr>

 <tr>

 <td style="border-right: 0.5pt solid ; border-bottom: 0.5pt solid ; " align="left">E_XOONIPS_INVALID_VERSION</td>

 <td style="border-right: 0.5pt solid ; border-bottom: 0.5pt solid ; " align="left">E0020</td>

 <td style="border-bottom: 0.5pt solid ; " align="left">未知のバージョン(version属性値)</td>

 </tr>

 <tr>

 <td style="border-right: 0.5pt solid ; border-bottom: 0.5pt solid ; " align="left">E_XOONIPS_PSEUDO_ID_CONFLICT</td>

 <td style="border-right: 0.5pt solid ; border-bottom: 0.5pt solid ; " align="left">E0021</td>

 <td style="border-bottom: 0.5pt solid ; " align="left">同じIDを持つ複数のXMLファイルがインポートファイル中で見つかった</td>

 </tr>

 <tr>

 <td style="border-right: 0.5pt solid ; border-bottom: 0.5pt solid ; " align="left">E_XOONIPS_RELATED_TO_CONFLICTING_ITEM</td>

 <td style="border-right: 0.5pt solid ; border-bottom: 0.5pt solid ; " align="left">E0022</td>

 <td style="border-bottom: 0.5pt solid ; " align="left">関連アイテムが重複している</td>

 </tr>

 <tr>

 <td style="border-right: 0.5pt solid ; border-bottom: 0.5pt solid ; " align="left">E_XOONIPS_TAG_REDUNDANT</td>

 <td style="border-right: 0.5pt solid ; border-bottom: 0.5pt solid ; " align="left">E0023</td>

 <td style="border-bottom: 0.5pt solid ; " align="left">冗長なタグ（タグが重複している、使用回数が多すぎる）</td>

 </tr>

 <tr>

 <td style="border-right: 0.5pt solid ; border-bottom: 0.5pt solid ; " align="left">E_XOONIPS_DOI_CONFLICT</td>

 <td style="border-right: 0.5pt solid ; border-bottom: 0.5pt solid ; " align="left">E0024</td>

 <td style="border-bottom: 0.5pt solid ; " align="left">アイテムのDOIフィールドの値が既存のアイテムと重複している</td>

 </tr>

 <tr>

 <td style="border-right: 0.5pt solid ; " align="left">E_XOONIPS_UPDATE_CERTIFY_REQUEST_LOCKED</td>

 <td style="border-right: 0.5pt solid ; " align="left">E0025</td>

 <td style="" align="left">アイテムがロックされているため更新できない</td>

 </tr>

 </tbody>

 </table>

 </div>

 </div>

 <p><br class="table-break" />

 </p>

 </div>

 </div>

 </div>

 <div xmlns="http://www.w3.org/1999/xhtml" class="navfooter">



 </div>

 </div>

 </body>


