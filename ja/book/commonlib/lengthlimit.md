 <body>


 <div xmlns="http://www.w3.org/1999/xhtml" class="chapter" lang="ja" id="lengthlimit" xml:lang="ja">

 <div xmlns="" class="titlepage">

 <div>

 <div>

 <h2 xmlns="http://www.w3.org/1999/xhtml" class="title"><a id="lengthlimit"></a>第12章 文字数制限</h2>

 </div>

 </div>

 </div>

 <div class="section" lang="ja" xml:lang="ja">

 <div xmlns="" class="titlepage">

 <div>

 <div>

 <h2 xmlns="http://www.w3.org/1999/xhtml" class="title" style="clear: both"><a id="func-xnpTrimString"></a>1. array xnpTrimString( string str, int length, string enc=null )</h2>

 </div>

 </div>

 </div>

 <p>strの頭から，lengthバイト以下かつマルチバイト文字・数値文字参照の途中でないような文字列を切り出します．</p>

 <div class="section" lang="ja" xml:lang="ja">

 <div xmlns="" class="titlepage">

 <div>

 <div>

 <h3 xmlns="http://www.w3.org/1999/xhtml" class="title"><a id="func-xnpTrimString-inpval"></a>1.1. 入力</h3>

 </div>

 </div>

 </div>

 <div class="itemizedlist">

 <ul type="disc">

 <li>

 <p>str : 文字列</p>

 </li>

 <li>

 <p>length :切り出すバイト数</p>

 </li>

 <li>

 <p>enc : strのエンコード．nullなら自動判別する．</p>

 </li>

 </ul>

 </div>

 </div>

 <div class="section" lang="ja" xml:lang="ja">

 <div xmlns="" class="titlepage">

 <div>

 <div>

 <h3 xmlns="http://www.w3.org/1999/xhtml" class="title"><a id="func-xnpTrimString-retval"></a>1.2. 戻り値</h3>

 </div>

 </div>

 </div>

 <div class="itemizedlist">

 <ul type="disc">

 <li>

 <p>array( 切り出した文字列, 残りの文字列 )</p>

 </li>

 </ul>

 </div>

 </div>

 </div>

 <div class="section" lang="ja" xml:lang="ja">

 <div xmlns="" class="titlepage">

 <div>

 <div>

 <h2 xmlns="http://www.w3.org/1999/xhtml" class="title" style="clear: both"><a id="func-xnpTrimColumn"></a>2. void xnpTrimColumn( array &amp;assoc, string table_without_prefix, array names=null, string enc=null )</h2>

 </div>

 </div>

 </div>

 <p>複数の文字列から，DBに収まる部分だけを切り出します．</p>

 <div class="section" lang="ja" xml:lang="ja">

 <div xmlns="" class="titlepage">

 <div>

 <div>

 <h3 xmlns="http://www.w3.org/1999/xhtml" class="title"><a id="func-xnpTrimColumn-inpval"></a>2.1. 入力</h3>

 </div>

 </div>

 </div>

 <div class="itemizedlist">

 <ul type="disc">

 <li>

 <p>assoc : 連想配列 array( カラム名=&gt;文字列 ) ． </p>

 </li>

 <li>

 <p>table_without_prefix :テーブル名(prefixを除く)</p>

 </li>

 <li>

 <p>names : カラム名の配列．assoc中の処理すべき文字列を指定します．nullなら全て処理します．</p>

 </li>

 <li>

 <p>enc : strのエンコード．nullなら自動判別する．</p>

 </li>

 </ul>

 </div>

 </div>

 <div class="section" lang="ja" xml:lang="ja">

 <div xmlns="" class="titlepage">

 <div>

 <div>

 <h3 xmlns="http://www.w3.org/1999/xhtml" class="title"><a id="func-xnpTrimColumn-retval"></a>2.2. 戻り値</h3>

 </div>

 </div>

 </div>

 <div class="itemizedlist">

 <ul type="disc">

 <li>

 <p>なし．関数実行後のassocは，array( カラム名=&gt;切り出した文字列 ) となります．</p>

 </li>

 </ul>

 </div>

 </div>

 </div>

 <div class="section" lang="ja" xml:lang="ja">

 <div xmlns="" class="titlepage">

 <div>

 <div>

 <h2 xmlns="http://www.w3.org/1999/xhtml" class="title" style="clear: both"><a id="func-xnpConfirmHtml"></a>3. void xnpConfirmHtml( array &amp;assoc, string table_without_prefix, array names=null, string enc=null )</h2>

 </div>

 </div>

 </div>

 <p>複数の文字列から，(DBに収まる部分，収まらない部分，確認画面表示用html，文字列のhtml) を生成します．</p>

 <div class="section" lang="ja" xml:lang="ja">

 <div xmlns="" class="titlepage">

 <div>

 <div>

 <h3 xmlns="http://www.w3.org/1999/xhtml" class="title"><a id="func-xnpConfirmHtml-inpval"></a>3.1. 入力</h3>

 </div>

 </div>

 </div>

 <div class="itemizedlist">

 <ul type="disc">

 <li>

 <p>assoc : 連想配列 array( カラム名=&gt;array( 'value'=&gt;文字列 ) ) ． </p>

 </li>

 <li>

 <p>table_without_prefix : テーブル名(prefixを除く)</p>

 </li>

 <li>

 <p>names : カラム名の配列．assoc中の処理すべき文字列を指定します．nullなら全て処理します．</p>

 </li>

 <li>

 <p>enc : strのエンコード．nullなら自動判別する．</p>

 </li>

 </ul>

 </div>

 </div>

 <div class="section" lang="ja" xml:lang="ja">

 <div xmlns="" class="titlepage">

 <div>

 <div>

 <h3 xmlns="http://www.w3.org/1999/xhtml" class="title"><a id="func-xnpConfirmHtml-retval"></a>3.2. 戻り値</h3>

 </div>

 </div>

 </div>

 <div class="itemizedlist">

 <ul type="disc">

 <li>

 <p>なし．切り出した結果はassocに書き込まれます．関数実行後のassocは，

 array(

 カラム名 =&gt; array( 'value'=&gt;確認画面表示用html , 'within'=&gt;収まる部分 , 'without'=&gt;収まらない部分 , 'html_string'=&gt;文字列のhtml )

 ) となります．

 </p>

 </li>

 </ul>

 </div>

 </div>

 </div>

 <div class="section" lang="ja" xml:lang="ja">

 <div xmlns="" class="titlepage">

 <div>

 <div>

 <h2 xmlns="http://www.w3.org/1999/xhtml" class="title" style="clear: both"><a id="func-xnpHasWithout"></a>4. bool xnpHasWithout( array assoc )</h2>

 </div>

 </div>

 </div>

 <p>xnpConfirmHtmlの結果を見て，DBに収まらない文字列があったかどうかを返します．</p>

 <div class="section" lang="ja" xml:lang="ja">

 <div xmlns="" class="titlepage">

 <div>

 <div>

 <h3 xmlns="http://www.w3.org/1999/xhtml" class="title"><a id="func-xnpHasWithout-inpval"></a>4.1. 入力</h3>

 </div>

 </div>

 </div>

 <div class="itemizedlist">

 <ul type="disc">

 <li>

 <p>assoc : xnpConfirmHtmlに渡したassoc ． </p>

 </li>

 </ul>

 </div>

 </div>

 <div class="section" lang="ja" xml:lang="ja">

 <div xmlns="" class="titlepage">

 <div>

 <div>

 <h3 xmlns="http://www.w3.org/1999/xhtml" class="title"><a id="func-xnpHasWithout-retval"></a>4.2. 戻り値</h3>

 </div>

 </div>

 </div>

 <div class="itemizedlist">

 <ul type="disc">

 <li>

 <p>DBに収まらない文字列があったならtrueを返します．</p>

 </li>

 </ul>

 </div>

 </div>

 </div>

 <div class="section" lang="ja" xml:lang="ja">

 <div xmlns="" class="titlepage">

 <div>

 <div>

 <h2 xmlns="http://www.w3.org/1999/xhtml" class="title" style="clear: both"><a id="func-xnpGetColumnLengths"></a>5. array xnpGetColumnLengths( string table_without_prefix )</h2>

 </div>

 </div>

 </div>

 <p>テーブルの各カラム(文字列型・バイナリ型のみ)のサイズを得ます．</p>

 <div class="section" lang="ja" xml:lang="ja">

 <div xmlns="" class="titlepage">

 <div>

 <div>

 <h3 xmlns="http://www.w3.org/1999/xhtml" class="title"><a id="func-xnpGetColumnLengths-inpval"></a>5.1. 入力</h3>

 </div>

 </div>

 </div>

 <div class="itemizedlist">

 <ul type="disc">

 <li>

 <p>table_without_prefix : テーブル名(prefixを除く) ． </p>

 </li>

 </ul>

 </div>

 </div>

 <div class="section" lang="ja" xml:lang="ja">

 <div xmlns="" class="titlepage">

 <div>

 <div>

 <h3 xmlns="http://www.w3.org/1999/xhtml" class="title"><a id="func-xnpGetColumnLengths-retval"></a>5.2. 戻り値</h3>

 </div>

 </div>

 </div>

 <div class="itemizedlist">

 <ul type="disc">

 <li>

 <p>連想配列 array( カラム名 =&gt; サイズ(bytes) )</p>

 </li>

 </ul>

 </div>

 </div>

 </div>

 <div class="section" lang="ja" xml:lang="ja">

 <div xmlns="" class="titlepage">

 <div>

 <div>

 <h2 xmlns="http://www.w3.org/1999/xhtml" class="title" style="clear: both"><a id="func-xnpWithinWithoutHtml"></a>6. string xnpWithinWithoutHtml( string within, string without )</h2>

 </div>

 </div>

 </div>

 <p>確認画面用の，一部が赤くなったHTMLを生成します．</p>

 <div class="section" lang="ja" xml:lang="ja">

 <div xmlns="" class="titlepage">

 <div>

 <div>

 <h3 xmlns="http://www.w3.org/1999/xhtml" class="title"><a id="func-xnpWithinWithoutHtml-inpval"></a>6.1. 入力</h3>

 </div>

 </div>

 </div>

 <div class="itemizedlist">

 <ul type="disc">

 <li>

 <p>within : 黒く表示すべき文字列．</p>

 </li>

 <li>

 <p>without : 赤く表示すべき文字列．</p>

 </li>

 </ul>

 </div>

 </div>

 <div class="section" lang="ja" xml:lang="ja">

 <div xmlns="" class="titlepage">

 <div>

 <div>

 <h3 xmlns="http://www.w3.org/1999/xhtml" class="title"><a id="func-xnpWithinWithoutHtml-retval"></a>6.2. 戻り値</h3>

 </div>

 </div>

 </div>

 <div class="itemizedlist">

 <ul type="disc">

 <li>

 <p> within文字列の後に，赤いwithout文字列を結合したHTML </p>

 </li>

 </ul>

 </div>

 </div>

 </div>

 </div>

 <div xmlns="http://www.w3.org/1999/xhtml" class="navfooter">

 <hr />

 <table width="100%" summary="Navigation footer">

 </body>




