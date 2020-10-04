# attachment

| ![&#x524D;&#x306E;&#x30DA;&#x30FC;&#x30B8;](https://github.com/XoopsDocs/xoonips-developerguide/tree/a6a58e91b3c2fbad05284b6a55d66570e12e94d6/en/book/assets/commonlib/prev.gif) |  | ![&#x6B21;&#x306E;&#x30DA;&#x30FC;&#x30B8;](https://github.com/XoopsDocs/xoonips-developerguide/tree/a6a58e91b3c2fbad05284b6a55d66570e12e94d6/en/book/assets/commonlib/next.gif) |
| :--- | :---: | :--- |


## 第6章 Attachment <a id="6-attachment"></a>

アイテムにファイルを添付したい場合に使用します．\($name 引数については 章 14. _補足: Attachment, TextFile 系関数の $name 引数について_ を参照\)

## 1. array xnpGetAttachmentDetailBlock\( int item\_id, string name \) <a id="1-array-xnpgetattachmentdetailblock-int-item-id-string-name"></a>

アイテム詳細画面に表示するフォームを作成します．ファイル名とサイズを表示します．ファイルをダウンロードするにはファイル名をクリックします．

### 1.1. 内部で参照する $\_POST 変数 <a id="1-1-post"></a>

なし

### 1.2. 画面 <a id="1-2"></a>

誰でもダウンロード可能な場合

> ![](https://github.com/XoopsDocs/xoonips-developerguide/tree/a6a58e91b3c2fbad05284b6a55d66570e12e94d6/en/book/assets/commonlib/xnpGetAttachmentDetailBlock3.gif)

ログインユーザのみダウンロード可能, かつログインユーザの場合

> ![](https://github.com/XoopsDocs/xoonips-developerguide/tree/a6a58e91b3c2fbad05284b6a55d66570e12e94d6/en/book/assets/commonlib/xnpGetAttachmentDetailBlock4.gif)

ログインユーザのみダウンロード可能, かつゲストユーザの場合

> ![](https://github.com/XoopsDocs/xoonips-developerguide/tree/a6a58e91b3c2fbad05284b6a55d66570e12e94d6/en/book/assets/commonlib/xnpGetAttachmentDetailBlock2.gif)

### 1.3. 送信データ <a id="1-3"></a>

なし

## 2. array xnpGetAttachmentEditBlock\( int item\_id, string name \) <a id="2-array-xnpgetattachmenteditblock-int-item-id-string-name"></a>

アイテム編集画面に表示するフォームを作成します．アップロードするファイルの指定と，アップ済みファイルの情報とその削除ボタンを表示します．

### 2.1. 内部で参照する $\_POST 変数 <a id="2-1-post"></a>

* $\_POST\['mode'\]
* $\_POST\['fileID'\]
* $\_POST\["${name}FileID"\]

### 2.2. 画面 <a id="2-2"></a>

> ![](https://github.com/XoopsDocs/xoonips-developerguide/tree/a6a58e91b3c2fbad05284b6a55d66570e12e94d6/en/book/assets/commonlib/xnpGetAttachmentEditBlock.gif)

### 2.3. 送信データ <a id="2-3"></a>

Delete ボタン → 現在の画面へ以下を送信する．

* $\_POST\['mode'\] = 'Delete'
* $\_POST\["${name}FileID"\] = $file\_id
* $\_POST\['fileID'\]

Submit ボタン → 確認画面へ以下を送信する

* $\_POST\['mode'\]
* $\_POST\["${name}FileID"\]
* $\_FILES\["${name}"\]

## 3. array xnpGetAttachmentConfirmBlock\( int item\_id, string name \) <a id="3-array-xnpgetattachmentconfirmblock-int-item-id-string-name"></a>

登録確認画面，編集確認画面に表示するフォームを作成します．

### 3.1. 内部で参照する $\_POST 変数 <a id="3-1-post"></a>

* $\_POST\["${name}FileID"\]
* $\_FILES\["${name}"\]

### 3.2. 画面 <a id="3-2"></a>

> ![](https://github.com/XoopsDocs/xoonips-developerguide/tree/a6a58e91b3c2fbad05284b6a55d66570e12e94d6/en/book/assets/commonlib/xnpGetAttachmentConfirmBlock.gif)

### 3.3. 送信データ <a id="3-3"></a>

* $\_POST\["${name}FileID"\] = $file\_id

## 4. array xnpGetAttachmentRegisterBlock\( string name \) <a id="4-array-xnpgetattachmentregisterblock-string-name"></a>

→ 項2. 「array xnpGetAttachmentEditBlock\( int item\_id, string name \)」 と同じ

## 5. xnpInsertAttachemnt : \(無し\) <a id="5-xnpinsertattachemnt"></a>

代わりに 項6. 「bool xnpUpdateAttachment\( int item\_id, string name \)」 を使用してください

## 6. bool xnpUpdateAttachment\( int item\_id, string name \) <a id="6-bool-xnpupdateattachment-int-item-id-string-name"></a>

添付ファイルをアイテムに登録します．既に添付ファイルがある場合はその情報を上書きします．

### 6.1. 内部で参照する $\_POST 変数 <a id="6-1-post"></a>

* $\_POST\['fileID'\]

## 7. xnpDeleteAttachemnt : \(無し\) <a id="7-xnpdeleteattachemnt"></a>

項9. 「bool xnpDeleteBasicInformation\( int item\_id \)」 が Attachment の削除を行うので，この関数はありません．

## 8. bool xnpGetDownloadLimitationOptionRegisterBlock\( string dirname, int option = 0 \) <a id="8-bool-xnpgetdownloadlimitationoptionregisterblock-string-dirname-int-option-0"></a>

添付ファイルのダウンロード制限を登録するフォームを生成します．アイテムタイプがアイテム登録画面を作成する際に使用します．

dirname引数で添付ファイルが属するモジュールのフォルダ名を指定します．option引数で，制限の初期値を指定します．1でログインユーザに限定，0で全てのユーザに解放，を意味します．option引数省略時のデフォルト値は0です．

$\_POST\['attachment\_dl\_limit'\]が定義されている場合はoption引数の値は無視されます．

### 8.1. 内部で参照する $\_POST 変数 <a id="8-1-post"></a>

* $\_POST\['attachment\_dl\_limit'\]

### 8.2. 送信データ <a id="8-2"></a>

* $\_POST\['attachment\_dl\_limit'\]

## 9. bool xnpGetDownloadLimitationOptionEditBlock\( string dirname, int option \) <a id="9-bool-xnpgetdownloadlimitationoptioneditblock-string-dirname-int-option"></a>

添付ファイルのダウンロード制限を編集するフォームを生成します．アイテムタイプがアイテム編集画面を作成する際に使用します．

dirname引数で添付ファイルが属するモジュールのフォルダ名を指定します．option引数で，制限の初期値を指定します．1でログインユーザに限定，0で全てのユーザに解放，を意味します．

$\_POST\['attachment\_dl\_limit'\]が定義されている場合はoption引数の値は無視されます．

### 9.1. 内部で参照する $\_POST 変数 <a id="9-1-post"></a>

* $\_POST\['attachment\_dl\_limit'\]

### 9.2. 送信データ <a id="9-2"></a>

* $\_POST\['attachment\_dl\_limit'\]

## 10. bool xnpGetDownloadLimitationOptionConfirmBlock\( string dirname \) <a id="10-bool-xnpgetdownloadlimitationoptionconfirmblock-string-dirname"></a>

添付ファイルのダウンロード制限を確認するフォームを生成します．

dirname引数で添付ファイルが属するモジュールのフォルダ名を指定します．

### 10.1. 内部で参照する $\_POST 変数 <a id="10-1-post"></a>

* $\_POST\['attachment\_dl\_limit'\]

### 10.2. 送信データ <a id="10-2"></a>

* $\_POST\['attachment\_dl\_limit'\]

## 11. bool xnpGetDownloadNotificationOptionRegisterBlock\( string dirname, int option = 0 \) <a id="11-bool-xnpgetdownloadnotificationoptionregisterblock-string-dirname-int-option-0"></a>

添付ファイルのダウンロード通知を登録するフォームを生成します．アイテムタイプがアイテム登録画面を作成する際に使用します．

dirname引数で添付ファイルが属するモジュールのフォルダ名を指定します．option引数で，通知の初期値を指定します．1で通知する，0で通知しない，を意味します．option引数省略時のデフォルト値は0です．

$\_POST\['attachment\_dl\_notify'\]が定義されている場合はoption引数の値は無視されます．

### 11.1. 内部で参照する $\_POST 変数 <a id="11-1-post"></a>

* $\_POST\['attachment\_dl\_notify'\]

### 11.2. 送信データ <a id="11-2"></a>

* $\_POST\['attachment\_dl\_notify'\]

## 12. bool xnpGetDownloadNotificationOptionEditBlock\( string dirname, int option \) <a id="12-bool-xnpgetdownloadnotificationoptioneditblock-string-dirname-int-option"></a>

添付ファイルのダウンロード通知を編集するフォームを生成します．アイテムタイプがアイテム編集画面を作成する際に使用します．

dirname引数で添付ファイルが属するモジュールのフォルダ名を指定します．option引数で，通知の初期値を指定します．1で通知する，0で通知しない，を意味します．

$\_POST\['attachment\_dl\_notify'\]が定義されている場合はoption引数の値は無視されます．

### 12.1. 内部で参照する $\_POST 変数 <a id="12-1-post"></a>

* $\_POST\['attachment\_dl\_notify'\]

### 12.2. 送信データ <a id="12-2"></a>

* $\_POST\['attachment\_dl\_notify'\]

## 13. bool xnpGetDownloadNotificationOptionConfirmBlock\( string dirname \) <a id="13-bool-xnpgetdownloadnotificationoptionconfirmblock-string-dirname"></a>

添付ファイルのダウンロード通知を確認するフォームを生成します．

dirname引数で添付ファイルが属するモジュールのフォルダ名を指定します．

### 13.1. 内部で参照する $\_POST 変数 <a id="13-1-post"></a>

* $\_POST\['attachment\_dl\_notify'\]

### 13.2. 送信データ <a id="13-2"></a>

* $\_POST\['attachment\_dl\_notify'\]

## 14. bool xnpGetDownloadConfirmationBlock\( int item\_id, int download\_file\_id, bool attachment\_dl\_notify, bool use\_license, int use\_cc, string rights \) <a id="14-bool-xnpgetdownloadconfirmationblock-int-item-id-int-download-file-id-bool-attachment-dl-notify-bool-use-license-int-use-cc-string-rights"></a>

添付ファイルのダウンロード前に合意を求めるポップアップを表示するブロックを生成します。

download\_file\_id引数がfalseでないなら，download\_file\_idで指定されたファイルのダウンロードボタンを自動で押します．falseなら押しません． attachment\_dl\_notifyがtrueならダウンロード前にダウンロード通知の合意を求め，falseなら求めません． use\_licenseがtrueならダウンロード前にライセンスの合意を求め，falseなら求めません．

rightsにはライセンス文を指定します．use\_ccには，rightsがテキスト形式なら0を指定し，HTML形式なら1を指定します．

attachment\_dl\_notifyとuse\_licenseの片方でもtrueなら，ユーザは求められた全ての合意で「合意します」を選択しないとファイルをダウンロードできません．

### 14.1. 内部で参照する $\_POST 変数 <a id="14-1-post"></a>

* なし

### 14.2. 送信データ <a id="14-2"></a>

* $\_POST\['file\_id'\]
* $\_POST\['xoonips\_download\_with\_token'\]
* \(XOOPSのXoopsToken．名前は'xoonips\_download\_token'\)

| ![&#x524D;&#x306E;&#x30DA;&#x30FC;&#x30B8;](https://github.com/XoopsDocs/xoonips-developerguide/tree/a6a58e91b3c2fbad05284b6a55d66570e12e94d6/en/book/assets/commonlib/prev.gif) |  | ![&#x6B21;&#x306E;&#x30DA;&#x30FC;&#x30B8;](https://github.com/XoopsDocs/xoonips-developerguide/tree/a6a58e91b3c2fbad05284b6a55d66570e12e94d6/en/book/assets/commonlib/next.gif) |
| :--- | :--- | :--- |
|  | ![&#x30DB;&#x30FC;&#x30E0;](https://github.com/XoopsDocs/xoonips-developerguide/tree/a6a58e91b3c2fbad05284b6a55d66570e12e94d6/en/book/assets/commonlib/home.gif) |  |

Last updated: 2010/04/15

