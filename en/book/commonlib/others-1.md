# others

## 第13章 その他

## 1. double xnpGetTotalFileSize\( array iids \)

iids で指定したアイテムのファイルサイズの合計を返す．

### 1.1. 入力

* iids : item\_id の配列

### 1.2. 戻り値

iids で指定したアイテムのファイルサイズの合計 \(byte\)

## 2. bool xnpIsPending\( int item\_id \)

アイテムが現在 Pending \(承認待ち状態\) であるかを調べ，真偽値を返します．

### 2.1. 入力

* item\_id : 調べる対象のアイテムの ID

### 2.2. 戻り値

* true : 承認待ちのインデックスがある \(Pending中\)
* false : 承認待ちのインデックスはない

## 3. string xnpGetTopBlock\( string moduleName, string displayName, string iconPath, string explanation, string subtypeVarName, array subtypes \)

XooNIpsモジュールトップページに表示するブロックの HTML を返します．

### 3.1. 入力

* moduleName : モジュール名
* displayName : アイテムタイプ表示名
* iconPath : アイテムタイプのアイコン\(XOOPS\_URL/modules/モジュール名/ からの相対パス\)
* explanation : アイテムタイプの説明
* subtypeVarName : 詳細検索時にアイテムサブタイプを指定する変数の変数名．サブタイプが無いときはfalseを指定する．
* subtypes : アイテムサブタイプの連想配列\(key=アイテムサブタイプ名，value=アイテムサブタイプ表示名\)．サブタイプが無いときはfalseを指定する．

### 3.2. 戻り値

トップページに表示するブロックの HTML

### 3.3. 画面

\(省略\)

### 3.4. 送信データ

以下の変数を送信します．

* アイテムタイプ名をクリック → itemselect.phpへ以下を送信する．
  * $\_POST\['op'\] = 'itemtypesearch'
  * $\_POST\['search\_itemtype'\] = \(モジュール名\)
* アイテムサブタイプ名をクリック → itemselect.phpへ以下を送信する．
  * $\_POST\['op'\] = 'itemsubtypesearch'
  * $\_POST\[\(モジュール名\)\] = 'on'
  * $\_POST\[\(詳細検索時にアイテムサブタイプを指定する変数の変数名\)\] = \(アイテムサブタイプ名\)
  * $\_POST\['search\_var\[\]'\] = \(モジュール名\)
  * $\_POST\['search\_var\[\]'\] = \(詳細検索時にアイテムサブタイプを指定する変数の変数名\)

## 4. bool xnpIsAttachmentModified\( string file\_type\_name, int item\_id \)

item\_idで指定されたアイテムの添付ファイルの中で，ファイルタイプ名がfile\_type\_nameに一致するものが変更されているかを調べる．

※アイテム編集内容確認画面以外では正常に動作しない．

### 4.1. 入力

* item\_id : 比較対象のアイテムID
* file\_type\_name : xoonips\_file\_typeテーブルに登録したファイルタイプ名

### 4.2. 戻り値

* true : 変更があった
* false : 変更は無かった

## 5. string xnpISO8601\( int year, int month, int day \)

日付をISO8601の形式でフォーマットする．

### 5.1. 入力

* year : 年．
* month : 月．0なら月日を出力しない．
* day : 日．0なら日を出力しない．

### 5.2. 戻り値

* monthが0なら YYYY 形式の文字列
* monthが非0でdayが0なら YYYY-MM 形式の文字列
* monthもdayも非0なら YYYY-MM-DD 形式の文字列

## 6. string xnpDate\( int year, int month, int day \)

日付をフォーマットする．

### 6.1. 入力

* year : 年．
* month : 月．0なら月日を出力しない．
* day : 日．0なら日を出力しない．

### 6.2. 戻り値

* monthが0なら 年 形式の文字列\(例 : 2006\)
* monthが非0でdayが0なら 月 年 形式の文字列\(例 : Jan 2006\)
* monthもdayも非0なら 月 日,年 形式の文字列\(例 : Jan 1, 2006\)

※ 1970年以前，あるいは2038年以降の日付は正しく出力しない可能性があります．

## 7. bool xnpExportFile\( string export\_path, resource fhdl, int item\_id \)

添付ファイルの情報をエクスポートファイルに出力する．

各アイテムタイプのExportItem関数で，エクスポートファイルに添付ファイルの情報を含めたい場合にこの関数を使用してください．

### 7.1. 入力

* export\_path : 各アイテムタイプのExportItem関数に渡されたexport\_path引数をそのまま渡してください．
* fhdl : 出力先のファイルハンドル
* item\_id : アイテムID．

### 7.2. 戻り値

* true : 成功
* false : 失敗

