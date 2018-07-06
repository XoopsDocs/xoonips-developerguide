# others {#others}

| ![前のページ](../../assets/commonlib/prev.gif)  |   |  ![次のページ](../../assets/commonlib/next.gif) |
| --- | :-: | --- |

## 第13章 その他 {#13}

## 1\. double xnpGetTotalFileSize( array iids ) {#1-double-xnpgettotalfilesize-array-iids}

iids で指定したアイテムのファイルサイズの合計を返す．

### 1.1\. 入力 {#1-1}

*   iids : item_id の配列

### 1.2\. 戻り値 {#1-2}

iids で指定したアイテムのファイルサイズの合計 (byte)

## 2\. bool xnpIsPending( int item_id ) {#2-bool-xnpispending-int-item-id}

アイテムが現在 Pending (承認待ち状態) であるかを調べ，真偽値を返します．

### 2.1\. 入力 {#2-1}

*   item_id : 調べる対象のアイテムの ID

### 2.2\. 戻り値 {#2-2}

*   true : 承認待ちのインデックスがある (Pending中)

*   false : 承認待ちのインデックスはない

## 3\. string xnpGetTopBlock( string moduleName, string displayName, string iconPath, string explanation, string subtypeVarName, array subtypes ) {#3-string-xnpgettopblock-string-modulename-string-displayname-string-iconpath-string-explanation-string-subtypevarname-array-subtypes}

XooNIpsモジュールトップページに表示するブロックの HTML を返します．

### 3.1\. 入力 {#3-1}

*   moduleName : モジュール名

*   displayName : アイテムタイプ表示名

*   iconPath : アイテムタイプのアイコン(XOOPS_URL/modules/モジュール名/ からの相対パス)

*   explanation : アイテムタイプの説明

*   subtypeVarName : 詳細検索時にアイテムサブタイプを指定する変数の変数名．サブタイプが無いときはfalseを指定する．

*   subtypes : アイテムサブタイプの連想配列(key=アイテムサブタイプ名，value=アイテムサブタイプ表示名)．サブタイプが無いときはfalseを指定する．

### 3.2\. 戻り値 {#3-2}

トップページに表示するブロックの HTML

### 3.3\. 画面 {#3-3}

(省略)

### 3.4\. 送信データ {#3-4}

以下の変数を送信します．

*   アイテムタイプ名をクリック → itemselect.phpへ以下を送信する．

    *   $_POST[&#039;op&#039;] = &#039;itemtypesearch&#039;

    *   $_POST[&#039;search_itemtype&#039;] = (モジュール名)

*   アイテムサブタイプ名をクリック → itemselect.phpへ以下を送信する．

    *   $_POST[&#039;op&#039;] = &#039;itemsubtypesearch&#039;

    *   $_POST[(モジュール名)] = &#039;on&#039;

    *   $_POST[(詳細検索時にアイテムサブタイプを指定する変数の変数名)] = (アイテムサブタイプ名)

    *   $_POST[&#039;search_var[]&#039;] = (モジュール名)

    *   $_POST[&#039;search_var[]&#039;] = (詳細検索時にアイテムサブタイプを指定する変数の変数名)

## 4\. bool xnpIsAttachmentModified( string file_type_name, int item_id ) {#4-bool-xnpisattachmentmodified-string-file-type-name-int-item-id}

item_idで指定されたアイテムの添付ファイルの中で，ファイルタイプ名がfile_type_nameに一致するものが変更されているかを調べる．

※アイテム編集内容確認画面以外では正常に動作しない．

### 4.1\. 入力 {#4-1}

*   item_id : 比較対象のアイテムID

*   file_type_name : xoonips_file_typeテーブルに登録したファイルタイプ名

### 4.2\. 戻り値 {#4-2}

*   true : 変更があった

*   false : 変更は無かった

## 5\. string xnpISO8601( int year, int month, int day ) {#5-string-xnpiso8601-int-year-int-month-int-day}

日付をISO8601の形式でフォーマットする．

### 5.1\. 入力 {#5-1}

*   year : 年．

*   month : 月．0なら月日を出力しない．

*   day : 日．0なら日を出力しない．

### 5.2\. 戻り値 {#5-2}

*   monthが0なら YYYY 形式の文字列

*   monthが非0でdayが0なら YYYY-MM 形式の文字列

*   monthもdayも非0なら YYYY-MM-DD 形式の文字列

## 6\. string xnpDate( int year, int month, int day ) {#6-string-xnpdate-int-year-int-month-int-day}

日付をフォーマットする．

### 6.1\. 入力 {#6-1}

*   year : 年．

*   month : 月．0なら月日を出力しない．

*   day : 日．0なら日を出力しない．

### 6.2\. 戻り値 {#6-2}

*   monthが0なら 年 形式の文字列(例 : 2006)

*   monthが非0でdayが0なら 月 年 形式の文字列(例 : Jan 2006)

*   monthもdayも非0なら 月 日,年 形式の文字列(例 : Jan 1, 2006)

※ 1970年以前，あるいは2038年以降の日付は正しく出力しない可能性があります．

## 7\. bool xnpExportFile( string export_path, resource fhdl, int item_id ) {#7-bool-xnpexportfile-string-export-path-resource-fhdl-int-item-id}

添付ファイルの情報をエクスポートファイルに出力する．

各アイテムタイプのExportItem関数で，エクスポートファイルに添付ファイルの情報を含めたい場合にこの関数を使用してください．

### 7.1\. 入力 {#7-1}

*   export_path : 各アイテムタイプのExportItem関数に渡されたexport_path引数をそのまま渡してください．

*   fhdl : 出力先のファイルハンドル

*   item_id : アイテムID．

### 7.2\. 戻り値 {#7-2}

*   true : 成功

*   false : 失敗

| ![前のページ](../../assets/commonlib/prev.gif)  |   |  ![次のページ](../../assets/commonlib/next.gif) |
| --- | --- | --- |
|   | ![ホーム](../../assets/commonlib/home.gif)  |   |

Last updated: 2010/04/15