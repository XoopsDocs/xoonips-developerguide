# 14. bool xnpGetDownloadConfirmationBlock\( int item\_id, int download\_file\_id, bool attachment\_dl\_noti

添付ファイルのダウンロード前に合意を求めるポップアップを表示するブロックを生成します。

download\_file\_id引数がfalseでないなら，download\_file\_idで指定されたファイルのダウンロードボタンを自動で押します．falseなら押しません． attachment\_dl\_notifyがtrueならダウンロード前にダウンロード通知の合意を求め，falseなら求めません． use\_licenseがtrueならダウンロード前にライセンスの合意を求め，falseなら求めません．

rightsにはライセンス文を指定します．use\_ccには，rightsがテキスト形式なら0を指定し，HTML形式なら1を指定します．

attachment\_dl\_notifyとuse\_licenseの片方でもtrueなら，ユーザは求められた全ての合意で「合意します」を選択しないとファイルをダウンロードできません．

## 14.1. 内部で参照する $\_POST 変数 <a id="14-1-post"></a>

* なし

## 14.2. 送信データ <a id="14-2"></a>

* $\_POST\['file\_id'\]
* $\_POST\['xoonips\_download\_with\_token'\]
* \(XOOPSのXoopsToken．名前は'xoonips\_download\_token'\)

| ![&#x524D;&#x306E;&#x30DA;&#x30FC;&#x30B8;](https://github.com/XoopsDocs/xoonips-developerguide/tree/a6a58e91b3c2fbad05284b6a55d66570e12e94d6/en/book/assets/commonlib/prev.gif) |  | ![&#x6B21;&#x306E;&#x30DA;&#x30FC;&#x30B8;](https://github.com/XoopsDocs/xoonips-developerguide/tree/a6a58e91b3c2fbad05284b6a55d66570e12e94d6/en/book/assets/commonlib/next.gif) |
| :--- | :--- | :--- |
|  | ![&#x30DB;&#x30FC;&#x30E0;](https://github.com/XoopsDocs/xoonips-developerguide/tree/a6a58e91b3c2fbad05284b6a55d66570e12e94d6/en/book/assets/commonlib/home.gif) |  |

Last updated: 2010/04/15

