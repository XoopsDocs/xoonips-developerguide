# 2. array xnpGetAttachmentEditBlock\( int item\_id, string name \)

アイテム編集画面に表示するフォームを作成します．アップロードするファイルの指定と，アップ済みファイルの情報とその削除ボタンを表示します．

## 2.1. 内部で参照する $\_POST 変数 <a id="2-1-post"></a>

* $\_POST\['mode'\]
* $\_POST\['fileID'\]
* $\_POST\["${name}FileID"\]

## 2.2. 画面 <a id="2-2"></a>

> ![](https://github.com/XoopsDocs/xoonips-developerguide/tree/a6a58e91b3c2fbad05284b6a55d66570e12e94d6/en/book/assets/commonlib/xnpGetAttachmentEditBlock.gif)

## 2.3. 送信データ <a id="2-3"></a>

Delete ボタン → 現在の画面へ以下を送信する．

* $\_POST\['mode'\] = 'Delete'
* $\_POST\["${name}FileID"\] = $file\_id
* $\_POST\['fileID'\]

Submit ボタン → 確認画面へ以下を送信する

* $\_POST\['mode'\]
* $\_POST\["${name}FileID"\]
* $\_FILES\["${name}"\]

