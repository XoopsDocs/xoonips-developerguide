# preview

## 第5章 Preview <a id="5-preview"></a>

アイテムに画像を添付したい場合に使用します．編集，登録の場合は画像の削除，追加が可能です．詳細表示の場合はサムネイルクリックで原寸大画像にアクセスできます．

## 1. array xnpGetPreviewDetailBlock\( int item\_id \) <a id="1-array-xnpgetpreviewdetailblock-int-item-id"></a>

アイテム詳細画面に表示する Previewフォーム を作成します．

### 1.1. 内部で参照する $\_POST 変数 <a id="1-1-post"></a>

なし

### 1.2. 画面 <a id="1-2"></a>

> ![](../../../.gitbook/assets/xnpGetPreviewDetailBlock%20%282%29.gif)

### 1.3. 送信データ <a id="1-3"></a>

なし

## 2. array xnpGetPreviewEditBlock\( int item\_id \) <a id="2-array-xnpgetprevieweditblock-int-item-id"></a>

アイテム編集画面に表示する Preview 欄を生成します．

Update ボタン押下で画像ファイルをサーバヘアップロードし，サムネイル画像を作成します．

### 2.1. 内部で参照する $\_POST 変数 <a id="2-1-post"></a>

* $\_POST\['mode'\]
* $\_POST\['fileID'\]
* $\_POST\['previewFileID'\]
* $\_POST\['previewCaption'\]
* $\_FILES\['preview'\]

### 2.2. 画面 <a id="2-2"></a>

> ![](../../../.gitbook/assets/xnpGetPreviewEditBlock%20%282%29.gif)

### 2.3. 送信データ <a id="2-3"></a>

* Upload ボタン → 現在の画面へ以下を送信する．
  * $\_POST\['mode'\] = 'Upload'
  * $\_POST\['previewFileID'\] // \(コンマ区切りの file\_id\)
  * $\_FILES\['preview'\]
  * $\_POST\['previewCaption'\]
* Delete ボタン → 現在の画面へ以下を送信する．
  * $\_POST\['mode'\] = 'Delete'
  * $\_POST\['previewFileID'\] // \(コンマ区切りの file\_id\)
  * $\_POST\['fileID'\]
* Submit ボタン → 確認画面へ以下を送信する．
  * $\_POST\['mode'\]
  * $\_POST\['previewFileID'\] // \(コンマ区切りの file\_id\)

※ この関数が生成したフォームと一緒に以下の JavaScript を定義してください．

> ```text
> <script type="text/javascript">> <!--> function xnpSubmitFileUpload( form, name ){> form.mode.value = 'Upload';> eval( 'var fileobj = form.' + name + ';' );> if ( fileobj.value == null || fileobj.value == "" ){> window.alert( 'error: no file specified.' );> return false;> }> getCheckedIndexes( form );> saveScrollPosition();> form.action = '';> form.submit();> }> function xnpSubmitFileDelete( form, name, fileID ){> form.mode.value = 'Delete';> form.fileID.value = fileID;> getCheckedIndexes( form );> saveScrollPosition();> form.action = '';> form.submit();> }> //-->> </script>
> ```

※ フォーム内に，以下のタグが必要です．

> ```text
> <input type='hidden' name='mode' value=''>> <input type='hidden' name='fileID' value=''>
> ```

※ フォームには，以下の method と enctype の指定が必要です．

> ```text
> <form method="POST" enctype="multipart/form-data" ….. >
> ```

## 3. array xnpGetPreviewConfirmBlock\( int item\_id \) <a id="3-array-xnpgetpreviewconfirmblock-int-item-id"></a>

登録確認画面，編集確認画面に表示する Preview フォームを作成します．

### 3.1. 内部で参照する $\_POST 変数 <a id="3-1-post"></a>

* $\_POST\['previewFileID'\]

### 3.2. 画面 <a id="3-2"></a>

> ![](../../../.gitbook/assets/xnpGetPreviewConfirmBlock%20%282%29.gif)

### 3.3. 送信データ <a id="3-3"></a>

* $\_POST\['previewFileID'\]

## 4. array xnpGetPreviewRegisterBlock\(\) <a id="4-array-xnpgetpreviewregisterblock"></a>

→ 項2. 「array xnpGetPreviewEditBlock\( int item\_id \)」と同じ

## 5. xnpInsertPreview : \(無し\) <a id="5-xnpinsertpreview"></a>

代わりに 項6. 「bool xnpUpdatePreview\( int item\_id \)」 を使用してください．

## 6. bool xnpUpdatePreview\( int item\_id \) <a id="6-bool-xnpupdatepreview-int-item-id"></a>

新しく追加された画像をアイテムに追加します．削除された画像をアイテムから削除します．

### 6.1. 内部で参照する $\_POST 変数 <a id="6-1-post"></a>

* $\_POST\['previewFileID'\]

## 7. xnpDeletePreview : \(無し\) <a id="7-xnpdeletepreview"></a>

項9. 「bool xnpDeleteBasicInformation\( int item\_id \)」 が Perview の削除を行うので，この関数はありません．

