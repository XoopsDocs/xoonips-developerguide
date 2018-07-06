# preview {#preview}

| ![前のページ](../../assets/commonlib/prev.gif)  |   |  ![次のページ](../../assets/commonlib/next.gif) |
| --- | :-: | --- |

## 第5章 Preview {#5-preview}

アイテムに画像を添付したい場合に使用します．編集，登録の場合は画像の削除，追加が可能です．詳細表示の場合はサムネイルクリックで原寸大画像にアクセスできます．

## 1\. array xnpGetPreviewDetailBlock( int item_id ) {#1-array-xnpgetpreviewdetailblock-int-item-id}

アイテム詳細画面に表示する Previewフォーム を作成します．

### 1.1\. 内部で参照する $_POST 変数 {#1-1-post}

なし

### 1.2\. 画面 {#1-2}

> ![](../../assets/commonlib/xnpGetPreviewDetailBlock.gif)

### 1.3\. 送信データ {#1-3}

なし

## 2\. array xnpGetPreviewEditBlock( int item_id ) {#2-array-xnpgetprevieweditblock-int-item-id}

アイテム編集画面に表示する Preview 欄を生成します．

Update ボタン押下で画像ファイルをサーバヘアップロードし，サムネイル画像を作成します．

### 2.1\. 内部で参照する $_POST 変数 {#2-1-post}

*   $_POST[&#039;mode&#039;]

*   $_POST[&#039;fileID&#039;]

*   $_POST[&#039;previewFileID&#039;]

*   $_POST[&#039;previewCaption&#039;]

*   $_FILES[&#039;preview&#039;]

### 2.2\. 画面 {#2-2}

> ![](../../assets/commonlib/xnpGetPreviewEditBlock.gif)

### 2.3\. 送信データ {#2-3}

*   Upload ボタン → 現在の画面へ以下を送信する．

    *   $_POST[&#039;mode&#039;] = &#039;Upload&#039;

    *   $_POST[&#039;previewFileID&#039;] // (コンマ区切りの file_id)

    *   $_FILES[&#039;preview&#039;]

    *   $_POST[&#039;previewCaption&#039;]

*   Delete ボタン → 現在の画面へ以下を送信する．

    *   $_POST[&#039;mode&#039;] = &#039;Delete&#039;

    *   $_POST[&#039;previewFileID&#039;] // (コンマ区切りの file_id)

    *   $_POST[&#039;fileID&#039;]

*   Submit ボタン → 確認画面へ以下を送信する．

    *   $_POST[&#039;mode&#039;]

    *   $_POST[&#039;previewFileID&#039;] // (コンマ区切りの file_id)

※ この関数が生成したフォームと一緒に以下の JavaScript を定義してください．

> <pre class="programlisting">&lt;script type=&quot;text/javascript&quot;&gt;
> &lt;!--
> function xnpSubmitFileUpload( form, name ){
> 	form.mode.value = &#039;Upload&#039;;
> 	eval( &#039;var fileobj = form.&#039; + name + &#039;;&#039; );
> 	if ( fileobj.value == null || fileobj.value == &quot;&quot; ){
> 		window.alert( &#039;error: no file specified.&#039; );
> 		return false;
> 	}
> 	getCheckedIndexes( form );
> 	saveScrollPosition();
> 	form.action = &#039;&#039;;
> 	form.submit();
> }
> function xnpSubmitFileDelete( form, name, fileID ){
> 	form.mode.value = &#039;Delete&#039;;
> 	form.fileID.value = fileID;
> 	getCheckedIndexes( form );
> 	saveScrollPosition();
> 	form.action = &#039;&#039;;
> 	form.submit();
> }
> //--&gt;
> &lt;/script&gt;</pre>

※ フォーム内に，以下のタグが必要です．

> <pre class="programlisting">&lt;input type=&#039;hidden&#039; name=&#039;mode&#039; value=&#039;&#039;&gt;
> &lt;input type=&#039;hidden&#039; name=&#039;fileID&#039; value=&#039;&#039;&gt;</pre>

※ フォームには，以下の method と enctype の指定が必要です．

> <pre class="programlisting">&lt;form method=&quot;POST&quot;  enctype=&quot;multipart/form-data&quot; …..  &gt;</pre>

## 3\. array xnpGetPreviewConfirmBlock( int item_id ) {#3-array-xnpgetpreviewconfirmblock-int-item-id}

登録確認画面，編集確認画面に表示する Preview フォームを作成します．

### 3.1\. 内部で参照する $_POST 変数 {#3-1-post}

*   $_POST[&#039;previewFileID&#039;]

### 3.2\. 画面 {#3-2}

> ![](../../assets/commonlib/xnpGetPreviewConfirmBlock.gif)

### 3.3\. 送信データ {#3-3}

*   $_POST[&#039;previewFileID&#039;]

## 4\. array xnpGetPreviewRegisterBlock() {#4-array-xnpgetpreviewregisterblock}

→ 項2\. 「array xnpGetPreviewEditBlock( int item_id )」と同じ

## 5\. xnpInsertPreview : (無し) {#5-xnpinsertpreview}

代わりに 項6\. 「bool xnpUpdatePreview( int item_id )」 を使用してください．

## 6\. bool xnpUpdatePreview( int item_id ) {#6-bool-xnpupdatepreview-int-item-id}

新しく追加された画像をアイテムに追加します．削除された画像をアイテムから削除します．

### 6.1\. 内部で参照する $_POST 変数 {#6-1-post}

*   $_POST[&#039;previewFileID&#039;]

## 7\. xnpDeletePreview : (無し) {#7-xnpdeletepreview}

項9\. 「bool xnpDeleteBasicInformation( int item_id )」 が Perview の削除を行うので，この関数はありません．

| ![前のページ](../../assets/commonlib/prev.gif)  |   |  ![次のページ](../../assets/commonlib/next.gif) |
| --- | --- | --- |
|   | ![ホーム](../../assets/commonlib/home.gif)  |   |

Last updated: 2010/04/15