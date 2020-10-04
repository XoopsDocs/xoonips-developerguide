# rights

| ![&#x524D;&#x306E;&#x30DA;&#x30FC;&#x30B8;](https://github.com/XoopsDocs/xoonips-developerguide/tree/a6a58e91b3c2fbad05284b6a55d66570e12e94d6/en/book/assets/commonlib/prev.gif) |  | ![&#x6B21;&#x306E;&#x30DA;&#x30FC;&#x30B8;](https://github.com/XoopsDocs/xoonips-developerguide/tree/a6a58e91b3c2fbad05284b6a55d66570e12e94d6/en/book/assets/commonlib/next.gif) |
| :--- | :---: | :--- |


## 第8章 Rights <a id="8-rights"></a>

Rightsを取り扱います．Creative Commonsのライセンスまたは章 7. _TextFile_同様の長文を設定可能です．

## 1. array xnpGetRightsDetailBlock\( int item\_id, int use\_cc=1, string text='', int cc\_commercial\_use=1, int cc\_modification=2 \) <a id="1-array-xnpgetrightsdetailblock-int-item-id-int-use-cc-1-string-text-int-cc-commercial-use-1-int-cc-modification-2"></a>

### 1.1. 入力 <a id="1-1"></a>

* use\_cc : Some rights reservedを選択なら1，そうでないなら0
* text : urlencodeされたLicense Text
* cc\_commercial\_use : 営利目的利用を許すなら1, そうでないなら0
* cc\_modification : 翻案・改変を許すなら2, 条件付で許すなら1, そうでないなら0

### 1.2. 内部で参照する $\_POST 変数 <a id="1-2-post"></a>

なし

### 1.3. 画面 <a id="1-3"></a>

Some rights reservedを選択した場合は以下のように表示されます．

> ![](https://github.com/XoopsDocs/xoonips-developerguide/tree/a6a58e91b3c2fbad05284b6a55d66570e12e94d6/en/book/assets/commonlib/xnpGetRightsDetailBlock.gif)

All rights reservedを選択した場合は、項1. 「array xnpGetTextFileDetailBlock\( int item\_id, string name, string text \)」 と同じです

### 1.4. 送信データ <a id="1-4"></a>

なし

## 2. array xnpGetRightsEditBlock\( int item\_id, int use\_cc=1, string text='', int cc\_commercial\_use=1, int cc\_modification=2 \) <a id="2-array-xnpgetrightseditblock-int-item-id-int-use-cc-1-string-text-int-cc-commercial-use-1-int-cc-modification-2"></a>

### 2.1. 入力 <a id="2-1"></a>

* use\_cc : Some rights reservedを選択なら1，そうでないなら0
* text : urlencodeされたLicense Text
* cc\_commercial\_use : 営利目的利用を許すなら1, そうでないなら0
* cc\_modification : 翻案・改変を許すなら2, 条件付で許すなら1, そうでないなら0

※ $\_POST\["rightsUseCC"\]があれば，これらの引数は全て無視されて以下の$\_POST変数が使用されます．

### 2.2. 内部で参照する $\_POST 変数 <a id="2-2-post"></a>

* $\_POST\["rightsUseCC"\] = Some rights reservedを選択なら1，そうでないなら0．
* $\_POST\["rightsEncText"\] = urlencodeされたLicense Text
* $\_POST\["rightsCCCommercialUse"\] = 営利目的利用を許すなら1, そうでないなら0
* $\_POST\["rightsCCModification"\] = 翻案・改変を許すなら2, 条件付で許すなら1, そうでないなら0

### 2.3. 画面 <a id="2-3"></a>

> ![](https://github.com/XoopsDocs/xoonips-developerguide/tree/a6a58e91b3c2fbad05284b6a55d66570e12e94d6/en/book/assets/commonlib/xnpGetRightsEditBlock1.gif)

### 2.4. 送信データ <a id="2-4"></a>

Submit ボタン → 確認画面へ

* $\_POST\["rightsEncText"\]
* $\_POST\["rightsUseCC"\]
* $\_POST\["rightsCCCommercialUse"\]
* $\_POST\["rightsCCModification"\]

## 3. array xnpGetRightsConfirmBlock\( int item\_id, int maxlen=65535 \) <a id="3-array-xnpgetrightsconfirmblock-int-item-id-int-maxlen-65535"></a>

Confirm 画面用の HTML を生成する．

### 3.1. 内部で参照する $\_POST 変数 <a id="3-1-post"></a>

* $\_POST\["rightsEncText"\]
* $\_POST\["rightsUseCC"\]
* $\_POST\["rightsCCCommercialUse"\]
* $\_POST\["rightsCCModification"\]

### 3.2. 画面 <a id="3-2"></a>

→ 項1. 「array xnpGetRightsDetailBlock\( int item\_id, int use\_cc=1, string text='', int cc\_commercial\_use=1, int cc\_modification=2 \)」 と同じ

### 3.3. 送信データ <a id="3-3"></a>

* $\_POST\["rightsEncText"\]
* $\_POST\["rightsUseCC"\]
* $\_POST\["rightsCCCommercialUse"\]
* $\_POST\["rightsCCModification"\]

### 3.4. 入力 <a id="3-4"></a>

* maxlen : DBのカラムサイズ

## 4. array xnpGetRightsRegisterBlock\( \) <a id="4-array-xnpgetrightsregisterblock"></a>

→ 項2. 「array xnpGetRightsEditBlock\( int item\_id, int use\_cc=1, string text='', int cc\_commercial\_use=1, int cc\_modification=2 \)」 と同じ

## 5. array xnpGetRights\(\) <a id="5-array-xnpgetrights"></a>

Confirm 画面で送信したデータを配列 \( $text, $use\_cc, $cc\_commercial\_use, $cc\_modification \) にして返す．各アイテムタイプモジュールは，この関数で得た文字列を DB に記録する．

| ![&#x524D;&#x306E;&#x30DA;&#x30FC;&#x30B8;](https://github.com/XoopsDocs/xoonips-developerguide/tree/a6a58e91b3c2fbad05284b6a55d66570e12e94d6/en/book/assets/commonlib/prev.gif) |  | ![&#x6B21;&#x306E;&#x30DA;&#x30FC;&#x30B8;](https://github.com/XoopsDocs/xoonips-developerguide/tree/a6a58e91b3c2fbad05284b6a55d66570e12e94d6/en/book/assets/commonlib/next.gif) |
| :--- | :--- | :--- |
|  | ![&#x30DB;&#x30FC;&#x30E0;](https://github.com/XoopsDocs/xoonips-developerguide/tree/a6a58e91b3c2fbad05284b6a55d66570e12e94d6/en/book/assets/commonlib/home.gif) |  |

Last updated: 2010/04/15

