 <body>

 <div id="page">

 <div xmlns="http://www.w3.org/1999/xhtml" class="navheader">

 </div>

 <div xmlns="http://www.w3.org/1999/xhtml" class="chapter" lang="ja" id="quicksearch" xml:lang="ja">

 <div xmlns="" class="titlepage">

 <div>

 <div>

 <h2 xmlns="http://www.w3.org/1999/xhtml" class="title"><a id="quicksearch"></a>第15章 簡易検索</h2>

 </div>

 </div>

 </div>

 <p>アイテムタイプモジュールの以下の関数に簡易検索用クエリを作成する処理を定義してください． </p>

 <div class="itemizedlist">

 <ul type="disc">

 <li>

 <p>function &lt;モジュール名&gt;GetDetailInformationQuickSearchQuery( &amp;$wheres, &amp;$join, $keywords )</p>

 <div class="itemizedlist">

 <ul type="circle">

 <li>

 <p>引数 : $wheres (SQL の WHERE 節に使用する式の配列)</p>

 </li>

 <li>

 <p>引数 : $join (SQL の JOIN 節に使用する式)</p>

 </li>

 <li>

 <p>引数 : $keywords (検索語句の配列)</p>

 </li>

 <li>

 <p>戻り値 : なし</p>

 </li>

 </ul>

 </div>

 </li>

 </ul>

 </div>

 <p>$join の意味は GetAdvancedSearchQuery と同様です．<a href="advancedsearch.html" title="第16章 詳細検索">章 16. <i>詳細検索</i></a>を参照してください．</p>

 <p>$wheres には，以下のような配列を書く必要があります．</p>

 <div class="itemizedlist">

 <ul type="disc">

 <li>

 <p>$wheres の要素数は $keywords の要素数と同じ</p>

 </li>

 <li>

 <p>$wheres[n] は，「Detail Information が $keywords[n] を含む」 を表す SQL 式</p>

 </li>

 </ul>

 </div>

 <p>但し，Detail Information がどのキーワードも含まないことが前もってわかっている場合は，$wheres に何も書かなくても問題ありません．</p>

 <p>その他の注意点は以下のとおりです．</p>

 <div class="itemizedlist">

 <ul type="disc">

 <li>

 <p>xoops_(モジュール名)_item_detail はデフォルトで JOIN されるので $joinに書く必要は無い．他に JOIN すべきテーブルが無い場合は，$join には何も書かなくて良い．</p>

 </li>

 <li>

 <p>SQL 式でのカラムの指定は，必ずテーブル名を含む形で指定すること．</p>

 <div class="itemizedlist">

 <ul type="circle">

 <li>

 <p>例: 'pubmed_id' → $xoopsDB-&gt;prefix('xnppaper_item_detail') . '.pubmed_id'</p>

 </li>

 </ul>

 </div>

 </li>

 <li>

 <p>$wheres の生成には，xnpGetKeywordsQueries を使用できる．</p>

 </li>

 </ul>

 </div>

 <p>以下の関数も参照してください．</p>

 <div class="itemizedlist">

 <ul type="disc">

 <li>

 <p>xnpGetKeywordQuery</p>

 </li>

 <li>

 <p>xnpGetKeywordsQueries</p>

 </li>

 </ul>

 </div>

 </div>

 <div xmlns="http://www.w3.org/1999/xhtml" class="navfooter">



 </div>

 </div>

 </body>


