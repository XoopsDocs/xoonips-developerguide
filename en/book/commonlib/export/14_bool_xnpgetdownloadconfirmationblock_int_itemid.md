## 14\. bool xnpGetDownloadConfirmationBlock( int item_id, int download_file_id, bool attachment_dl_notify, bool use_license, int use_cc, string rights ) {#14-bool-xnpgetdownloadconfirmationblock-int-item-id-int-download-file-id-bool-attachment-dl-notify-bool-use-license-int-use-cc-string-rights}

添付ファイルのダウンロード前に合意を求めるポップアップを表示するブロックを生成します。

download_file_id引数がfalseでないなら，download_file_idで指定されたファイルのダウンロードボタンを自動で押します．falseなら押しません． attachment_dl_notifyがtrueならダウンロード前にダウンロード通知の合意を求め，falseなら求めません． use_licenseがtrueならダウンロード前にライセンスの合意を求め，falseなら求めません．

rightsにはライセンス文を指定します．use_ccには，rightsがテキスト形式なら0を指定し，HTML形式なら1を指定します．

attachment_dl_notifyとuse_licenseの片方でもtrueなら，ユーザは求められた全ての合意で「合意します」を選択しないとファイルをダウンロードできません．

### 14.1\. 内部で参照する $_POST 変数 {#14-1-post}

*   なし

### 14.2\. 送信データ {#14-2}

*   $_POST[&#039;file_id&#039;]

*   $_POST[&#039;xoonips_download_with_token&#039;]

*   (XOOPSのXoopsToken．名前は&#039;xoonips_download_token&#039;)

| ![前のページ](../../assets/commonlib/prev.gif)  |   |  ![次のページ](../../assets/commonlib/next.gif) |
| --- | --- | --- |
|   | ![ホーム](../../assets/commonlib/home.gif)  |   |

Last updated: 2010/04/15