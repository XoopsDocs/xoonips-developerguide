# metainfo {#metainfo}

| ![前のページ](../../assets/commonlib/prev.gif)  |   |  ![次のページ](../../assets/commonlib/next.gif) |
| --- | :-: | --- |

## 第9章 メタ情報 {#9}

## 1\. array xnpGetBasicInformationArray( int item_id ) {#1-array-xnpgetbasicinformationarray-int-item-id}

アイテムの Basic Information を返します．

{$modulename}GetMetaInformationからの呼び出しを前提とした関数です．

### 1.1\. 戻り値 {#1-1}

引数で指定された item_id に対応するアイテム情報を連想配列で返します．

連想配列の構造は以下の通りです．

> <pre class="programlisting">array( key1 =&gt; value1, key2 =&gt; value2, … )</pre>

キーは先頭から以下の順に並びます．

*   &#039;item_type&#039; : アイテムタイプの表示名

*   &#039;title&#039; : タイトル文字列

*   &#039;contributor&#039; : アイテム作成者の名前

*   &#039;keywords&#039; : フリーキーワード

*   &#039;description&#039; : コメント

*   &#039;doi&#039; : DOI文字列

*   &#039;last_update_date&#039; : 最終更新日時の文字列

*   &#039;creation_date&#039; : アイテム作成日時の文字列

*   &#039;publication_year&#039; : アイテム内容に関連する西暦

*   &#039;publication_month&#039; : アイテム内容に関連する月(1-12)

*   &#039;publication_mday&#039; : アイテム内容に関連する日(1-31)

*   &#039;lang&#039; : 言語

## 2\. bool xnpBasicInformation2XML( resource fhdl, array item, bool is_absolute, int base_index_id=false ) {#2-bool-xnpbasicinformation2xml-resource-fhdl-array-item-bool-is-absolute-int-base-index-id-false}

アイテムの Basic Information を，外部アプリと交換するためのXMLに変換してファイルに出力します．

### 2.1\. 入力 {#2-1}

*   fhdl : 出力先のファイルハンドル

*   item : 変換したいアイテムのBasic Informationの連想配列

*   is_absolute, base_index_id : XMLのインデックスタグのCDATA部の指定．

    *   is_absoluteがtrueなら，base_index_idは無視される．インデックスタグのCDATA部は，インデックスを絶対パスで表した文字列になる．

    *   is_absoluteがfalseかつbase_index_idがfalseなら，インデックスタグのCDATA部は空文字列になる．

    *   is_absoluteがfalseかつbase_index_idがfalseでないなら，インデックスタグのCDATA部は，base_index_idの子孫のインデックスのみをbase_index_idからの相対パスで表した文字列になる．

連想配列itemの構造は以下の通りです．

> <pre class="programlisting">array( key1 =&gt; value1, key2 =&gt; value2, … )</pre>

*   &#039;item_id&#039; : アイテムID

*   &#039;item_type&#039; : アイテムタイプの表示名

*   &#039;title&#039; : タイトル文字列

*   &#039;contributor&#039; : アイテム作成者の名前

*   &#039;keywords&#039; : フリーキーワード

*   &#039;description&#039; : コメント

*   &#039;doi&#039; : DOI文字列

*   &#039;last_update_date&#039; : 最終更新日時の文字列

*   &#039;creation_date&#039; : アイテム作成日時の文字列

*   &#039;publication_year&#039; : アイテム内容に関連する西暦

*   &#039;publication_month&#039; : アイテム内容に関連する月(1-12)

*   &#039;publication_mday&#039; : アイテム内容に関連する日(1-31)

*   &#039;lang&#039; : 言語

### 2.2\. 戻り値 {#2-2}

*   true : 成功

*   false : 失敗

| ![前のページ](../../assets/commonlib/prev.gif)  |   |  ![次のページ](../../assets/commonlib/next.gif) |
| --- | --- | --- |
|   | ![ホーム](../../assets/commonlib/home.gif)  |   |

Last updated: 2010/04/15