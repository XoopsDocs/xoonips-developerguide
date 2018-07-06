 <body>

 

 <div xmlns="http://www.w3.org/1999/xhtml" class="chapter" lang="ja" id="metainfo" xml:lang="ja">

 <div xmlns="" class="titlepage">

 <div>

 <div>

 <h2 xmlns="http://www.w3.org/1999/xhtml" class="title"><a id="metainfo"></a>第9章 メタ情報</h2>

 </div>

 </div>

 </div>

 <div class="section" lang="ja" xml:lang="ja">

 <div xmlns="" class="titlepage">

 <div>

 <div>

 <h2 xmlns="http://www.w3.org/1999/xhtml" class="title" style="clear: both"><a id="func-xnpGetBasicInformationArray"></a>1. array xnpGetBasicInformationArray( int item_id )</h2>

 </div>

 </div>

 </div>

 <p>アイテムの Basic Information を返します．</p>

 <p>{$modulename}GetMetaInformationからの呼び出しを前提とした関数です．</p>

 <div class="section" lang="ja" xml:lang="ja">

 <div xmlns="" class="titlepage">

 <div>

 <div>

 <h3 xmlns="http://www.w3.org/1999/xhtml" class="title"><a id="func-xnpGetBasicInformationArray-retval"></a>1.1. 戻り値</h3>

 </div>

 </div>

 </div>

 <p>引数で指定された item_id に対応するアイテム情報を連想配列で返します．</p>

 <p>連想配列の構造は以下の通りです．</p>

 <div class="blockquote">

 <blockquote class="blockquote">

 <pre class="programlisting">array( key1 =&gt; value1, key2 =&gt; value2, … )</pre>

 </blockquote>

 </div>

 <p>キーは先頭から以下の順に並びます．</p>

 <div class="itemizedlist">

 <ul type="disc">

 <li>

 <p>'item_type' : アイテムタイプの表示名</p>

 </li>

 <li>

 <p>'title' : タイトル文字列</p>

 </li>

 <li>

 <p>'contributor' : アイテム作成者の名前</p>

 </li>

 <li>

 <p>'keywords' : フリーキーワード</p>

 </li>

 <li>

 <p>'description' : コメント</p>

 </li>

 <li>

 <p>'doi' : DOI文字列</p>

 </li>

 <li>

 <p>'last_update_date' : 最終更新日時の文字列</p>

 </li>

 <li>

 <p>'creation_date' : アイテム作成日時の文字列</p>

 </li>

 <li>

 <p>'publication_year' : アイテム内容に関連する西暦</p>

 </li>

 <li>

 <p>'publication_month' : アイテム内容に関連する月(1-12)</p>

 </li>

 <li>

 <p>'publication_mday' : アイテム内容に関連する日(1-31)</p>

 </li>

 <li>

 <p>'lang' : 言語</p>

 </li>

 </ul>

 </div>

 </div>

 </div>

 <div class="section" lang="ja" xml:lang="ja">

 <div xmlns="" class="titlepage">

 <div>

 <div>

 <h2 xmlns="http://www.w3.org/1999/xhtml" class="title" style="clear: both"><a id="func-xnpBasicInformation2XML"></a>2. bool xnpBasicInformation2XML( resource fhdl, array item, bool is_absolute, int base_index_id=false )</h2>

 </div>

 </div>

 </div>

 <p>アイテムの Basic Information を，外部アプリと交換するためのXMLに変換してファイルに出力します．</p>

 <div class="section" lang="ja" xml:lang="ja">

 <div xmlns="" class="titlepage">

 <div>

 <div>

 <h3 xmlns="http://www.w3.org/1999/xhtml" class="title"><a id="func-xnpBasicInformation2XML-inpval"></a>2.1. 入力</h3>

 </div>

 </div>

 </div>

 <div class="itemizedlist">

 <ul type="disc">

 <li>

 <p>fhdl : 出力先のファイルハンドル</p>

 </li>

 <li>

 <p>item : 変換したいアイテムのBasic Informationの連想配列</p>

 </li>

 <li>

 <p>is_absolute, base_index_id : XMLのインデックスタグのCDATA部の指定．</p>

 <div class="itemizedlist">

 <ul type="circle">

 <li>

 <p>is_absoluteがtrueなら，base_index_idは無視される．インデックスタグのCDATA部は，インデックスを絶対パスで表した文字列になる．</p>

 </li>

 <li>

 <p>is_absoluteがfalseかつbase_index_idがfalseなら，インデックスタグのCDATA部は空文字列になる．</p>

 </li>

 <li>

 <p>is_absoluteがfalseかつbase_index_idがfalseでないなら，インデックスタグのCDATA部は，base_index_idの子孫のインデックスのみをbase_index_idからの相対パスで表した文字列になる．</p>

 </li>

 </ul>

 </div>

 </li>

 </ul>

 </div>

 <p>連想配列itemの構造は以下の通りです．</p>

 <div class="blockquote">

 <blockquote class="blockquote">

 <pre class="programlisting">array( key1 =&gt; value1, key2 =&gt; value2, … )</pre>

 </blockquote>

 </div>

 <div class="itemizedlist">

 <ul type="disc">

 <li>

 <p>'item_id' : アイテムID</p>

 </li>

 <li>

 <p>'item_type' : アイテムタイプの表示名</p>

 </li>

 <li>

 <p>'title' : タイトル文字列</p>

 </li>

 <li>

 <p>'contributor' : アイテム作成者の名前</p>

 </li>

 <li>

 <p>'keywords' : フリーキーワード</p>

 </li>

 <li>

 <p>'description' : コメント</p>

 </li>

 <li>

 <p>'doi' : DOI文字列</p>

 </li>

 <li>

 <p>'last_update_date' : 最終更新日時の文字列</p>

 </li>

 <li>

 <p>'creation_date' : アイテム作成日時の文字列</p>

 </li>

 <li>

 <p>'publication_year' : アイテム内容に関連する西暦</p>

 </li>

 <li>

 <p>'publication_month' : アイテム内容に関連する月(1-12)</p>

 </li>

 <li>

 <p>'publication_mday' : アイテム内容に関連する日(1-31)</p>

 </li>

 <li>

 <p>'lang' : 言語</p>

 </li>

 </ul>

 </div>

 </div>

 <div class="section" lang="ja" xml:lang="ja">

 <div xmlns="" class="titlepage">

 <div>

 <div>

 <h3 xmlns="http://www.w3.org/1999/xhtml" class="title"><a id="func-xnpBasicInformation2XML-retval"></a>2.2. 戻り値</h3>

 </div>

 </div>

 </div>

 <div class="itemizedlist">

 <ul type="disc">

 <li>

 <p>true : 成功</p>

 </li>

 <li>

 <p>false : 失敗</p>

 </li>

 </ul>

 </div>

 </div>

 </div>

 </div>

 <div xmlns="http://www.w3.org/1999/xhtml" class="navfooter">


 </body>


