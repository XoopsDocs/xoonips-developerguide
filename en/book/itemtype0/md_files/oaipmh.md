# oaipmh

## 第21章 OAI-PMH

OAI-PMHハーベスタからの要求に対し，メタデータを生成します

## 1. OAI-PMH処理

アイテムタイプモジュールは以下のOAI-PMH要求に対応します．

### 1.1. 対応メタデータフォーマットの列挙

以下の関数を定義し，アイテムタイプモジュールがメタデータフォーマットの生成に対応しているか否かを返します．

* function &lt;モジュール名&gt;SupportMetadataFormat\( $metadataPrefix, $item\_id \)

  $item\_idで指定されたアイテムのメタ情報を，$metadataPrefixで指定されるフォーマットで生成できるかを返します．

  * 戻り値 : true\(生成可能\)
  * 戻り値 : false\(生成不可能\)

### 1.2. メタデータの生成

以下の関数を定義し，指定されたアイテムのメタデータを返します．

* function &lt;モジュール名&gt;GetMetadata\( $metadataPrefix, $item\_id \)

  $item\_idで指定されたアイテムのメタデータを，$metadataPrefixで指定されるフォーマットで生成して返します．&lt;metadata&gt;から&lt;/metadata&gt;までを生成て返します．

  * 戻り値 : メタデータテキスト\(&lt;metadata&gt;から&lt;/metadata&gt;まで\)
  * 戻り値 : false\(生成失敗\)

