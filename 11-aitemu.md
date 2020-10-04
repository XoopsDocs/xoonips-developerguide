---
description: アイテムの詳しい情報を表示します．処理の流れは図 6のとおりです．
---

# 第11章 アイテム詳細画面



![&#x30A2;&#x30A4;&#x30C6;&#x30E0;&#x8A73;&#x7D30;&#x753B;&#x9762;&#x8868;&#x793A;&#x306E;&#x6D41;&#x308C;](https://xoonips.osdn.jp/manuals/itemtype-340/images/detail-flow.gif)

**図 11.1. アイテム詳細画面表示の流れ**  


アイテムタイプモジュールの以下の関数に詳細画面作成処理を定義してください．システムは詳細画面が必要なときこの関数をコールバックします．

* function &lt;モジュール名&gt;GetDetailBlock\( $item\_id \)
  * 引数 : アイテムID
  * 戻り値 : 詳細画面の HTML

ユーザがアイテムを編集する権限を持つなら，詳細画面のHTMLに以下のようなフォームを含めて下さい．

> ```text
> <form id='xoonips_edit_form'>
>   <input type='hidden' ... > 
> </form>
> ```

このフォームは詳細画面の「公開インデックスに登録」ボタンを押したときに確認画面に送信されます． アイテム登録画面・編集画面が送信するのと同じデータを送信するよう，適切なinputタグを入れる必要があります．

もし詳細画面の生成で関数xnpGetAttachmentDetailBlockを使用するなら，引数download\_file\_idをxnpGetDownloadConfirmationBlockに渡し，その結果をHTMLに含めてください．

### 1. Basic Information のフォーム生成

共通ライブラリに Basic Information の詳細画面用フォームを作成する関数があります．その関数を呼び出して，Basic Information のフォームを取得します．Basic Information のフィールド毎のフォームが得られるので，その中から必要なフィールドを取り出して組合せ，Basic Information の詳細画面を作成します．

以下の項目も参照してください．

* xnpGetBasicInformationDetailBlock

### 2. Detail Informationのフォーム生成

Detail Information の詳細画面の作成はアイテムタイプで自由に定義できます．添付ファイル，インデックス，画像などは共有ライブラリに関数が用意されているのでそれを利用できます．

最後に，Basic Information と Detail Information のフォームをまとめて戻り値とします．

以下の項目も参照してください．

* xnpGetPreviewDetailBlock
* xnpGetAttachmentDetailBlock
* xnpGetTextFileDetailBlock
* xnpGetRightsDetailBlock
* xnpGetIndexDetailBlock

