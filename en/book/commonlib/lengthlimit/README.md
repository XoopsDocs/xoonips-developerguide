# lengthlimit {#lengthlimit}

| ![前のページ](../../assets/commonlib/prev.gif)  |   |  ![次のページ](../../assets/commonlib/next.gif) |
| --- | :-: | --- |

## 第12章 文字数制限 {#12}

## 1\. array xnpTrimString( string str, int length, string enc=null ) {#1-array-xnptrimstring-string-str-int-length-string-enc-null}

strの頭から，lengthバイト以下かつマルチバイト文字・数値文字参照の途中でないような文字列を切り出します．

### 1.1\. 入力 {#1-1}

*   str : 文字列

*   length :切り出すバイト数

*   enc : strのエンコード．nullなら自動判別する．

### 1.2\. 戻り値 {#1-2}

*   array( 切り出した文字列,　残りの文字列 )

## 2\. void xnpTrimColumn( array &amp;assoc, string table_without_prefix, array names=null, string enc=null ) {#2-void-xnptrimcolumn-array-assoc-string-table-without-prefix-array-names-null-string-enc-null}

複数の文字列から，DBに収まる部分だけを切り出します．

### 2.1\. 入力 {#2-1}

*   assoc : 連想配列 array( カラム名=&gt;文字列 ) ．

*   table_without_prefix :テーブル名(prefixを除く)

*   names : カラム名の配列．assoc中の処理すべき文字列を指定します．nullなら全て処理します．

*   enc : strのエンコード．nullなら自動判別する．

### 2.2\. 戻り値 {#2-2}

*   なし．関数実行後のassocは，array( カラム名=&gt;切り出した文字列 ) となります．

## 3\. void xnpConfirmHtml( array &amp;assoc, string table_without_prefix, array names=null, string enc=null ) {#3-void-xnpconfirmhtml-array-assoc-string-table-without-prefix-array-names-null-string-enc-null}

複数の文字列から，(DBに収まる部分，収まらない部分，確認画面表示用html，文字列のhtml) を生成します．

### 3.1\. 入力 {#3-1}

*   assoc : 連想配列 array( カラム名=&gt;array( &#039;value&#039;=&gt;文字列 ) ) ．

*   table_without_prefix : テーブル名(prefixを除く)

*   names : カラム名の配列．assoc中の処理すべき文字列を指定します．nullなら全て処理します．

*   enc : strのエンコード．nullなら自動判別する．

### 3.2\. 戻り値 {#3-2}

*   なし．切り出した結果はassocに書き込まれます．関数実行後のassocは， array( カラム名 =&gt; array( &#039;value&#039;=&gt;確認画面表示用html , &#039;within&#039;=&gt;収まる部分 , &#039;without&#039;=&gt;収まらない部分 , &#039;html_string&#039;=&gt;文字列のhtml ) ) となります．

## 4\. bool xnpHasWithout( array assoc ) {#4-bool-xnphaswithout-array-assoc}

xnpConfirmHtmlの結果を見て，DBに収まらない文字列があったかどうかを返します．

### 4.1\. 入力 {#4-1}

*   assoc : xnpConfirmHtmlに渡したassoc ．

### 4.2\. 戻り値 {#4-2}

*   DBに収まらない文字列があったならtrueを返します．

## 5\. array xnpGetColumnLengths( string table_without_prefix ) {#5-array-xnpgetcolumnlengths-string-table-without-prefix}

テーブルの各カラム(文字列型・バイナリ型のみ)のサイズを得ます．

### 5.1\. 入力 {#5-1}

*   table_without_prefix : テーブル名(prefixを除く) ．

### 5.2\. 戻り値 {#5-2}

*   連想配列　array( カラム名 =&gt; サイズ(bytes) )

## 6\. string xnpWithinWithoutHtml( string within, string without ) {#6-string-xnpwithinwithouthtml-string-within-string-without}

確認画面用の，一部が赤くなったHTMLを生成します．

### 6.1\. 入力 {#6-1}

*   within : 黒く表示すべき文字列．

*   without : 赤く表示すべき文字列．

### 6.2\. 戻り値 {#6-2}

*   within文字列の後に，赤いwithout文字列を結合したHTML

| ![前のページ](../../assets/commonlib/prev.gif)  |   |  ![次のページ](../../assets/commonlib/next.gif) |
| --- | --- | --- |
|   | ![ホーム](../../assets/commonlib/home.gif)  |   |

Last updated: 2010/04/15