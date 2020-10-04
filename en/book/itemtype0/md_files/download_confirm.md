# download\_confirm

## 第22章 ダウンロード前の合意要求

添付ファイルのダウンロード前に，ライセンスの合意とダウンロード通知の合意を求めます．そのためにアイテムタイプは，以下の関数を実装します．

* ライセンスの合意要求の有無を返す関数
* ダウンロードの通知の有無を返す関数
* 合意を問い合わせるブロックを生成する関数

合意のパターンは以下の4種類です。

* ライセンスとダウンロード通知の合意が必要
* ライセンスの合意が必要
* ダウンロード通知の合意が必要
* どちらの合意も不要

ライセンスの合意が必要な添付ファイルの場合、システムはユーザ にアイテムのライセンス文を提示し合意を求めます。ダウンロードを通知 する場合、システムはユーザにダウンロードが通知される旨を告知して合 意を求めます。合意されない場合はダウンロードできません。

この機能を利用するには，次の &lt;モジュール名&gt;GetDownloadConfirmationBlock\( $item\_id, $download\_file\_id \) を定義する必要があります．

以下の項目も参照してください．

* xnpGetAttachmentDetailBlock
* xnpGetDownloadConfirmationBlock
* &lt;モジュール名&gt;GetDownloadConfirmationBlock

## 1. ライセンスの合意要求の有無

アイテムタイプモジュールの以下の関数で，ダウンロード前の合意が必要かどうかを返してください．

```text
bool <モジュール名>GetDownloadConfirmationRequired( $item_id )
```

* 戻り値 : true\(ダウンロード前に合意が必要\)
* 戻り値 : false\(ダウンロード前に合意が不要\)

## 2. ダウンロードの通知の有無

添付ファイルのダウンロードをアイテム作成者に通知することができます．通知の要否を返す以下の関数を実装してください．実装のないアイテムタイプは，通知しないものとみなされます．

```text
bool <モジュール名>GetAttachmentDownloadNotifyOption( $item_id )
```

* 引数 item\_id: ダウンロードする添付ファイルを持つアイテムのID
* 戻り値 : true\(ダウンロードを通知する\)
* 戻り値 : false\(ダウンロードを通知しない\)

## 3. 合意要求ブロック

合意を求めるブロックを返す以下の関数を定義してください．

```text
string <モジュール名>GetDownloadConfirmationBlock( $item_id, $download_file_id )
```

* 引数 item\_id: アイテムのID
* 引数 download\_file\_id: ダウンロードするファイルのID．
* 戻り値 : ライセンスとダウンロード通知の合意を求めるブロック

関数xnpGetDownloadConfirmationBlock\(\)を呼び，その戻り値をそのまま返してください．

以下の項目も参照してください．

* xnpGetDownloadConfirmationBlock

