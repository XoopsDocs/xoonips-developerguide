## 11\. bool xnpGetDownloadNotificationOptionRegisterBlock( string dirname, int option = 0 ) {#11-bool-xnpgetdownloadnotificationoptionregisterblock-string-dirname-int-option-0}

添付ファイルのダウンロード通知を登録するフォームを生成します．アイテムタイプがアイテム登録画面を作成する際に使用します．

dirname引数で添付ファイルが属するモジュールのフォルダ名を指定します．option引数で，通知の初期値を指定します．1で通知する，0で通知しない，を意味します．option引数省略時のデフォルト値は0です．

$_POST[&#039;attachment_dl_notify&#039;]が定義されている場合はoption引数の値は無視されます．

### 11.1\. 内部で参照する $_POST 変数 {#11-1-post}

*   $_POST[&#039;attachment_dl_notify&#039;]

### 11.2\. 送信データ {#11-2}

*   $_POST[&#039;attachment_dl_notify&#039;]