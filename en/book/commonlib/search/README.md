# search

| ![&#x524D;&#x306E;&#x30DA;&#x30FC;&#x30B8;](https://github.com/XoopsDocs/xoonips-developerguide/tree/a6a58e91b3c2fbad05284b6a55d66570e12e94d6/en/book/assets/commonlib/prev.gif) |  | ![&#x6B21;&#x306E;&#x30DA;&#x30FC;&#x30B8;](https://github.com/XoopsDocs/xoonips-developerguide/tree/a6a58e91b3c2fbad05284b6a55d66570e12e94d6/en/book/assets/commonlib/next.gif) |
| :--- | :---: | :--- |


## 第10章 検索 <a id="10"></a>

## 1. array xnpGetBasicInformationAdvancedSearchBlock\( string modulename, array &search\_var \) <a id="1-array-xnpgetbasicinformationadvancedsearchblock-string-modulename-array-search-var"></a>

AdvancedSearch 画面用の HTML を生成する．

### 1.1. 画面 <a id="1-1"></a>

> ![](https://github.com/XoopsDocs/xoonips-developerguide/tree/a6a58e91b3c2fbad05284b6a55d66570e12e94d6/en/book/assets/commonlib/xnpGetBasicInformationAdvancedSearchBlock.gif)

### 1.2. 戻り値 <a id="1-2"></a>

以下の構造の連想配列を返す．

> ```text
> array(
>     "(カラム名1)" => array( 
>         'name'=>"(カラム名HTML1)", 'value'=>"(カラム値HTML1)" ),
>     "(カラム名2)" => array(
>         'name'=>"(カラム名HTML2)", 'value'=>"(カラム値HTML2)" ),
>     (以下同様)
> );
> ```

ここで \(カラム名n\) は，'title', 'keywords', 'description', 'doi', 'publication\_date', 'publication\_year', 'publication\_month', 'publication\_mday' のいずれかである．

### 1.3. 送信データ <a id="1-3"></a>

* $\_POST\['\(モジュール名\)\_title'\]
* $\_POST\['\(モジュール名\)\_keywords'\]
* $\_POST\['\(モジュール名\)\_description'\]
* $\_POST\['\(モジュール名\)\_doi'\]
* $\_POST\['\(モジュール名\)\_publication\_date\_from'\]
* $\_POST\['\(モジュール名\)\_publication\_date\_fromYear'\]
* $\_POST\['\(モジュール名\)\_publication\_date\_fromMonth'\]
* $\_POST\['\(モジュール名\)\_publication\_date\_fromDay'\]
* $\_POST\['\(モジュール名\)\_publication\_date\_to'\]
* $\_POST\['\(モジュール名\)\_publication\_date\_toYear'\]
* $\_POST\['\(モジュール名\)\_publication\_date\_toMonth'\]
* $\_POST\['\(モジュール名\)\_publication\_date\_toDay'\]

※ この関数は，以上全ての $\_POST\[\] のキーを配列 $search\_var に追加します．

## 2. string xnpGetBasicInformationAdvancedSearchQuery\( string moduleName \) <a id="2-string-xnpgetbasicinformationadvancedsearchquery-string-modulename"></a>

モジュール名と $\_POST 変数から，Basic Information を検索するような SQL の条件式を作って返す．

条件の入力が無い場合は，空文字列を返す．

## 3. string xnpGetKeywordQuery \( string dbVarName, string postVarName \) <a id="3-string-xnpgetkeywordquery-string-dbvarname-string-postvarname"></a>

DB のカラム名と Keyword から SQL の条件式を作って返す．

Keyword として，$\_POST\[$postVarName\] を使用する．

「DBのカラムが Keyword 内の全ての単語を含む」を表すような条件式を返す．

検索条件が入力されていない場合は空文字列を返す．

> ```text
> 例:
>
> $_POST[$postVarName] = 'foo "bar's fobar"'
> $dbVarName = 'xoops_xnpdummy_item_detail.title'
>
> とすると，戻り値は
>
> "xoops_xnpdummy_item_detail.title like '%foo%' AND 
>  xoops_xnpdummy_item_detail.title like '%bar\'s fobar%'"
>
> となる．
> ```

### 3.1. 入力 <a id="3-1"></a>

* dbVarName : DB のテーブル名.カラム名
* postVarName : POST された Keyword 変数名

### 3.2. 戻り値 <a id="3-2"></a>

SQL の条件式

## 4. array xnpGetKeywordsQueries\( array dbVarNames, array keywords \) <a id="4-array-xnpgetkeywordsqueries-array-dbvarnames-array-keywords"></a>

DB のカラム名と Keyword から SQL の条件式の配列を作って返す．

戻り値の配列の \[N\] は，「dbVarNames の内の少なくとも 1つのカラムが Keywords\[N\] の文字列を含む」を意味するような条件式となる．

> ```text
> 例:
>
> $keywords = array('keyword1', 'keyword2' )
> $dbVarNames = array( 'table1.column1', 'table2.column2' )
>
> とすると，戻り値は
>
> array(
>   'table1.column1 like '%keyword1%' or table2.column2 like '%keyword1%',
>   'table1.column1 like '%keyword2%' or table2.column2 like '%keyword2%',
> )
>
> となる．
> ```

### 4.1. 入力 <a id="4-1"></a>

* dbVarNames : DB のテーブル名.カラム名 の配列
* keywords : Keywordの配列

### 4.2. 戻り値 <a id="4-2"></a>

SQL の条件式の配列

## 5. array xnpKeywordsToFulltextSql\( keywords \) <a id="5-array-xnpkeywordstofulltextsql-keywords"></a>

keywordから、ファイル内検索用SQLの一部を作成する．

この関数は array\(expression, errorMessage\) を返す． この expression を利用したSQL式

```text
match ( xoops_xoonips_file.search_text ) against ( '$expression' in boolean mode ) 
```

は、「xoops\_xoonips\_fileテーブルのsearch\_textカラム が、 keyword で指定された文字列を含む」という意味になる．

### 5.1. 入力 <a id="5-1"></a>

* keyword : 入力キーワード．論理式\(括弧, AND, OR\)を使った検索が使用可能．""で囲ってフレーズ検索をすることも可能．

### 5.2. 戻り値 <a id="5-2"></a>

array\( expression, errorMessage \)

* expression : SQL式の一部． " select .... match \( ... \) against \( $expression in boolean mode \)" といった形で使用可能
* errorMessage : エラーメッセージ．成功ならerrorMessage==false

| ![&#x524D;&#x306E;&#x30DA;&#x30FC;&#x30B8;](https://github.com/XoopsDocs/xoonips-developerguide/tree/a6a58e91b3c2fbad05284b6a55d66570e12e94d6/en/book/assets/commonlib/prev.gif) |  | ![&#x6B21;&#x306E;&#x30DA;&#x30FC;&#x30B8;](https://github.com/XoopsDocs/xoonips-developerguide/tree/a6a58e91b3c2fbad05284b6a55d66570e12e94d6/en/book/assets/commonlib/next.gif) |
| :--- | :--- | :--- |
|  | ![&#x30DB;&#x30FC;&#x30E0;](https://github.com/XoopsDocs/xoonips-developerguide/tree/a6a58e91b3c2fbad05284b6a55d66570e12e94d6/en/book/assets/commonlib/home.gif) |  |

Last updated: 2010/04/15

