# 第15章 簡易検索

アイテムタイプモジュールの以下の関数に簡易検索用クエリを作成する処理を定義してください．

* function &lt;モジュール名&gt;GetDetailInformationQuickSearchQuery\( &$wheres, &$join, $keywords \)
  * 引数 : $wheres \(SQL の WHERE 節に使用する式の配列\)
  * 引数 : $join \(SQL の JOIN 節に使用する式\)
  * 引数 : $keywords \(検索語句の配列\)
  * 戻り値 : なし

$join の意味は GetAdvancedSearchQuery と同様です．[章 16. 詳細検索](https://github.com/XoopsDocs/xoonips-developerguide/tree/a6a58e91b3c2fbad05284b6a55d66570e12e94d6/en/book/itemtype0/md_files/advancedsearch.html)を参照してください．

$wheres には，以下のような配列を書く必要があります．

* $wheres の要素数は $keywords の要素数と同じ
* $wheres\[n\] は，「Detail Information が $keywords\[n\] を含む」 を表す SQL 式

但し，Detail Information がどのキーワードも含まないことが前もってわかっている場合は，$wheres に何も書かなくても問題ありません．

その他の注意点は以下のとおりです．

* xoops\_\(モジュール名\)\_item\_detail はデフォルトで JOIN されるので $joinに書く必要は無い．他に JOIN すべきテーブルが無い場合は，$join には何も書かなくて良い．
* SQL 式でのカラムの指定は，必ずテーブル名を含む形で指定すること．
  * 例: 'pubmed\_id' → $xoopsDB-&gt;prefix\('xnppaper\_item\_detail'\) . '.pubmed\_id'
* $wheres の生成には，xnpGetKeywordsQueries を使用できる．

以下の関数も参照してください．

* xnpGetKeywordQuery
* xnpGetKeywordsQueries

