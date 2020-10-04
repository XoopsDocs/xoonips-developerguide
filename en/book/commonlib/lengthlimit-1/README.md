# lengthlimit

| ![&#x524D;&#x306E;&#x30DA;&#x30FC;&#x30B8;](https://github.com/XoopsDocs/xoonips-developerguide/tree/a6a58e91b3c2fbad05284b6a55d66570e12e94d6/en/book/assets/commonlib/prev.gif) |  | ![&#x6B21;&#x306E;&#x30DA;&#x30FC;&#x30B8;](https://github.com/XoopsDocs/xoonips-developerguide/tree/a6a58e91b3c2fbad05284b6a55d66570e12e94d6/en/book/assets/commonlib/next.gif) |
| :--- | :---: | :--- |


## 第12章 文字数制限 <a id="12"></a>

## 1. array xnpTrimString\( string str, int length, string enc=null \) <a id="1-array-xnptrimstring-string-str-int-length-string-enc-null"></a>

strの頭から，lengthバイト以下かつマルチバイト文字・数値文字参照の途中でないような文字列を切り出します．

### 1.1. 入力 <a id="1-1"></a>

* str : 文字列
* length :切り出すバイト数
* enc : strのエンコード．nullなら自動判別する．

### 1.2. 戻り値 <a id="1-2"></a>

* array\( 切り出した文字列,　残りの文字列 \)

## 2. void xnpTrimColumn\( array &assoc, string table\_without\_prefix, array names=null, string enc=null \) <a id="2-void-xnptrimcolumn-array-assoc-string-table-without-prefix-array-names-null-string-enc-null"></a>

複数の文字列から，DBに収まる部分だけを切り出します．

### 2.1. 入力 <a id="2-1"></a>

* assoc : 連想配列 array\( カラム名=&gt;文字列 \) ．
* table\_without\_prefix :テーブル名\(prefixを除く\)
* names : カラム名の配列．assoc中の処理すべき文字列を指定します．nullなら全て処理します．
* enc : strのエンコード．nullなら自動判別する．

### 2.2. 戻り値 <a id="2-2"></a>

* なし．関数実行後のassocは，array\( カラム名=&gt;切り出した文字列 \) となります．

## 3. void xnpConfirmHtml\( array &assoc, string table\_without\_prefix, array names=null, string enc=null \) <a id="3-void-xnpconfirmhtml-array-assoc-string-table-without-prefix-array-names-null-string-enc-null"></a>

複数の文字列から，\(DBに収まる部分，収まらない部分，確認画面表示用html，文字列のhtml\) を生成します．

### 3.1. 入力 <a id="3-1"></a>

* assoc : 連想配列 array\( カラム名=&gt;array\( 'value'=&gt;文字列 \) \) ．
* table\_without\_prefix : テーブル名\(prefixを除く\)
* names : カラム名の配列．assoc中の処理すべき文字列を指定します．nullなら全て処理します．
* enc : strのエンコード．nullなら自動判別する．

### 3.2. 戻り値 <a id="3-2"></a>

* なし．切り出した結果はassocに書き込まれます．関数実行後のassocは， array\( カラム名 =&gt; array\( 'value'=&gt;確認画面表示用html , 'within'=&gt;収まる部分 , 'without'=&gt;収まらない部分 , 'html\_string'=&gt;文字列のhtml \) \) となります．

## 4. bool xnpHasWithout\( array assoc \) <a id="4-bool-xnphaswithout-array-assoc"></a>

xnpConfirmHtmlの結果を見て，DBに収まらない文字列があったかどうかを返します．

### 4.1. 入力 <a id="4-1"></a>

* assoc : xnpConfirmHtmlに渡したassoc ．

### 4.2. 戻り値 <a id="4-2"></a>

* DBに収まらない文字列があったならtrueを返します．

## 5. array xnpGetColumnLengths\( string table\_without\_prefix \) <a id="5-array-xnpgetcolumnlengths-string-table-without-prefix"></a>

テーブルの各カラム\(文字列型・バイナリ型のみ\)のサイズを得ます．

### 5.1. 入力 <a id="5-1"></a>

* table\_without\_prefix : テーブル名\(prefixを除く\) ．

### 5.2. 戻り値 <a id="5-2"></a>

* 連想配列　array\( カラム名 =&gt; サイズ\(bytes\) \)

## 6. string xnpWithinWithoutHtml\( string within, string without \) <a id="6-string-xnpwithinwithouthtml-string-within-string-without"></a>

確認画面用の，一部が赤くなったHTMLを生成します．

### 6.1. 入力 <a id="6-1"></a>

* within : 黒く表示すべき文字列．
* without : 赤く表示すべき文字列．

### 6.2. 戻り値 <a id="6-2"></a>

* within文字列の後に，赤いwithout文字列を結合したHTML

| ![&#x524D;&#x306E;&#x30DA;&#x30FC;&#x30B8;](https://github.com/XoopsDocs/xoonips-developerguide/tree/a6a58e91b3c2fbad05284b6a55d66570e12e94d6/en/book/assets/commonlib/prev.gif) |  | ![&#x6B21;&#x306E;&#x30DA;&#x30FC;&#x30B8;](https://github.com/XoopsDocs/xoonips-developerguide/tree/a6a58e91b3c2fbad05284b6a55d66570e12e94d6/en/book/assets/commonlib/next.gif) |
| :--- | :--- | :--- |
|  | ![&#x30DB;&#x30FC;&#x30E0;](https://github.com/XoopsDocs/xoonips-developerguide/tree/a6a58e91b3c2fbad05284b6a55d66570e12e94d6/en/book/assets/commonlib/home.gif) |  |

Last updated: 2010/04/15

