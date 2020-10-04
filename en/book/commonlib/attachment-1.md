# attachment

## 第6章 Attachment

アイテムにファイルを添付したい場合に使用します．\($name 引数については [章 14. 補足: Attachment, TextFile 系関数の $name 引数について](https://github.com/XoopsDocs/xoonips-developerguide/tree/a6a58e91b3c2fbad05284b6a55d66570e12e94d6/en/book/commonlib/auxil.html) を参照\)

## 1. array xnpGetAttachmentDetailBlock\( int item\_id, string name \)

アイテム詳細画面に表示するフォームを作成します．ファイル名とサイズを表示します．ファイルをダウンロードするにはファイル名をクリックします．

### 1.1. 内部で参照する $\_POST 変数

なし

### 1.2. 画面

誰でもダウンロード可能な場合

> ![](https://github.com/XoopsDocs/xoonips-developerguide/tree/a6a58e91b3c2fbad05284b6a55d66570e12e94d6/en/book/commonlib/images/xnpGetAttachmentDetailBlock3.gif)

ログインユーザのみダウンロード可能, かつログインユーザの場合

> ![](https://github.com/XoopsDocs/xoonips-developerguide/tree/a6a58e91b3c2fbad05284b6a55d66570e12e94d6/en/book/commonlib/images/xnpGetAttachmentDetailBlock4.gif)

ログインユーザのみダウンロード可能, かつゲストユーザの場合

> ![](https://github.com/XoopsDocs/xoonips-developerguide/tree/a6a58e91b3c2fbad05284b6a55d66570e12e94d6/en/book/commonlib/images/xnpGetAttachmentDetailBlock2.gif)

### 1.3. 送信データ

なし

## 2. array xnpGetAttachmentEditBlock\( int item\_id, string name \)

アイテム編集画面に表示するフォームを作成します．アップロードするファイルの指定と，アップ済みファイルの情報とその削除ボタンを表示します．

### 2.1. 内部で参照する $\_POST 変数

* $\_POST\['mode'\]
* $\_POST\['fileID'\]
* $\_POST\["${name}FileID"\]

### 2.2. 画面

> ![](https://github.com/XoopsDocs/xoonips-developerguide/tree/a6a58e91b3c2fbad05284b6a55d66570e12e94d6/en/book/commonlib/images/xnpGetAttachmentEditBlock.gif)

### 2.3. 送信データ

Delete ボタン → 現在の画面へ以下を送信する．

* $\_POST\['mode'\] = 'Delete'
* $\_POST\["${name}FileID"\] = $file\_id
* $\_POST\['fileID'\]

Submit ボタン → 確認画面へ以下を送信する

* $\_POST\['mode'\]
* $\_POST\["${name}FileID"\]
* $\_FILES\["${name}"\]

## 3. array xnpGetAttachmentConfirmBlock\( int item\_id, string name \)

登録確認画面，編集確認画面に表示するフォームを作成します．

### 3.1. 内部で参照する $\_POST 変数

* $\_POST\["${name}FileID"\]
* $\_FILES\["${name}"\]

### 3.2. 画面

> ![](https://github.com/XoopsDocs/xoonips-developerguide/tree/a6a58e91b3c2fbad05284b6a55d66570e12e94d6/en/book/commonlib/images/xnpGetAttachmentConfirmBlock.gif)

### 3.3. 送信データ

* $\_POST\["${name}FileID"\] = $file\_id

## 4. array xnpGetAttachmentRegisterBlock\( string name \)

→ [項2. 「array xnpGetAttachmentEditBlock\( int item\_id, string name \)」](https://github.com/XoopsDocs/xoonips-developerguide/tree/a6a58e91b3c2fbad05284b6a55d66570e12e94d6/en/book/commonlib/attachment.html#func-xnpGetAttachmentEditBlock) と同じ

## 5. xnpInsertAttachemnt : \(無し\)

代わりに [項6. 「bool xnpUpdateAttachment\( int item\_id, string name \)」](https://github.com/XoopsDocs/xoonips-developerguide/tree/a6a58e91b3c2fbad05284b6a55d66570e12e94d6/en/book/commonlib/attachment.html#func-xnpUpdateAttachment) を使用してください

## 6. bool xnpUpdateAttachment\( int item\_id, string name \)

添付ファイルをアイテムに登録します．既に添付ファイルがある場合はその情報を上書きします．

### 6.1. 内部で参照する $\_POST 変数

* $\_POST\['fileID'\]

## 7. xnpDeleteAttachemnt : \(無し\)

[項9. 「bool xnpDeleteBasicInformation\( int item\_id \)」](https://github.com/XoopsDocs/xoonips-developerguide/tree/a6a58e91b3c2fbad05284b6a55d66570e12e94d6/en/book/commonlib/basicinfo.html#func-xnpDeleteBasicInformation) が Attachment の削除を行うので，この関数はありません．

## 8. bool xnpGetDownloadLimitationOptionRegisterBlock\( string dirname, int option = 0 \)

添付ファイルのダウンロード制限を登録するフォームを生成します．アイテムタイプがアイテム登録画面を作成する際に使用します．

dirname引数で添付ファイルが属するモジュールのフォルダ名を指定します．option引数で，制限の初期値を指定します．1でログインユーザに限定，0で全てのユーザに解放，を意味します．option引数省略時のデフォルト値は0です．

$\_POST\['attachment\_dl\_limit'\]が定義されている場合はoption引数の値は無視されます．

### 8.1. 内部で参照する $\_POST 変数

* $\_POST\['attachment\_dl\_limit'\]

### 8.2. 送信データ

* $\_POST\['attachment\_dl\_limit'\]

## 9. bool xnpGetDownloadLimitationOptionEditBlock\( string dirname, int option \)

添付ファイルのダウンロード制限を編集するフォームを生成します．アイテムタイプがアイテム編集画面を作成する際に使用します．

dirname引数で添付ファイルが属するモジュールのフォルダ名を指定します．option引数で，制限の初期値を指定します．1でログインユーザに限定，0で全てのユーザに解放，を意味します．

$\_POST\['attachment\_dl\_limit'\]が定義されている場合はoption引数の値は無視されます．

### 9.1. 内部で参照する $\_POST 変数

* $\_POST\['attachment\_dl\_limit'\]

### 9.2. 送信データ

* $\_POST\['attachment\_dl\_limit'\]

## 10. bool xnpGetDownloadLimitationOptionConfirmBlock\( string dirname \)

添付ファイルのダウンロード制限を確認するフォームを生成します．

dirname引数で添付ファイルが属するモジュールのフォルダ名を指定します．

### 10.1. 内部で参照する $\_POST 変数

* $\_POST\['attachment\_dl\_limit'\]

### 10.2. 送信データ

* $\_POST\['attachment\_dl\_limit'\]

## 11. bool xnpGetDownloadNotificationOptionRegisterBlock\( string dirname, int option = 0 \)

添付ファイルのダウンロード通知を登録するフォームを生成します．アイテムタイプがアイテム登録画面を作成する際に使用します．

dirname引数で添付ファイルが属するモジュールのフォルダ名を指定します．option引数で，通知の初期値を指定します．1で通知する，0で通知しない，を意味します．option引数省略時のデフォルト値は0です．

$\_POST\['attachment\_dl\_notify'\]が定義されている場合はoption引数の値は無視されます．

### 11.1. 内部で参照する $\_POST 変数

* $\_POST\['attachment\_dl\_notify'\]

### 11.2. 送信データ

* $\_POST\['attachment\_dl\_notify'\]

## 12. bool xnpGetDownloadNotificationOptionEditBlock\( string dirname, int option \)

添付ファイルのダウンロード通知を編集するフォームを生成します．アイテムタイプがアイテム編集画面を作成する際に使用します．

dirname引数で添付ファイルが属するモジュールのフォルダ名を指定します．option引数で，通知の初期値を指定します．1で通知する，0で通知しない，を意味します．

$\_POST\['attachment\_dl\_notify'\]が定義されている場合はoption引数の値は無視されます．

### 12.1. 内部で参照する $\_POST 変数

* $\_POST\['attachment\_dl\_notify'\]

### 12.2. 送信データ

* $\_POST\['attachment\_dl\_notify'\]

## 13. bool xnpGetDownloadNotificationOptionConfirmBlock\( string dirname \)

添付ファイルのダウンロード通知を確認するフォームを生成します．

dirname引数で添付ファイルが属するモジュールのフォルダ名を指定します．

### 13.1. 内部で参照する $\_POST 変数

* $\_POST\['attachment\_dl\_notify'\]

### 13.2. 送信データ

* $\_POST\['attachment\_dl\_notify'\]

## 14. bool xnpGetDownloadConfirmationBlock\( int item\_id, int download\_file\_id, bool attachment\_dl\_notify, bool use\_license, int use\_cc, string rights \)

添付ファイルのダウンロード前に合意を求めるポップアップを表示するブロックを生成します。

download\_file\_id引数がfalseでないなら，download\_file\_idで指定されたファイルのダウンロードボタンを自動で押します．falseなら押しません． attachment\_dl\_notifyがtrueならダウンロード前にダウンロード通知の合意を求め，falseなら求めません． use\_licenseがtrueならダウンロード前にライセンスの合意を求め，falseなら求めません．

rightsにはライセンス文を指定します．use\_ccには，rightsがテキスト形式なら0を指定し，HTML形式なら1を指定します．

attachment\_dl\_notifyとuse\_licenseの片方でもtrueなら，ユーザは求められた全ての合意で「合意します」を選択しないとファイルをダウンロードできません．

### 14.1. 内部で参照する $\_POST 変数

* なし

### 14.2. 送信データ

* $\_POST\['file\_id'\]
* $\_POST\['xoonips\_download\_with\_token'\]
* \(XOOPSのXoopsToken．名前は'xoonips\_download\_token'\)

