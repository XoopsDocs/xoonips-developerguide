# 8. bool xnpGetDownloadLimitationOptionRegisterBlock\( string dirname, int option = 0 \)

添付ファイルのダウンロード制限を登録するフォームを生成します．アイテムタイプがアイテム登録画面を作成する際に使用します．

dirname引数で添付ファイルが属するモジュールのフォルダ名を指定します．option引数で，制限の初期値を指定します．1でログインユーザに限定，0で全てのユーザに解放，を意味します．option引数省略時のデフォルト値は0です．

$\_POST\['attachment\_dl\_limit'\]が定義されている場合はoption引数の値は無視されます．

## 8.1. 内部で参照する $\_POST 変数 <a id="8-1-post"></a>

* $\_POST\['attachment\_dl\_limit'\]

## 8.2. 送信データ <a id="8-2"></a>

* $\_POST\['attachment\_dl\_limit'\]

