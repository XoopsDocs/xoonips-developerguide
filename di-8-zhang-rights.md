---
description: Rightsを取り扱います．Creative Commonsのライセンスまたは章 7. TextFile同様の長文を設定可能です．
---

# 第8章 Rights

### 1. array xnpGetRightsDetailBlock\( int item\_id, int use\_cc=1, string text='', int cc\_commercial\_use=1, int cc\_modification=2 \)

#### 1.1. 入力

* use\_cc : Some rights reservedを選択なら1，そうでないなら0
* text : urlencodeされたLicense Text
* cc\_commercial\_use : 営利目的利用を許すなら1, そうでないなら0
* cc\_modification : 翻案・改変を許すなら2, 条件付で許すなら1, そうでないなら0

#### 1.2. 内部で参照する $\_POST 変数

なし

#### 1.3. 画面

Some rights reservedを選択した場合は以下のように表示されます．

> ![](https://xoonips.osdn.jp/manuals/commonlib-340/images/xnpGetRightsDetailBlock.gif)

All rights reservedを選択した場合は、[項1. 「array xnpGetTextFileDetailBlock\( int item\_id, string name, string text \)」](https://xoonips.osdn.jp/manuals/commonlib-340/textfile.html#func-xnpGetTextFileDetailBlock) と同じです

#### 1.4. 送信データ

なし

### 2. array xnpGetRightsEditBlock\( int item\_id, int use\_cc=1, string text='', int cc\_commercial\_use=1, int cc\_modification=2 \)

#### 2.1. 入力

* use\_cc : Some rights reservedを選択なら1，そうでないなら0
* text : urlencodeされたLicense Text
* cc\_commercial\_use : 営利目的利用を許すなら1, そうでないなら0
* cc\_modification : 翻案・改変を許すなら2, 条件付で許すなら1, そうでないなら0

※ $\_POST\["rightsUseCC"\]があれば，これらの引数は全て無視されて以下の$\_POST変数が使用されます．

#### 2.2. 内部で参照する $\_POST 変数

* $\_POST\["rightsUseCC"\] = Some rights reservedを選択なら1，そうでないなら0．
* $\_POST\["rightsEncText"\] = urlencodeされたLicense Text
* $\_POST\["rightsCCCommercialUse"\] = 営利目的利用を許すなら1, そうでないなら0
* $\_POST\["rightsCCModification"\] = 翻案・改変を許すなら2, 条件付で許すなら1, そうでないなら0

#### 2.3. 画面

> ![](https://xoonips.osdn.jp/manuals/commonlib-340/images/xnpGetRightsEditBlock1.gif)

#### 2.4. 送信データ

Submit ボタン → 確認画面へ

* $\_POST\["rightsEncText"\]
* $\_POST\["rightsUseCC"\]
* $\_POST\["rightsCCCommercialUse"\]
* $\_POST\["rightsCCModification"\]

### 3. array xnpGetRightsConfirmBlock\( int item\_id, int maxlen=65535 \)

Confirm 画面用の HTML を生成する．

#### 3.1. 内部で参照する $\_POST 変数

* $\_POST\["rightsEncText"\]
* $\_POST\["rightsUseCC"\]
* $\_POST\["rightsCCCommercialUse"\]
* $\_POST\["rightsCCModification"\]

#### 3.2. 画面

→ [項1. 「array xnpGetRightsDetailBlock\( int item\_id, int use\_cc=1, string text='', int cc\_commercial\_use=1, int cc\_modification=2 \)」](https://xoonips.osdn.jp/manuals/commonlib-340/rights.html#func-xnpGetRightsDetailBlock) と同じ

#### 3.3. 送信データ

* $\_POST\["rightsEncText"\]
* $\_POST\["rightsUseCC"\]
* $\_POST\["rightsCCCommercialUse"\]
* $\_POST\["rightsCCModification"\]

#### 3.4. 入力

* maxlen : DBのカラムサイズ

### 4. array xnpGetRightsRegisterBlock\( \)

→ [項2. 「array xnpGetRightsEditBlock\( int item\_id, int use\_cc=1, string text='', int cc\_commercial\_use=1, int cc\_modification=2 \)」](https://xoonips.osdn.jp/manuals/commonlib-340/rights.html#func-xnpGetRightsEditBlock) と同じ

### 5. array xnpGetRights\(\)

Confirm 画面で送信したデータを配列 \( $text, $use\_cc, $cc\_commercial\_use, $cc\_modification \) にして返す．各アイテムタイプモジュールは，この関数で得た文字列を DB に記録する．

