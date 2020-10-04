# 第9章 メタ情報

### 1. array xnpGetBasicInformationArray\( int item\_id \)

アイテムの Basic Information を返します．

{$modulename}GetMetaInformationからの呼び出しを前提とした関数です．

#### 1.1. 戻り値

引数で指定された item\_id に対応するアイテム情報を連想配列で返します．

連想配列の構造は以下の通りです．

> ```text
> array( key1 => value1, key2 => value2, … )
> ```

キーは先頭から以下の順に並びます．

* 'item\_type' : アイテムタイプの表示名
* 'title' : タイトル文字列
* 'contributor' : アイテム作成者の名前
* 'keywords' : フリーキーワード
* 'description' : コメント
* 'doi' : DOI文字列
* 'last\_update\_date' : 最終更新日時の文字列
* 'creation\_date' : アイテム作成日時の文字列
* 'publication\_year' : アイテム内容に関連する西暦
* 'publication\_month' : アイテム内容に関連する月\(1-12\)
* 'publication\_mday' : アイテム内容に関連する日\(1-31\)
* 'lang' : 言語

### 2. bool xnpBasicInformation2XML\( resource fhdl, array item, bool is\_absolute, int base\_index\_id=false \)

アイテムの Basic Information を，外部アプリと交換するためのXMLに変換してファイルに出力します．

#### 2.1. 入力

* fhdl : 出力先のファイルハンドル
* item : 変換したいアイテムのBasic Informationの連想配列
* is\_absolute, base\_index\_id : XMLのインデックスタグのCDATA部の指定．
  * is\_absoluteがtrueなら，base\_index\_idは無視される．インデックスタグのCDATA部は，インデックスを絶対パスで表した文字列になる．
  * is\_absoluteがfalseかつbase\_index\_idがfalseなら，インデックスタグのCDATA部は空文字列になる．
  * is\_absoluteがfalseかつbase\_index\_idがfalseでないなら，インデックスタグのCDATA部は，base\_index\_idの子孫のインデックスのみをbase\_index\_idからの相対パスで表した文字列になる．

連想配列itemの構造は以下の通りです．

> ```text
> array( key1 => value1, key2 => value2, … )
> ```

* 'item\_id' : アイテムID
* 'item\_type' : アイテムタイプの表示名
* 'title' : タイトル文字列
* 'contributor' : アイテム作成者の名前
* 'keywords' : フリーキーワード
* 'description' : コメント
* 'doi' : DOI文字列
* 'last\_update\_date' : 最終更新日時の文字列
* 'creation\_date' : アイテム作成日時の文字列
* 'publication\_year' : アイテム内容に関連する西暦
* 'publication\_month' : アイテム内容に関連する月\(1-12\)
* 'publication\_mday' : アイテム内容に関連する日\(1-31\)
* 'lang' : 言語

#### 2.2. 戻り値

* true : 成功
* false : 失敗

