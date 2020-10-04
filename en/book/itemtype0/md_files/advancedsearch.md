# advancedsearch

## 第16章 詳細検索

 ![&#x8A73;&#x7D30;&#x691C;&#x7D22;&#x306E;&#x6D41;&#x308C;](https://github.com/XoopsDocs/xoonips-developerguide/tree/a6a58e91b3c2fbad05284b6a55d66570e12e94d6/en/book/assets/itemtype/search-flow.gif)

 **図 16.1. 詳細検索の流れ**  
 ![&#x753B;&#x9762;&#x9077;&#x79FB;&#x3068;&#x9001;&#x4FE1;&#x30D1;&#x30E9;&#x30E1;&#x30FC;&#x30BF;](https://github.com/XoopsDocs/xoonips-developerguide/tree/a6a58e91b3c2fbad05284b6a55d66570e12e94d6/en/book/assets/itemtype/search-trans.gif)

 **図 16.2. 画面遷移と送信パラメータ**  


## 1. 検索フォーム作成

アイテムタイプモジュールの以下の関数に詳細検索用クエリを作成する処理を定義してください．

* function &lt;モジュール名&gt; GetAdvancedSearchBlock\( &$search\_var \)
  * 引数 : $search\_var \(検索条件を代入するパラメータの名前の配列\)
  * 戻り値 : 検索フォームの HTML

アイテムタイプを検索するためのフォームを作成します．Basic Information と Detail Information の中から検索条件にするフィールドを入力するフォームを作成します．

Basic Information の条件入力フォーム生成は共通ライブラリに用意された関数を使用します．この関数は Basic Information の検索条件に指定可能なすべてのフィールドのフォームを返しますので，その中でアイテムタイプの検索条件として使いたいフィールドだけを抜き出して使用します．

Detail Information の検索条件入力フォームはアイテムタイプモジュールで自由に定義できます．

以下の関数も参照してください．

* xnpGetKeywordQuery
* xnpGetKeywordsQueries
* xnpGetBasicInformationAdvancedSearchBlock

### 1.1. $search\_var 引数について

フォームに入力された検索条件を代入するパラメータ名 \(&lt;input&gt; タグの name 属性\) を $search\_var 引数に追加します． アイテムタイプ 'Book' 型の著者の検索条件のパラメータ名が 'xnpbook\_author' だとすれば，$search\_var\[\] = 'xnpbook\_author'; と追加します．

パラメータ名が他のアイテムタイプが使用するものと重複するのを防ぐため，パラメータ名の先頭にはモジュール名をつけてください．例えば 'Book' 型の著者の場合はパラメータ名を 'xnpbook\_author' とします．タイトル，キーワードなどの Basic Information も，アイテムタイプごとに重複しないように注意してください．

## 2. 検索クエリ \(SQL\) 文作成

アイテムタイプモジュールの以下の関数に詳細検索フォーム作成処理を定義してください．

* function &lt;モジュール名&gt; GetAdvancedSearchQuery\( &$where, &$join \)
  * 引数 : $where \(検索に必要な WHERE 節\)
  * 引数 : $join \(検索に必要な JOIN 節\)
  * 戻り値 : なし

検索を実行する直前にシステムから呼び出されます．アイテムの検索を行なうために必要な条件式や JOIN 文を生成して返します．

XooNIps は以下のような SQL で検索します．GetAdvancedSearchQuery で作成された文字列 $where と $join は，以下の SQL の下線の部分として使用さます．

> ```text
> 例: xnppaperの場合
>
>
>
> select xoops_xoonips_item_basic.item_id
>
>
>
> from xoops_xoonips_item_basic
>
>
>
> left join xoops_xoonips_index_item_link on ...
>
>
>
> left join xoops_xoonips_index on ...
>
>
>
> left join xoops_xoonips_groups_users_link on ...
>
>
>
> left join xoops_users on ...
>
>
>
> left join xoops_xoonips_file on ...
>
>
>
> left join xoops_xoonips_item_title on ...
>
>
>
> left join xoops_xoonips_item_keyword on ...
>
>
>
> left join xoops_xnppaper_item_detail on ...
>
>
>
> left join (テーブル名) on (条件) ← $join
>
>
>
> where
>
>
>
>  xoops_xnppaper_item_detail.paper_id is not null and
>
>
>
>  ( xoops_xoonips_item_basic.title like '%foo%' and ... ) ← $where
>
>
>
>  and ...
>
>
>
> group by xoops_xoonips_item_basic.item_id;
> ```

以下の関数も参照してください．

* xnpGetKeywordQuery
* xnpGetKeywordsQueries
* xnpKeywordsToFulltextSql
* xnpGetBasicInformationAdvancedSearchQuery

