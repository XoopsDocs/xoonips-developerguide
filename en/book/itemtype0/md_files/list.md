# list

## 第9章 アイテム一覧

複数のアイテムを一覧表示する画面に各アイテムの概要を表示します．アイテム一覧画面の一部の小領域が個々のアイテムに割り当てられます．アイテムタイプは割り当てられたその領域に表示する概要を作成します．

アイテムタイプモジュールの以下の関数にアイテム概要の HTML を生成する処理を定義してください．アイテム一覧表示を行なう際に，システムがこの関数をコールバックします．

* function &lt;モジュール名&gt;GetListBlock\( $item\_basic \)
  * 引数 : $item\_basic \(アイテムの Basic Information\)
  * 戻り値 : 概要の HTML

## 1. アイテム概要の生成

一覧表示に必要な HTML を作成します．引数 $item\_basic に Basic Information が設定されているので，タイトルなどの Basic Information を表示するにはそちらを参照してください．$item\_basic に設定されたアイテム ID を使って Detail Information を取得し，一覧表示に Detail Information を加えることも出来ます．

