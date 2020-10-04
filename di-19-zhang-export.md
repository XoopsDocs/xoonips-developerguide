---
description: アイテム，インデックスをXMLで表現してExportします．Exportに対応したいアイテムタイプモジュールには，かならず以下の関数を定義してください．
---

# 第19章 Export

### 1. ライセンスの合意

Exportするにあたりライセンスの合意が必要か否か，およびそのライセンス文をXooNIpsに返す必要があります．アイテムタイプに以下の関数を定義してください．

* function &lt;モジュール名&gt;GetLicenseRequired \( $item\_id \)
  * 引数 : item\_id \(アイテム ID\)
  * 戻り値 : 合意が必要ならtrue
* function &lt;モジュール名&gt;GetLicenseStatement \( $item\_id \)
  * 引数 : item\_id \(アイテム ID\)
  * 戻り値 : array\( ライセンス文, use\_cc \)．Creative Commonsのライセンスを使用する場合は，ライセンス文をhtmlにしてuse\_ccを非falseにする．ライセンスが無い場合は戻り値をNULLにする．

### 2. Detail Information の Export

アイテムタイプのDetail InformationをXMLで表現した文字列をファイルに出力します．&lt;DETAIL&gt;で始まり，&lt;/DETAIL&gt;で終わるタグの中に，アイテムタイプ独自のタグを定義できます．

* function &lt;モジュール名&gt;ExportItem \( $export\_path, $fhdl, $item\_id, $attachment \)
  * 引数 : export\_path \(添付ファイルをエクスポートする時，この引数をxnpExportFileの第1引数に渡してください\)
  * 引数 : fhdl \(出力先ファイルハンドル\)
  * 引数 : item\_id \(アイテム ID\)
  * 引数 : attachment \(添付ファイルをExportするならtrue．しないならfalse．\)
  * 戻り値 : 成功なら true ．失敗なら false ．

以下の関数も参照してください．

* xnpExportFile

