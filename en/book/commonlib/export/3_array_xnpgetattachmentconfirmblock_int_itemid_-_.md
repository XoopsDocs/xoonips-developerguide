# 3. array xnpGetAttachmentConfirmBlock\( int item\_id, string name \)

登録確認画面，編集確認画面に表示するフォームを作成します．

## 3.1. 内部で参照する $\_POST 変数 <a id="3-1-post"></a>

* $\_POST\["${name}FileID"\]
* $\_FILES\["${name}"\]

## 3.2. 画面 <a id="3-2"></a>

> ![](https://github.com/XoopsDocs/xoonips-developerguide/tree/a6a58e91b3c2fbad05284b6a55d66570e12e94d6/en/book/assets/commonlib/xnpGetAttachmentConfirmBlock.gif)

## 3.3. 送信データ <a id="3-3"></a>

* $\_POST\["${name}FileID"\] = $file\_id

