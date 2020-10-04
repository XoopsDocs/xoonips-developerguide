# itemindex

| ![&#x524D;&#x306E;&#x30DA;&#x30FC;&#x30B8;](https://github.com/XoopsDocs/xoonips-developerguide/tree/a6a58e91b3c2fbad05284b6a55d66570e12e94d6/en/book/assets/commonlib/prev.gif) |  | ![&#x6B21;&#x306E;&#x30DA;&#x30FC;&#x30B8;](https://github.com/XoopsDocs/xoonips-developerguide/tree/a6a58e91b3c2fbad05284b6a55d66570e12e94d6/en/book/assets/commonlib/next.gif) |
| :--- | :---: | :--- |


## 第4章 Index <a id="4-index"></a>

## 1. array xnpGetIndexDetailBlock\( int item\_id, bool button\_flag = true \) <a id="1-array-xnpgetindexdetailblock-int-item-id-bool-button-flag-true"></a>

アイテム詳細画面の Index 欄に表示するフォームを生成する．

### 1.1. 内部で参照する $\_POST 変数 <a id="1-1-post"></a>

なし

### 1.2. 画面 <a id="1-2"></a>

> ![](https://github.com/XoopsDocs/xoonips-developerguide/tree/a6a58e91b3c2fbad05284b6a55d66570e12e94d6/en/book/assets/commonlib/xnpGetIndexDetailBlock.gif)

※ インデックスの右側のボタン，表示は閲覧者ごとに以下の様に場合分けされる \(図は Reject ボタン の例\)．

* モデレータ
  * 承認済みの Public インデックス，Group インデックス
    * Reject ボタンを表示
  * 承認待ちの Public インデックス，Group インデックス
    * Accetpt ボタンを表示
    * Reject ボタンを表示
* 承認権限を持つグループ管理者
  * 承認済みの Group インデックス
    * Reject ボタンを表示
  * 承認待ちの Public インデックス
    * 文字列 '\(Pending\)'を表示
  * 承認待ちの Group インデックス
    * Accept ボタンを表示
    * Reject ボタンを表示
  * 承認権限を持たないグループ管理者
    * 承認待ちのインデックス
      * 文字列 '\(Pending\)' を表示
  * アイテム作成者
    * 承認待ちの Public インデックス，Group インデックス
      * 文字列 '\(Pending\)' を表示
  * 上記以外のユーザ，ゲスト
    * 承認待ちの Public インデックス，Group インデックス
      * 文字列 '\(Pending\)'を表示

※ 各ボタンの働きは以下の通り

* Reject ボタン，Withdraw ボタン
  * 承認待ち状態を未承認へ変更する．
  * 二つのボタンはラベルが異なるだけで働きは同じ．
* Accept ボタン
  * 承認待ち状態を承認済みへ変更する．

※ インデックスキーワードをクリックすると，そのキーワードに属するアイテムの一覧を表示する．

### 1.3. 送信データ <a id="1-3"></a>

* Reject ボタン，Withdraw ボタン
  * フォーム \(name = 'cancel\_certify'\) に以下のパラメータをセットして submit する
    * index\_id = 承認を取り消すインデックスの ID
    * item\_id = 承認を取り消すアイテムの ID
    * op = 'cancel\_certify'
* Accept ボタン
  * フォーム \(name = 'accept\_certify'\) に以下のパラメータをセットして submit する
    * index\_id = 承認するインデックスのID
    * item\_id = 承認するアイテムのID
    * op = 'accept\_certify'
* ボタンに共通する事柄
  * ボタン押下時に JavaScript のダイアログで OK/Cancel を問い合わせる．
  * フォームは `detail.php` の Smarty テンプレートに定義する．

## 2. array xnpGetIndexEditBlock\( int item\_id \) <a id="2-array-xnpgetindexeditblock-int-item-id"></a>

アイテム編集画面の Index 欄に表示するフォームを生成します．

### 2.1. 内部で参照する $\_POST 変数 <a id="2-1-post"></a>

* $\_POST\['xnpindexCheckedXID'\]

### 2.2. 画面 <a id="2-2"></a>

$\_POST\['xnpindexCheckedXID'\] に指定されたインデックスキーワードを以下の様に表示します．

> ![](https://github.com/XoopsDocs/xoonips-developerguide/tree/a6a58e91b3c2fbad05284b6a55d66570e12e94d6/en/book/assets/commonlib/xnpGetIndexEditBlock.gif)

### 2.3. 送信データ <a id="2-3"></a>

なし

## 3. array xnpGetIndexConfirmBlock\( int item\_id \) <a id="3-array-xnpgetindexconfirmblock-int-item-id"></a>

登録確認画面，編集確認画面の Index 欄のフォームを生成します．

### 3.1. 内部で参照する $\_POST 変数 <a id="3-1-post"></a>

* $\_POST\['xnpindexCheckedXID'\]

### 3.2. 画面 <a id="3-2"></a>

$\_POST\['xnpindexCheckedXID'\] に指定されたインデックスキーワードを以下の様に表示します．

> ![](https://github.com/XoopsDocs/xoonips-developerguide/tree/a6a58e91b3c2fbad05284b6a55d66570e12e94d6/en/book/assets/commonlib/xnpGetIndexConfirmBlock.gif)

### 3.3. 送信データ <a id="3-3"></a>

なし

## 4. array xnpGetIndexRegisterBlock\(\) <a id="4-array-xnpgetindexregisterblock"></a>

アイテム登録画面の Index 欄に表示するフォームを生成します．

### 4.1. 内部で参照する $\_POST 変数 <a id="4-1-post"></a>

* $\_POST\['xnpindexCheckedXID'\]

### 4.2. 画面 <a id="4-2"></a>

$\_POST\['xnpindexCheckedXID'\] に指定されたインデックスキーワードを以下の様に表示します．

> ![](https://github.com/XoopsDocs/xoonips-developerguide/tree/a6a58e91b3c2fbad05284b6a55d66570e12e94d6/en/book/assets/commonlib/xnpGetIndexRegisterBlock.gif)

### 4.3. 送信データ <a id="4-3"></a>

なし

## 5. xnpInsertIndex : \(無し\) <a id="5-xnpinsertindex"></a>

代わりに 項6. 「bool xnpUpdateIndex\( int item\_id \)」 を使用してください．

## 6. bool xnpUpdateIndex\( int item\_id \) <a id="6-bool-xnpupdateindex-int-item-id"></a>

引数 item\_id で指定されるアイテムを，選択されたインデックスに登録します．選択を解除されたインデックスから登録を抹消します．

グループ管理者，モデレータの承認が必要な設定であれば，インデックスに対応する管理者のメールアドレスに承認要求メールを送信します．

### 6.1. 内部で参照する $\_POST 変数 <a id="6-1-post"></a>

選択されたインデックスキーワードを以下の変数から取得します．

* $\_POST\['xnpindexCheckedXID'\]

## 7. xnpDeleteIndex : \(無し\) <a id="7-xnpdeleteindex"></a>

項9. 「bool xnpDeleteBasicInformation\( int item\_id \)」 が Index の削除を行うので，この関数はありません．

| ![&#x524D;&#x306E;&#x30DA;&#x30FC;&#x30B8;](https://github.com/XoopsDocs/xoonips-developerguide/tree/a6a58e91b3c2fbad05284b6a55d66570e12e94d6/en/book/assets/commonlib/prev.gif) |  | ![&#x6B21;&#x306E;&#x30DA;&#x30FC;&#x30B8;](https://github.com/XoopsDocs/xoonips-developerguide/tree/a6a58e91b3c2fbad05284b6a55d66570e12e94d6/en/book/assets/commonlib/next.gif) |
| :--- | :--- | :--- |
|  | ![&#x30DB;&#x30FC;&#x30E0;](https://github.com/XoopsDocs/xoonips-developerguide/tree/a6a58e91b3c2fbad05284b6a55d66570e12e94d6/en/book/assets/commonlib/home.gif) |  |

Last updated: 2010/04/15

