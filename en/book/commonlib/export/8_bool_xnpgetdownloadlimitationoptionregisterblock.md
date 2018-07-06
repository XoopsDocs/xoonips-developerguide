## 8\. bool xnpGetDownloadLimitationOptionRegisterBlock( string dirname, int option = 0 ) {#8-bool-xnpgetdownloadlimitationoptionregisterblock-string-dirname-int-option-0}

添付ファイルのダウンロード制限を登録するフォームを生成します．アイテムタイプがアイテム登録画面を作成する際に使用します．

dirname引数で添付ファイルが属するモジュールのフォルダ名を指定します．option引数で，制限の初期値を指定します．1でログインユーザに限定，0で全てのユーザに解放，を意味します．option引数省略時のデフォルト値は0です．

$_POST[&#039;attachment_dl_limit&#039;]が定義されている場合はoption引数の値は無視されます．

### 8.1\. 内部で参照する $_POST 変数 {#8-1-post}

*   $_POST[&#039;attachment_dl_limit&#039;]

### 8.2\. 送信データ {#8-2}

*   $_POST[&#039;attachment_dl_limit&#039;]