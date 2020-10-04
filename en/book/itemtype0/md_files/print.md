# 第12章 アイテム詳細印刷用画面

アイテムの情報を印刷に適した形式に整形した HTML を作成します．

アイテムタイプモジュールの以下の関数に処理を定義してください．システムは印刷用画面が必要なときこの関数をコールバックします．

* function &lt;モジュール名&gt;GetPrinterFriendlyDetailBlock\( $item\_id \)
  * 引数 : アイテム ID
  * 戻り値 : 印刷用の HTML

以下の項目も参照してください．

* xnpGetBasicInformationPrinterFriendlyBlock
* xnpGetPreviewPrinterFriendlyBlock
* xnpGetAttachmentPrinterFriendlyBlock
* xnpGetTextFilePrinterFriendlyBlock
* xnpGetRightsPrinterFriendlyBlock
* xnpGetIndexPrinterFriendlyBlock

