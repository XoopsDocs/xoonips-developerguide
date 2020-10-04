# basicinfo

| ![&#x524D;&#x306E;&#x30DA;&#x30FC;&#x30B8;](https://github.com/XoopsDocs/xoonips-developerguide/tree/a6a58e91b3c2fbad05284b6a55d66570e12e94d6/en/book/assets/commonlib/prev.gif) |  | ![&#x6B21;&#x306E;&#x30DA;&#x30FC;&#x30B8;](https://github.com/XoopsDocs/xoonips-developerguide/tree/a6a58e91b3c2fbad05284b6a55d66570e12e94d6/en/book/assets/commonlib/next.gif) |
| :--- | :---: | :--- |


## 第3章 Basic Information <a id="3-basic-information"></a>

## 1. Basic Informationのデータ構造 <a id="1-basic-information"></a>

アイテムの Basic Information のフォームを生成します．戻り値の構造は以下の通りです．フォームの一部を構成する HTML が格納されます．

```text
array $basic;
$basic['title']             タイトル
$basic['contributor']       アイテム作成者名
$basic['keywords']          キーワード
$basic['description']       コメント
$basic['doi']               DOI
$basic['last_update_date']  最終更新日
$basic['creation_date']     アイテム作成日
$basic['item_type']         アイテムタイプ名
$basic['change_logs']       これまでの変更履歴
$basic['change_log']        変更内容(変更履歴に追加される)
$basic['publication_date']  年月日 (※)
$basic['publication_year']  年 (※)
$basic['publication_month'] 月 (※)
$basic['publication_mday']  日 (※)
$basic['uid']               ユーザID
$basic['related_to']        関連アイテム
$basic['lang']              言語 
```

\(※\) publication\_dateは，publication\_year, publication\_month, publication\_mdayをあわせたものです．登録，編集なら年月日を一度に設定できます．確認，詳細表示の場合は年月日の文字列です．

## 2. Basic Informationのフォームデータ構造 <a id="2-basic-information"></a>

送信されるアイテムの Basic Information フォームデータは以下の構造です．

**表 3.1. フォームデータ構造**

| 名前 | 内容 | 備考 |
| :--- | :--- | :--- |
| item\_type\_id | アイテムタイプID |  |
| title | タイトル |  |
| keywords | キーワード |  |
| description | コメント |  |
| doi | DOI |  |
| change\_log | 変更内容 | 変更履歴に追加される |
| PublicationDateYear | 年 |  |
| PublicationDateMonth | 月 |  |
| PublicationDateDay | 日 |  |
| lang | 言語 |  |
| related\_to | 関連アイテム |  |
| related\_to\_check | 関連アイテム |  |
| related\_to\_check\_all | 関連アイテム |  |

## 3. array xnpGetBasicInformationDetailBlock\( int item\_id \) <a id="3-array-xnpgetbasicinformationdetailblock-int-item-id"></a>

アイテム詳細表示に必要な Basic Information を返します．

### 3.1. 内部で参照する $\_POST 変数 <a id="3-1-post"></a>

なし

### 3.2. 画面 <a id="3-2"></a>

なし

### 3.3. 送信データ <a id="3-3"></a>

なし

## 4. array xnpGetBasicInformationEditBlock\( int item\_id \) <a id="4-array-xnpgetbasicinformationeditblock-int-item-id"></a>

アイテム編集画面のフォームを生成します．

### 4.1. 内部で参照する $\_POST 変数 <a id="4-1-post"></a>

表 3.1. 「フォームデータ構造」のフォームデータをフォームの初期値に使用します．

### 4.2. 画面 <a id="4-2"></a>

なし

### 4.3. 送信データ <a id="4-3"></a>

表 3.1. 「フォームデータ構造」

## 5. array xnpGetBasicInformationConfirmBlock\( int item\_id \) <a id="5-array-xnpgetbasicinformationconfirmblock-int-item-id"></a>

アイテム登録，アイテム編集時の内容確認画面に表示するフォームを生成します．

### 5.1. 内部で参照する $\_POST 変数 <a id="5-1-post"></a>

表 3.1. 「フォームデータ構造」のフォームデータを確認画面に表示します．

### 5.2. 画面 <a id="5-2"></a>

なし

### 5.3. 送信データ <a id="5-3"></a>

なし

## 6. array xnpGetBasicInformationRegisterBlock\(\) <a id="6-array-xnpgetbasicinformationregisterblock"></a>

登録画面，編集画面に表示する Basic Information のフォームを作成します．

### 6.1. 内部で参照する $\_POST 変数 <a id="6-1-post"></a>

表 3.1. 「フォームデータ構造」の値をフォームの初期値に使用します．

### 6.2. 画面 <a id="6-2"></a>

なし

### 6.3. 送信データ <a id="6-3"></a>

表 3.1. 「フォームデータ構造」

## 7. bool xnpInsertBasicInformation\( int &item\_id \) <a id="7-bool-xnpinsertbasicinformation-int-item-id"></a>

Basic Information をデータベースに登録します．アイテムのIDを引数 item\_id に代入します．

### 7.1. 内部で参照する $\_POST 変数 <a id="7-1-post"></a>

表 3.1. 「フォームデータ構造」の情報をデータベースに記録します．

## 8. bool xnpUpdateBasicInformation\( int item\_id \) <a id="8-bool-xnpupdatebasicinformation-int-item-id"></a>

アイテムの Basic Information を，引数 item\_id で指定されたアイテムに上書きします．

### 8.1. 内部で参照する $\_POST 変数 <a id="8-1-post"></a>

表 3.1. 「フォームデータ構造」の変数の内容をデータベースに上書きします．

## 9. bool xnpDeleteBasicInformation\( int item\_id \) <a id="9-bool-xnpdeletebasicinformation-int-item-id"></a>

引数 item\_id で指定されたアイテムの Basic Information とそのアイテムに関連するファイル\(添付ファイル，画像ファイル\)を削除します．

成功なら true を返します．

| ![&#x524D;&#x306E;&#x30DA;&#x30FC;&#x30B8;](https://github.com/XoopsDocs/xoonips-developerguide/tree/a6a58e91b3c2fbad05284b6a55d66570e12e94d6/en/book/assets/commonlib/prev.gif) |  | ![&#x6B21;&#x306E;&#x30DA;&#x30FC;&#x30B8;](https://github.com/XoopsDocs/xoonips-developerguide/tree/a6a58e91b3c2fbad05284b6a55d66570e12e94d6/en/book/assets/commonlib/next.gif) |
| :--- | :--- | :--- |
|  | ![&#x30DB;&#x30FC;&#x30E0;](https://github.com/XoopsDocs/xoonips-developerguide/tree/a6a58e91b3c2fbad05284b6a55d66570e12e94d6/en/book/assets/commonlib/home.gif) |  |

Last updated: 2010/04/15

