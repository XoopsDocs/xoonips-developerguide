 <body>

 <div id="page">

 <div xmlns="http://www.w3.org/1999/xhtml" class="navheader">

 </div>

 <div xmlns="http://www.w3.org/1999/xhtml" class="chapter" lang="ja" id="advancedsearch" xml:lang="ja">

 <div xmlns="" class="titlepage">

 <div>

 <div>

 <h2 xmlns="http://www.w3.org/1999/xhtml" class="title"><a id="advancedsearch"></a>第16章 詳細検索</h2>

 </div>

 </div>

 </div>

 <div class="figure">

 <a id="fig.advancedsearch.workflow"></a>

 <div class="figure-contents">

 <div class="mediaobject">

 <img src="../../assets/itemtype/search-flow.gif" alt="詳細検索の流れ" />

 </div>

 </div>

 <p class="title">

 <b>図 16.1. 詳細検索の流れ</b>

 </p>

 </div>

 <br class="figure-break" />

 <div class="figure">

 <a id="fig.advancedsearch.view-parameter"></a>

 <div class="figure-contents">

 <div class="mediaobject">

 <img src="../../assets/itemtype/search-trans.gif" alt="画面遷移と送信パラメータ" />

 </div>

 </div>

 <p class="title">

 <b>図 16.2. 画面遷移と送信パラメータ</b>

 </p>

 </div>

 <br class="figure-break" />

 <div class="section" lang="ja" xml:lang="ja">

 <div xmlns="" class="titlepage">

 <div>

 <div>

 <h2 xmlns="http://www.w3.org/1999/xhtml" class="title" style="clear: both"><a id="advancedsearch.form"></a>1. 検索フォーム作成</h2>

 </div>

 </div>

 </div>

 <p>アイテムタイプモジュールの以下の関数に詳細検索用クエリを作成する処理を定義してください．</p>

 <div class="itemizedlist">

 <ul type="disc">

 <li>

 <p>function &lt;モジュール名&gt; GetAdvancedSearchBlock( &amp;$search_var )</p>

 <div class="itemizedlist">

 <ul type="circle">

 <li>

 <p>引数 : $search_var (検索条件を代入するパラメータの名前の配列)</p>

 </li>

 <li>

 <p>戻り値 : 検索フォームの HTML</p>

 </li>

 </ul>

 </div>

 </li>

 </ul>

 </div>

 <p>アイテムタイプを検索するためのフォームを作成します．Basic Information と Detail Information の中から検索条件にするフィールドを入力するフォームを作成します．</p>

 <p>Basic Information の条件入力フォーム生成は共通ライブラリに用意された関数を使用します．この関数は Basic Information の検索条件に指定可能なすべてのフィールドのフォームを返しますので，その中でアイテムタイプの検索条件として使いたいフィールドだけを抜き出して使用します．</p>

 <p>Detail Information の検索条件入力フォームはアイテムタイプモジュールで自由に定義できます． </p>

 <p>以下の関数も参照してください．</p>

 <div class="itemizedlist">

 <ul type="disc">

 <li>

 <p>xnpGetKeywordQuery</p>

 </li>

 <li>

 <p>xnpGetKeywordsQueries</p>

 </li>

 <li>

 <p>xnpGetBasicInformationAdvancedSearchBlock</p>

 </li>

 </ul>

 </div>

 <div class="section" lang="ja" xml:lang="ja">

 <div xmlns="" class="titlepage">

 <div>

 <div>

 <h3 xmlns="http://www.w3.org/1999/xhtml" class="title"><a id="advancedsearch.form.arguments"></a>1.1. $search_var 引数について</h3>

 </div>

 </div>

 </div>

 <p>フォームに入力された検索条件を代入するパラメータ名 (&lt;input&gt; タグの name 属性) を $search_var 引数に追加します． アイテムタイプ 'Book' 型の著者の検索条件のパラメータ名が 'xnpbook_author' だとすれば，$search_var[] = 'xnpbook_author'; と追加します．</p>

 <p>パラメータ名が他のアイテムタイプが使用するものと重複するのを防ぐため，パラメータ名の先頭にはモジュール名をつけてください．例えば 'Book' 型の著者の場合はパラメータ名を 'xnpbook_author' とします．タイトル，キーワードなどの Basic Information も，アイテムタイプごとに重複しないように注意してください．</p>

 </div>

 </div>

 <div class="section" lang="ja" xml:lang="ja">

 <div xmlns="" class="titlepage">

 <div>

 <div>

 <h2 xmlns="http://www.w3.org/1999/xhtml" class="title" style="clear: both"><a id="advancedsearch.query"></a>2. 検索クエリ (SQL) 文作成</h2>

 </div>

 </div>

 </div>

 <p>アイテムタイプモジュールの以下の関数に詳細検索フォーム作成処理を定義してください． </p>

 <div class="itemizedlist">

 <ul type="disc">

 <li>

 <p>function &lt;モジュール名&gt; GetAdvancedSearchQuery( &amp;$where, &amp;$join )</p>

 <div class="itemizedlist">

 <ul type="circle">

 <li>

 <p>引数 : $where (検索に必要な WHERE 節)</p>

 </li>

 <li>

 <p>引数 : $join (検索に必要な JOIN 節)</p>

 </li>

 <li>

 <p>戻り値 : なし</p>

 </li>

 </ul>

 </div>

 </li>

 </ul>

 </div>

 <p>検索を実行する直前にシステムから呼び出されます．アイテムの検索を行なうために必要な条件式や JOIN 文を生成して返します．</p>

 <p><span class="application">XooNIps</span> は以下のような SQL で検索します．GetAdvancedSearchQuery で作成された文字列 $where と $join は，以下の SQL の下線の部分として使用さます．</p>

 <div class="blockquote">

 <blockquote class="blockquote">

 <pre class="programlisting">例: xnppaperの場合

select xoops_xoonips_item_basic.item_id
from xoops_xoonips_item_basic
left join xoops_xoonips_index_item_link on ...
left join xoops_xoonips_index on ...
left join xoops_xoonips_groups_users_link on ...
left join xoops_users on ...
left join xoops_xoonips_file on ...
left join xoops_xoonips_item_title on ...
left join xoops_xoonips_item_keyword on ...
left join xoops_xnppaper_item_detail on ...
<span class="underline">left join (テーブル名) on (条件)</span> ← $join
where
 xoops_xnppaper_item_detail.paper_id is not null and
 ( <span class="underline">xoops_xoonips_item_basic.title like '%foo%' and ...</span> ) ← $where
 and ...
group by xoops_xoonips_item_basic.item_id;</pre>

 </blockquote>

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

 <li>

 <p>xnpKeywordsToFulltextSql</p>

 </li>

 <li>

 <p>xnpGetBasicInformationAdvancedSearchQuery</p>

 </li>

 </ul>

 </div>

 </div>

 </div>

 <div xmlns="http://www.w3.org/1999/xhtml" class="navfooter">

 </div>

 </body>


