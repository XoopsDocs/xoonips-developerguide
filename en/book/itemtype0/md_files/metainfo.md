# metainfo

## 第14章 メタ情報

システムはユーザからの添付ファイルのダウンロード要求に対して，添付ファイルが属するアイテムの情報 \(メタ情報\) と添付ファイルを含んだ ZIP 書庫ファイルを出力します．

このときシステムはアイテムタイプモジュールに対してメタ情報を要求します．

アイテムタイプモジュールの以下の関数にメタ情報作成処理を定義してください．

* function &lt;モジュール名&gt;GetMetaInformation \( $item\_id \)
  * 引数 : アイテム ID
  * 戻り値 : メタ情報 \(Basic Information と Detail Information の両方を含む\)の連想配列
    * 連想配列の構造は以下の通りです．

      > ```text
      > array( key1 => value1, key2 => value2, ... )
      > ```

    * この情報は以下の形式で ZIP 書庫ファイルに添付されます．

      > ```text
      > key1: value1
      >
      > key2: value2
      >
      > ...
      > ```

## 1. BasicInformation のメタ情報

共通ライブラリにメタ情報生成用に Basic Information を取得する関数が定義されているのでそれを利用します．

以下の項目も参照してください．

* xnpGetBasicInformationArray

## 2. Detail Information のメタ情報

Detail Information のメタ情報はアイテムタイプモジュールが自由に定義できます．

