# 第10章 アイテム一覧印刷用画面

アイテムの情報を印刷に適した形式に整形した HTML を作成します．

アイテムタイプモジュールの以下の関数に処理を定義してください．システムは一覧印刷用画面が必要なときこの関数をコールバックします．

* function &lt;モジュール名&gt;GetPrinterFriendlyListBlock\( $item\_basic \)
  * 引数 : $item\_basic \(アイテムの Basic Information\)
  * 戻り値 : 印刷用の HTML

