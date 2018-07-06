# basicinfo {#basicinfo}

## 第3章 Basic Information {#3-basic-information}

## 1\. Basic Informationのデータ構造 {#1-basic-information}

アイテムの Basic Information のフォームを生成します．戻り値の構造は以下の通りです．フォームの一部を構成する HTML が格納されます．

<pre class="programlisting">array $basic;$basic[&#039;title&#039;] タイトル$basic[&#039;contributor&#039;] アイテム作成者名$basic[&#039;keywords&#039;] キーワード$basic[&#039;description&#039;] コメント$basic[&#039;doi&#039;] DOI$basic[&#039;last_update_date&#039;] 最終更新日$basic[&#039;creation_date&#039;] アイテム作成日$basic[&#039;item_type&#039;] アイテムタイプ名$basic[&#039;change_logs&#039;] これまでの変更履歴$basic[&#039;change_log&#039;] 変更内容(変更履歴に追加される)$basic[&#039;publication_date&#039;] 年月日 (※)$basic[&#039;publication_year&#039;] 年 (※)$basic[&#039;publication_month&#039;] 月 (※)$basic[&#039;publication_mday&#039;] 日 (※)$basic[&#039;uid&#039;] ユーザID$basic[&#039;related_to&#039;] 関連アイテム$basic[&#039;lang&#039;] 言語  </pre>

(※) publication_dateは，publication_year, publication_month, publication_mdayをあわせたものです．登録，編集なら年月日を一度に設定できます．確認，詳細表示の場合は年月日の文字列です．

## 2\. Basic Informationのフォームデータ構造 {#2-basic-information}

送信されるアイテムの Basic Information フォームデータは以下の構造です．

**表 3.1\. フォームデータ構造**

| 名前 | 内容 | 備考 || :-- | :-- | :-- || item_type_id | アイテムタイプID | || title | タイトル | || keywords | キーワード | || description | コメント | || doi | DOI | || change_log | 変更内容 | 変更履歴に追加される || PublicationDateYear | 年 | || PublicationDateMonth | 月 | || PublicationDateDay | 日 | || lang | 言語 | || related_to | 関連アイテム | || related_to_check | 関連アイテム | || related_to_check_all | 関連アイテム | |

## 3\. array xnpGetBasicInformationDetailBlock( int item_id ) {#3-array-xnpgetbasicinformationdetailblock-int-item-id}

アイテム詳細表示に必要な Basic Information を返します．

### 3.1\. 内部で参照する $_POST 変数 {#3-1-post}

なし

### 3.2\. 画面 {#3-2}

なし

### 3.3\. 送信データ {#3-3}

なし

## 4\. array xnpGetBasicInformationEditBlock( int item_id ) {#4-array-xnpgetbasicinformationeditblock-int-item-id}

アイテム編集画面のフォームを生成します．

### 4.1\. 内部で参照する $_POST 変数 {#4-1-post}

表 3.1\. 「フォームデータ構造」のフォームデータをフォームの初期値に使用します．

### 4.2\. 画面 {#4-2}

なし

### 4.3\. 送信データ {#4-3}

表 3.1\. 「フォームデータ構造」

## 5\. array xnpGetBasicInformationConfirmBlock( int item_id ) {#5-array-xnpgetbasicinformationconfirmblock-int-item-id}

アイテム登録，アイテム編集時の内容確認画面に表示するフォームを生成します．

### 5.1\. 内部で参照する $_POST 変数 {#5-1-post}

表 3.1\. 「フォームデータ構造」のフォームデータを確認画面に表示します．

### 5.2\. 画面 {#5-2}

なし

### 5.3\. 送信データ {#5-3}

なし

## 6\. array xnpGetBasicInformationRegisterBlock() {#6-array-xnpgetbasicinformationregisterblock}

登録画面，編集画面に表示する Basic Information のフォームを作成します．

### 6.1\. 内部で参照する $_POST 変数 {#6-1-post}

表 3.1\. 「フォームデータ構造」の値をフォームの初期値に使用します．

### 6.2\. 画面 {#6-2}

なし

### 6.3\. 送信データ {#6-3}

表 3.1\. 「フォームデータ構造」

## 7\. bool xnpInsertBasicInformation( int &amp;item_id ) {#7-bool-xnpinsertbasicinformation-int-item-id}

Basic Information をデータベースに登録します．アイテムのIDを引数 item_id に代入します．

### 7.1\. 内部で参照する $_POST 変数 {#7-1-post}

表 3.1\. 「フォームデータ構造」の情報をデータベースに記録します．

## 8\. bool xnpUpdateBasicInformation( int item_id ) {#8-bool-xnpupdatebasicinformation-int-item-id}

アイテムの Basic Information を，引数 item_id で指定されたアイテムに上書きします．

### 8.1\. 内部で参照する $_POST 変数 {#8-1-post}

表 3.1\. 「フォームデータ構造」の変数の内容をデータベースに上書きします．

## 9\. bool xnpDeleteBasicInformation( int item_id ) {#9-bool-xnpdeletebasicinformation-int-item-id}

引数 item_id で指定されたアイテムの Basic Information とそのアイテムに関連するファイル(添付ファイル，画像ファイル)を削除します．

成功なら true を返します．
