<div id="page">

<div xmlns="http://www.w3.org/1999/xhtml" class="navheader">

<table width="100%" summary="Navigation header">

<tbody>

<tr>

<td width="20%" align="left">[![前のページ](images\prev.gif)](quicksearch.html) </td>

<th width="60%" align="center"> </th>

<td width="20%" align="right"> [![次のページ](images\next.gif)](capacity.html)</td>

</tr>

</tbody>

</table>

* * *

</div>

<div xmlns="http://www.w3.org/1999/xhtml" class="chapter" lang="ja" id="advancedsearch" xml:lang="ja">

<div xmlns="" class="titlepage">

<div>

<div>

## <a id="advancedsearch"></a>第16章 詳細検索

</div>

</div>

</div>

<div class="figure"><a id="fig.advancedsearch.workflow"></a>

<div class="figure-contents">

<div class="mediaobject">![詳細検索の流れ](images\search-flow.gif)</div>
<img src="../../assets/itemtype/search-flow.gif" alt="詳細検索の流れ" />



</div>

**図 16.1\. 詳細検索の流れ**

</div>

<div class="figure"><a id="fig.advancedsearch.view-parameter"></a>

<div class="figure-contents">

<div class="mediaobject">![画面遷移と送信パラメータ](images\search-trans.gif)</div>
<img src="../../assets/itemtype/search-trans.gif" alt="画面遷移と送信パラメータ" />



</div>

**図 16.2\. 画面遷移と送信パラメータ**

</div>

<div class="section" lang="ja" xml:lang="ja">

<div xmlns="" class="titlepage">

<div>

<div>

## <a id="advancedsearch.form"></a>1\. 検索フォーム作成

</div>

</div>

</div>

アイテムタイプモジュールの以下の関数に詳細検索用クエリを作成する処理を定義してください．

<div class="itemizedlist">

*   function <モジュール名> GetAdvancedSearchBlock( &$search_var )

    <div class="itemizedlist">

    *   引数 : $search_var (検索条件を代入するパラメータの名前の配列)

    *   戻り値 : 検索フォームの HTML

    </div>

</div>

アイテムタイプを検索するためのフォームを作成します．Basic Information と Detail Information の中から検索条件にするフィールドを入力するフォームを作成します．

Basic Information の条件入力フォーム生成は共通ライブラリに用意された関数を使用します．この関数は Basic Information の検索条件に指定可能なすべてのフィールドのフォームを返しますので，その中でアイテムタイプの検索条件として使いたいフィールドだけを抜き出して使用します．

Detail Information の検索条件入力フォームはアイテムタイプモジュールで自由に定義できます．

以下の関数も参照してください．

<div class="itemizedlist">

*   xnpGetKeywordQuery

*   xnpGetKeywordsQueries

*   xnpGetBasicInformationAdvancedSearchBlock

</div>

<div class="section" lang="ja" xml:lang="ja">

<div xmlns="" class="titlepage">

<div>

<div>

### <a id="advancedsearch.form.arguments"></a>1.1\. $search_var 引数について

</div>

</div>

</div>

フォームに入力された検索条件を代入するパラメータ名 (<input> タグの name 属性) を $search_var 引数に追加します． アイテムタイプ 'Book' 型の著者の検索条件のパラメータ名が 'xnpbook_author' だとすれば，$search_var[] = 'xnpbook_author'; と追加します．

パラメータ名が他のアイテムタイプが使用するものと重複するのを防ぐため，パラメータ名の先頭にはモジュール名をつけてください．例えば 'Book' 型の著者の場合はパラメータ名を 'xnpbook_author' とします．タイトル，キーワードなどの Basic Information も，アイテムタイプごとに重複しないように注意してください．

</div>

</div>

<div class="section" lang="ja" xml:lang="ja">

<div xmlns="" class="titlepage">

<div>

<div>

## <a id="advancedsearch.query"></a>2\. 検索クエリ (SQL) 文作成

</div>

</div>

</div>

アイテムタイプモジュールの以下の関数に詳細検索フォーム作成処理を定義してください．

<div class="itemizedlist">

*   function <モジュール名> GetAdvancedSearchQuery( &$where, &$join )

    <div class="itemizedlist">

    *   引数 : $where (検索に必要な WHERE 節)

    *   引数 : $join (検索に必要な JOIN 節)

    *   戻り値 : なし

    </div>

</div>

検索を実行する直前にシステムから呼び出されます．アイテムの検索を行なうために必要な条件式や JOIN 文を生成して返します．

<span class="application">XooNIps</span> は以下のような SQL で検索します．GetAdvancedSearchQuery で作成された文字列 $where と $join は，以下の SQL の下線の部分として使用さます．

<div class="blockquote">

> <pre class="programlisting">例: xnppaperの場合
> 
> select xoops_xoonips_item_basic.item_id 
> from xoops_xoonips_item_basic
> left join xoops_xoonips_index_item_link on ...
> left join xoops_xoonips_index  on ...
> left join xoops_xoonips_groups_users_link on ...
> left join xoops_users on ...
> left join xoops_xoonips_file on ...
> left join xoops_xoonips_item_title on ...
> left join xoops_xoonips_item_keyword on ...
> left join xoops_xnppaper_item_detail on ...
> <span class="underline">left join (テーブル名) on (条件)</span> ← $join
> where
>   xoops_xnppaper_item_detail.paper_id is not null and
>     ( <span class="underline">xoops_xoonips_item_basic.title like '%foo%' and ...</span> ) ← $where
>   and ...
> group by xoops_xoonips_item_basic.item_id;</pre>

</div>

以下の関数も参照してください．

<div class="itemizedlist">

*   xnpGetKeywordQuery

*   xnpGetKeywordsQueries

*   xnpKeywordsToFulltextSql

*   xnpGetBasicInformationAdvancedSearchQuery

</div>

</div>

</div>

<div xmlns="http://www.w3.org/1999/xhtml" class="navfooter">

* * *

<table width="100%" summary="Navigation footer">

<tbody>

<tr>

<td width="40%" align="left">[![前のページ](images\prev.gif)](quicksearch.html) </td>

<td width="20%" align="center"> </td>

<td width="40%" align="right"> [![次のページ](images\next.gif)](capacity.html)</td>

</tr>

<tr>

<td width="40%" align="left" valign="top"> </td>

<td width="20%" align="center">[![ホーム](images\home.gif)](index.html) </td>

<td width="40%" align="right" valign="top"> </td>

</tr>

</tbody>

</table>

</div>

<div class="lastupdated">Last updated: 2010/04/15</div>

</div>