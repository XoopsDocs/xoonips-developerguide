## 2\. array xnpGetAttachmentEditBlock( int item_id, string name ) {#2-array-xnpgetattachmenteditblock-int-item-id-string-name}

アイテム編集画面に表示するフォームを作成します．アップロードするファイルの指定と，アップ済みファイルの情報とその削除ボタンを表示します．

### 2.1\. 内部で参照する $_POST 変数 {#2-1-post}

*   $_POST[&#039;mode&#039;]

*   $_POST[&#039;fileID&#039;]

*   $_POST[&quot;${name}FileID&quot;]

### 2.2\. 画面 {#2-2}

> ![](../../assets/commonlib/xnpGetAttachmentEditBlock.gif)

### 2.3\. 送信データ {#2-3}

Delete ボタン → 現在の画面へ以下を送信する．

*   $_POST[&#039;mode&#039;] = &#039;Delete&#039;

*   $_POST[&quot;${name}FileID&quot;] = $file_id

*   $_POST[&#039;fileID&#039;]

Submit ボタン → 確認画面へ以下を送信する

*   $_POST[&#039;mode&#039;]

*   $_POST[&quot;${name}FileID&quot;]

*   $_FILES[&quot;${name}&quot;]