# itemindex {#itemindex}

| ![前のページ](../../assets/commonlib/prev.gif)  |   |  ![次のページ](../../assets/commonlib/next.gif) |
| --- | :-: | --- |

## 第4章 Index {#4-index}

## 1\. array xnpGetIndexDetailBlock( int item_id, bool button_flag = true ) {#1-array-xnpgetindexdetailblock-int-item-id-bool-button-flag-true}

アイテム詳細画面の Index 欄に表示するフォームを生成する．

### 1.1\. 内部で参照する $_POST 変数 {#1-1-post}

なし

### 1.2\. 画面 {#1-2}

> ![](../../assets/commonlib/xnpGetIndexDetailBlock.gif)

※ インデックスの右側のボタン，表示は閲覧者ごとに以下の様に場合分けされる (図は Reject ボタン の例)．

*   モデレータ

    *   承認済みの Public インデックス，Group インデックス

        *   Reject ボタンを表示

    *   承認待ちの Public インデックス，Group インデックス

        *   Accetpt ボタンを表示

        *   Reject ボタンを表示

*   承認権限を持つグループ管理者

    *   承認済みの Group インデックス

        *   Reject ボタンを表示

    *   承認待ちの Public インデックス

        *   文字列 &#039;(Pending)&#039;を表示

    *   承認待ちの Group インデックス

        *   Accept ボタンを表示

        *   Reject ボタンを表示

    *   承認権限を持たないグループ管理者

        *   承認待ちのインデックス

            *   文字列 &#039;(Pending)&#039; を表示

    *   アイテム作成者

        *   承認待ちの Public インデックス，Group インデックス

            *   文字列 &#039;(Pending)&#039; を表示

    *   上記以外のユーザ，ゲスト

        *   承認待ちの Public インデックス，Group インデックス

            *   文字列 &#039;(Pending)&#039;を表示

※ 各ボタンの働きは以下の通り

*   Reject ボタン，Withdraw ボタン

    *   承認待ち状態を未承認へ変更する．

    *   二つのボタンはラベルが異なるだけで働きは同じ．

*   Accept ボタン

    *   承認待ち状態を承認済みへ変更する．

※ インデックスキーワードをクリックすると，そのキーワードに属するアイテムの一覧を表示する．

### 1.3\. 送信データ {#1-3}

*   Reject ボタン，Withdraw ボタン

    *   フォーム (name = &#039;cancel_certify&#039;) に以下のパラメータをセットして submit する

        *   index_id = 承認を取り消すインデックスの ID

        *   item_id = 承認を取り消すアイテムの ID

        *   op = &#039;cancel_certify&#039;

*   Accept ボタン

    *   フォーム (name = &#039;accept_certify&#039;) に以下のパラメータをセットして submit する

        *   index_id = 承認するインデックスのID

        *   item_id = 承認するアイテムのID

        *   op = &#039;accept_certify&#039;

*   ボタンに共通する事柄

    *   ボタン押下時に JavaScript のダイアログで OK/Cancel を問い合わせる．

    *   フォームは `detail.php` の Smarty テンプレートに定義する．

## 2\. array xnpGetIndexEditBlock( int item_id ) {#2-array-xnpgetindexeditblock-int-item-id}

アイテム編集画面の Index 欄に表示するフォームを生成します．

### 2.1\. 内部で参照する $_POST 変数 {#2-1-post}

*   $_POST[&#039;xnpindexCheckedXID&#039;]

### 2.2\. 画面 {#2-2}

$_POST[&#039;xnpindexCheckedXID&#039;] に指定されたインデックスキーワードを以下の様に表示します．

> ![](../../assets/commonlib/xnpGetIndexEditBlock.gif)

### 2.3\. 送信データ {#2-3}

なし

## 3\. array xnpGetIndexConfirmBlock( int item_id ) {#3-array-xnpgetindexconfirmblock-int-item-id}

登録確認画面，編集確認画面の Index 欄のフォームを生成します．

### 3.1\. 内部で参照する $_POST 変数 {#3-1-post}

*   $_POST[&#039;xnpindexCheckedXID&#039;]

### 3.2\. 画面 {#3-2}

$_POST[&#039;xnpindexCheckedXID&#039;] に指定されたインデックスキーワードを以下の様に表示します．

> ![](../../assets/commonlib/xnpGetIndexConfirmBlock.gif)

### 3.3\. 送信データ {#3-3}

なし

## 4\. array xnpGetIndexRegisterBlock() {#4-array-xnpgetindexregisterblock}

アイテム登録画面の Index 欄に表示するフォームを生成します．

### 4.1\. 内部で参照する $_POST 変数 {#4-1-post}

*   $_POST[&#039;xnpindexCheckedXID&#039;]

### 4.2\. 画面 {#4-2}

$_POST[&#039;xnpindexCheckedXID&#039;] に指定されたインデックスキーワードを以下の様に表示します．

> ![](../../assets/commonlib/xnpGetIndexRegisterBlock.gif)

### 4.3\. 送信データ {#4-3}

なし

## 5\. xnpInsertIndex : (無し) {#5-xnpinsertindex}

代わりに 項6\. 「bool xnpUpdateIndex( int item_id )」 を使用してください．

## 6\. bool xnpUpdateIndex( int item_id ) {#6-bool-xnpupdateindex-int-item-id}

引数 item_id で指定されるアイテムを，選択されたインデックスに登録します．選択を解除されたインデックスから登録を抹消します．

グループ管理者，モデレータの承認が必要な設定であれば，インデックスに対応する管理者のメールアドレスに承認要求メールを送信します．

### 6.1\. 内部で参照する $_POST 変数 {#6-1-post}

選択されたインデックスキーワードを以下の変数から取得します．

*   $_POST[&#039;xnpindexCheckedXID&#039;]

## 7\. xnpDeleteIndex : (無し) {#7-xnpdeleteindex}

項9\. 「bool xnpDeleteBasicInformation( int item_id )」 が Index の削除を行うので，この関数はありません．

| ![前のページ](../../assets/commonlib/prev.gif)  |   |  ![次のページ](../../assets/commonlib/next.gif) |
| --- | --- | --- |
|   | ![ホーム](../../assets/commonlib/home.gif)  |   |

Last updated: 2010/04/15