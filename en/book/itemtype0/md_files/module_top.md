# 第18章 XooNIpsモジュールのトップ画面

XooNIpsモジュールのトップ画面の一部の小領域が個々のアイテムタイプに割り当てられます． アイテムタイプは割り当てられたその領域に表示するブロックを作成します．

アイテムタイプモジュールの以下の関数にこの処理を定義してください．システムがこの関数をコールバックします．

* function &lt;モジュール名&gt;GetTopBlock\( $itemtype \)

  * 引数 : $itemtype \(以下のキーを含む連想配列． item\_type\_id, mid, name, displayname, viewphp\)
  * 戻り値 : アイテムタイプの概要を表す HTML

  XooNIpsモジュールのトップ画面に表示すべき HTML を作成して返してください．

以下の関数も参照してください．

* xnpGetTopBlock

