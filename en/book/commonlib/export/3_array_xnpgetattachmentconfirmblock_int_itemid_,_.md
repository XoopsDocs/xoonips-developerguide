## 3\. array xnpGetAttachmentConfirmBlock( int item_id, string name ) {#3-array-xnpgetattachmentconfirmblock-int-item-id-string-name}

登録確認画面，編集確認画面に表示するフォームを作成します．

### 3.1\. 内部で参照する $_POST 変数 {#3-1-post}

*   $_POST[&quot;${name}FileID&quot;]

*   $_FILES[&quot;${name}&quot;]

### 3.2\. 画面 {#3-2}

> ![](../../assets/commonlib/xnpGetAttachmentConfirmBlock.gif)

### 3.3\. 送信データ {#3-3}

*   $_POST[&quot;${name}FileID&quot;] = $file_id