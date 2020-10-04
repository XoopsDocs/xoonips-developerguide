# 9. bool xnpGetDownloadLimitationOptionEditBlock\( string dirname, int option \)

添付ファイルのダウンロード制限を編集するフォームを生成します．アイテムタイプがアイテム編集画面を作成する際に使用します．

dirname引数で添付ファイルが属するモジュールのフォルダ名を指定します．option引数で，制限の初期値を指定します．1でログインユーザに限定，0で全てのユーザに解放，を意味します．

$\_POST\['attachment\_dl\_limit'\]が定義されている場合はoption引数の値は無視されます．

## 9.1. 内部で参照する $\_POST 変数 <a id="9-1-post"></a>

* $\_POST\['attachment\_dl\_limit'\]

## 9.2. 送信データ <a id="9-2"></a>

* $\_POST\['attachment\_dl\_limit'\]

