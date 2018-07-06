# rights {#rights}

| ![前のページ](../../assets/commonlib/prev.gif)  |   |  ![次のページ](../../assets/commonlib/next.gif) |
| --- | :-: | --- |

## 第8章 Rights {#8-rights}

Rightsを取り扱います．Creative Commonsのライセンスまたは章 7\. _TextFile_同様の長文を設定可能です．

## 1\. array xnpGetRightsDetailBlock( int item_id, int use_cc=1, string text=&#039;&#039;, int cc_commercial_use=1, int cc_modification=2 ) {#1-array-xnpgetrightsdetailblock-int-item-id-int-use-cc-1-string-text-int-cc-commercial-use-1-int-cc-modification-2}

### 1.1\. 入力 {#1-1}

*   use_cc : Some rights reservedを選択なら1，そうでないなら0

*   text : urlencodeされたLicense Text

*   cc_commercial_use : 営利目的利用を許すなら1, そうでないなら0

*   cc_modification : 翻案・改変を許すなら2, 条件付で許すなら1, そうでないなら0

### 1.2\. 内部で参照する $_POST 変数 {#1-2-post}

なし

### 1.3\. 画面 {#1-3}

Some rights reservedを選択した場合は以下のように表示されます．

> ![](../../assets/commonlib/xnpGetRightsDetailBlock.gif)

All rights reservedを選択した場合は、項1\. 「array xnpGetTextFileDetailBlock( int item_id, string name, string text )」 と同じです

### 1.4\. 送信データ {#1-4}

なし

## 2\. array xnpGetRightsEditBlock( int item_id, int use_cc=1, string text=&#039;&#039;, int cc_commercial_use=1, int cc_modification=2 ) {#2-array-xnpgetrightseditblock-int-item-id-int-use-cc-1-string-text-int-cc-commercial-use-1-int-cc-modification-2}

### 2.1\. 入力 {#2-1}

*   use_cc : Some rights reservedを選択なら1，そうでないなら0

*   text : urlencodeされたLicense Text

*   cc_commercial_use : 営利目的利用を許すなら1, そうでないなら0

*   cc_modification : 翻案・改変を許すなら2, 条件付で許すなら1, そうでないなら0

※ $_POST[&quot;rightsUseCC&quot;]があれば，これらの引数は全て無視されて以下の$_POST変数が使用されます．

### 2.2\. 内部で参照する $_POST 変数 {#2-2-post}

*   $_POST[&quot;rightsUseCC&quot;] = Some rights reservedを選択なら1，そうでないなら0．

*   $_POST[&quot;rightsEncText&quot;] = urlencodeされたLicense Text

*   $_POST[&quot;rightsCCCommercialUse&quot;] = 営利目的利用を許すなら1, そうでないなら0

*   $_POST[&quot;rightsCCModification&quot;] = 翻案・改変を許すなら2, 条件付で許すなら1, そうでないなら0

### 2.3\. 画面 {#2-3}

> ![](../../assets/commonlib/xnpGetRightsEditBlock1.gif)

### 2.4\. 送信データ {#2-4}

Submit ボタン → 確認画面へ

*   $_POST[&quot;rightsEncText&quot;]

*   $_POST[&quot;rightsUseCC&quot;]

*   $_POST[&quot;rightsCCCommercialUse&quot;]

*   $_POST[&quot;rightsCCModification&quot;]

## 3\. array xnpGetRightsConfirmBlock( int item_id, int maxlen=65535 ) {#3-array-xnpgetrightsconfirmblock-int-item-id-int-maxlen-65535}

Confirm 画面用の HTML を生成する．

### 3.1\. 内部で参照する $_POST 変数 {#3-1-post}

*   $_POST[&quot;rightsEncText&quot;]

*   $_POST[&quot;rightsUseCC&quot;]

*   $_POST[&quot;rightsCCCommercialUse&quot;]

*   $_POST[&quot;rightsCCModification&quot;]

### 3.2\. 画面 {#3-2}

→ 項1\. 「array xnpGetRightsDetailBlock( int item_id, int use_cc=1, string text=&#039;&#039;, int cc_commercial_use=1, int cc_modification=2 )」 と同じ

### 3.3\. 送信データ {#3-3}

*   $_POST[&quot;rightsEncText&quot;]

*   $_POST[&quot;rightsUseCC&quot;]

*   $_POST[&quot;rightsCCCommercialUse&quot;]

*   $_POST[&quot;rightsCCModification&quot;]

### 3.4\. 入力 {#3-4}

*   maxlen : DBのカラムサイズ

## 4\. array xnpGetRightsRegisterBlock( ) {#4-array-xnpgetrightsregisterblock}

→ 項2\. 「array xnpGetRightsEditBlock( int item_id, int use_cc=1, string text=&#039;&#039;, int cc_commercial_use=1, int cc_modification=2 )」 と同じ

## 5\. array xnpGetRights() {#5-array-xnpgetrights}

Confirm 画面で送信したデータを配列 ( $text, $use_cc, $cc_commercial_use, $cc_modification ) にして返す．各アイテムタイプモジュールは，この関数で得た文字列を DB に記録する．

| ![前のページ](../../assets/commonlib/prev.gif)  |   |  ![次のページ](../../assets/commonlib/next.gif) |
| --- | --- | --- |
|   | ![ホーム](../../assets/commonlib/home.gif)  |   |

Last updated: 2010/04/15