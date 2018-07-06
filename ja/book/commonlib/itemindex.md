# itemindex {#itemindex}

## 第4章 Index {#4-index}

## 1\. array xnpGetIndexDetailBlock( int item_id, bool button_flag = true ) {#1-array-xnpgetindexdetailblock-int-item-id-bool-button-flag-true}

アイテム詳細画面の Index 欄に表示するフォームを生成する．

### 1.1\. 内部で参照する $_POST 変数 {#1-1-post}

なし

### 1.2\. 画面 {#1-2}

> ![](../../assets/commonlib/xnpGetIndexDetailBlock.gif)

※ インデックスの右側のボタン，表示は閲覧者ごとに以下の様に場合分けされる (図は Reject ボタン の例)．

* モデレータ

 * 承認済みの Public インデックス，Group インデックス

 * Reject ボタンを表示

 * 承認待ちの Public インデックス，Group インデックス

 * Accetpt ボタンを表示

 * Reject ボタンを表示

* 承認権限を持つグループ管理者

 * 承認済みの Group インデックス

 * Reject ボタンを表示

 * 承認待ちの Public インデックス

 * 文字列 &#039;(Pending)&#039;を表示

 * 承認待ちの Group インデックス

 * Accept ボタンを表示

 * Reject ボタンを表示

 * 承認権限を持たないグループ管理者

 * 承認待ちのインデックス

 * 文字列 &#039;(Pending)&#039; を表示

 * アイテム作成者

 * 承認待ちの Public インデックス，Group インデックス

 * 文字列 &#039;(Pending)&#039; を表示

 * 上記以外のユーザ，ゲスト

 * 承認待ちの Public インデックス，Group インデックス

 * 文字列 &#039;(Pending)&#039;を表示

※ 各ボタンの働きは以下の通り

* Reject ボタン，Withdraw ボタン

 * 承認待ち状態を未承認へ変更する．

 * 二つのボタンはラベルが異なるだけで働きは同じ．

* Accept ボタン

 * 承認待ち状態を承認済みへ変更する．

※ インデックスキーワードをクリックすると，そのキーワードに属するアイテムの一覧を表示する．

### 1.3\. 送信データ {#1-3}

* Reject ボタン，Withdraw ボタン

 * フォーム (name = &#039;cancel_certify&#039;) に以下のパラメータをセットして submit する

 * index_id = 承認を取り消すインデックスの ID

 * item_id = 承認を取り消すアイテムの ID

 * op = &#039;cancel_certify&#039;

* Accept ボタン

 * フォーム (name = &#039;accept_certify&#039;) に以下のパラメータをセットして submit する

 * index_id = 承認するインデックスのID

 * item_id = 承認するアイテムのID

 * op = &#039;accept_certify&#039;

* ボタンに共通する事柄

 * ボタン押下時に JavaScript のダイアログで OK/Cancel を問い合わせる．

 * フォームは `detail.php` の Smarty テンプレートに定義する．

## 2\. array xnpGetIndexEditBlock( int item_id ) {#2-array-xnpgetindexeditblock-int-item-id}

アイテム編集画面の Index 欄に表示するフォームを生成します．

### 2.1\. 内部で参照する $_POST 変数 {#2-1-post}

* $_POST[&#039;xnpindexCheckedXID&#039;]

### 2.2\. 画面 {#2-2}

$_POST[&#039;xnpindexCheckedXID&#039;] に指定されたインデックスキーワードを以下の様に表示します．

> ![](../../assets/commonlib/xnpGetIndexEditBlock.gif)

### 2.3\. 送信データ {#2-3}

なし

## 3\. array xnpGetIndexConfirmBlock( int item_id ) {#3-array-xnpgetindexconfirmblock-int-item-id}

登録確認画面，編集確認画面の Index 欄のフォームを生成します．

### 3.1\. 内部で参照する $_POST 変数 {#3-1-post}

* $_POST[&#039;xnpindexCheckedXID&#039;]

### 3.2\. 画面 {#3-2}

$_POST[&#039;xnpindexCheckedXID&#039;] に指定されたインデックスキーワードを以下の様に表示します．

> ![](../../assets/commonlib/xnpGetIndexConfirmBlock.gif)

### 3.3\. 送信データ {#3-3}

なし

## 4\. array xnpGetIndexRegisterBlock() {#4-array-xnpgetindexregisterblock}

アイテム登録画面の Index 欄に表示するフォームを生成します．

### 4.1\. 内部で参照する $_POST 変数 {#4-1-post}

* $_POST[&#039;xnpindexCheckedXID&#039;]

### 4.2\. 画面 {#4-2}

$_POST[&#039;xnpindexCheckedXID&#039;] に指定されたインデックスキーワードを以下の様に表示します．

> ![](../../assets/commonlib/xnpGetIndexRegisterBlock.gif)

### 4.3\. 送信データ {#4-3}

なし

## 5\. xnpInsertIndex : (無し) {#5-xnpinsertindex}

代わりに 項6\. 「bool xnpUpdateIndex( int item_id )」 を使用してください．

## 6\. bool xnpUpdateIndex( int item_id ) {#6-bool-xnpupdateindex-int-item-id}

引数 item_id で指定されるアイテムを，選択されたインデックスに登録します．選択を解除されたインデックスから登録を抹消します．

グループ管理者，モデレータの承認が必要な設定であれば，インデックスに対応する管理者のメールアドレスに承認要求メールを送信します．

### 6.1\. 内部で参照する $_POST 変数 {#6-1-post}

選択されたインデックスキーワードを以下の変数から取得します．

* $_POST[&#039;xnpindexCheckedXID&#039;]

## 7\. xnpDeleteIndex : (無し) {#7-xnpdeleteindex}

項9\. 「bool xnpDeleteBasicInformation( int item_id )」 が Index の削除を行うので，この関数はありません．












<?xml version="1.0" encoding="UTF-8" standalone="no"?>

<!DOCTYPE html PUBLIC "-//W3C//DTD XHTML 1.0 Transitional//EN" "http://www.w3.org/TR/xhtml1/DTD/xhtml1-transitional.dtd">

<html xmlns="http://www.w3.org/1999/xhtml">

 <head xmlns="http://www.w3.org/1999/xhtml">

 <meta http-equiv="Content-Type" content="text/html; charset=UTF-8" />

 <title>第4章 Index</title>

 <link rel="stylesheet" href="style.css" type="text/css" />

 <meta name="generator" content="DocBook XSL Stylesheets V1.72.0" />

 <link rel="start" href="index.html" title="XooNIps" />

 <link rel="up" href="index.html" title="XooNIps" />

 <link rel="prev" href="basicinfo.html" title="第3章 Basic Information" />

 <link rel="next" href="preview.html" title="第5章 Preview" />

 </head>

 <body>

 <div id="page">

 <div xmlns="http://www.w3.org/1999/xhtml" class="navheader">

 <table width="100%" summary="Navigation header">

 <tr>

 <td width="20%" align="left"><a accesskey="p" href="basicinfo.html"><img src="images\prev.gif" alt="前のページ" /></a> </td>

 <th width="60%" align="center"> </th>

 <td width="20%" align="right"> <a accesskey="n" href="preview.html"><img src="images\next.gif" alt="次のページ" /></a></td>

 </tr>

 </table>

 <hr />

 </div>

 <div xmlns="http://www.w3.org/1999/xhtml" class="chapter" lang="ja" id="itemindex" xml:lang="ja">

 <div xmlns="" class="titlepage">

 <div>

 <div>

 <h2 xmlns="http://www.w3.org/1999/xhtml" class="title"><a id="itemindex"></a>第4章 Index</h2>

 </div>

 </div>

 </div>

 <div class="section" lang="ja" xml:lang="ja">

 <div xmlns="" class="titlepage">

 <div>

 <div>

 <h2 xmlns="http://www.w3.org/1999/xhtml" class="title" style="clear: both"><a id="func-xnpGetIndexDetailBlock"></a>1. array xnpGetIndexDetailBlock( int item_id, bool button_flag = true )</h2>

 </div>

 </div>

 </div>

 <p>アイテム詳細画面の Index 欄に表示するフォームを生成する．</p>

 <div class="section" lang="ja" xml:lang="ja">

 <div xmlns="" class="titlepage">

 <div>

 <div>

 <h3 xmlns="http://www.w3.org/1999/xhtml" class="title"><a id="func-xnpGetIndexDetailBlock-postvar"></a>1.1. 内部で参照する $_POST 変数</h3>

 </div>

 </div>

 </div>

 <p>なし</p>

 </div>

 <div class="section" lang="ja" xml:lang="ja">

 <div xmlns="" class="titlepage">

 <div>

 <div>

 <h3 xmlns="http://www.w3.org/1999/xhtml" class="title"><a id="func-xnpGetIndexDetailBlock-view"></a>1.2. 画面</h3>

 </div>

 </div>

 </div>

 <div class="blockquote">

 <blockquote class="blockquote">

 <div class="informalfigure">

 <div class="mediaobject">

 <img src="images\xnpGetIndexDetailBlock.gif" />

 </div>

 </div>

 </blockquote>

 </div>

 <p>※ インデックスの右側のボタン，表示は閲覧者ごとに以下の様に場合分けされる (図は Reject ボタン の例)．</p>

 <div class="itemizedlist">

 <ul type="disc">

 <li>

 <p>モデレータ</p>

 <div class="itemizedlist">

 <ul type="circle">

 <li>

 <p>承認済みの Public インデックス，Group インデックス</p>

 <div class="itemizedlist">

 <ul type="square">

 <li>

 <p>Reject ボタンを表示</p>

 </li>

 </ul>

 </div>

 </li>

 <li>

 <p>承認待ちの Public インデックス，Group インデックス</p>

 <div class="itemizedlist">

 <ul type="square">

 <li>

 <p>Accetpt ボタンを表示</p>

 </li>

 <li>

 <p>Reject ボタンを表示</p>

 </li>

 </ul>

 </div>

 </li>

 </ul>

 </div>

 </li>

 <li>

 <p>承認権限を持つグループ管理者</p>

 <div class="itemizedlist">

 <ul type="circle">

 <li>

 <p>承認済みの Group インデックス</p>

 <div class="itemizedlist">

 <ul type="square">

 <li>

 <p>Reject ボタンを表示</p>

 </li>

 </ul>

 </div>

 </li>

 <li>

 <p>承認待ちの Public インデックス</p>

 <div class="itemizedlist">

 <ul type="square">

 <li>

 <p>文字列 '(Pending)'を表示</p>

 </li>

 </ul>

 </div>

 </li>

 <li>

 <p>承認待ちの Group インデックス</p>

 <div class="itemizedlist">

 <ul type="square">

 <li>

 <p>Accept ボタンを表示</p>

 </li>

 <li>

 <p>Reject ボタンを表示</p>

 </li>

 </ul>

 </div>

 </li>

 <li>

 <p>承認権限を持たないグループ管理者</p>

 <div class="itemizedlist">

 <ul type="square">

 <li>

 <p>承認待ちのインデックス</p>

 <div class="itemizedlist">

 <ul type="disc">

 <li>

 <p>文字列 '(Pending)' を表示</p>

 </li>

 </ul>

 </div>

 </li>

 </ul>

 </div>

 </li>

 <li>

 <p>アイテム作成者</p>

 <div class="itemizedlist">

 <ul type="square">

 <li>

 <p>承認待ちの Public インデックス，Group インデックス</p>

 <div class="itemizedlist">

 <ul type="disc">

 <li>

 <p>文字列 '(Pending)' を表示</p>

 </li>

 </ul>

 </div>

 </li>

 </ul>

 </div>

 </li>

 <li>

 <p>上記以外のユーザ，ゲスト</p>

 <div class="itemizedlist">

 <ul type="square">

 <li>

 <p>承認待ちの Public インデックス，Group インデックス</p>

 <div class="itemizedlist">

 <ul type="disc">

 <li>

 <p>文字列 '(Pending)'を表示</p>

 </li>

 </ul>

 </div>

 </li>

 </ul>

 </div>

 </li>

 </ul>

 </div>

 </li>

 </ul>

 </div>

 <p>※ 各ボタンの働きは以下の通り</p>

 <div class="itemizedlist">

 <ul type="disc">

 <li>

 <p>Reject ボタン，Withdraw ボタン</p>

 <div class="itemizedlist">

 <ul type="circle">

 <li>

 <p>承認待ち状態を未承認へ変更する．</p>

 </li>

 <li>

 <p>二つのボタンはラベルが異なるだけで働きは同じ．</p>

 </li>

 </ul>

 </div>

 </li>

 <li>

 <p>Accept ボタン</p>

 <div class="itemizedlist">

 <ul type="circle">

 <li>

 <p>承認待ち状態を承認済みへ変更する．</p>

 </li>

 </ul>

 </div>

 </li>

 </ul>

 </div>

 <p>※ インデックスキーワードをクリックすると，そのキーワードに属するアイテムの一覧を表示する．</p>

 </div>

 <div class="section" lang="ja" xml:lang="ja">

 <div xmlns="" class="titlepage">

 <div>

 <div>

 <h3 xmlns="http://www.w3.org/1999/xhtml" class="title"><a id="func-xnpGetIndexDetailBlock-putvar"></a>1.3. 送信データ</h3>

 </div>

 </div>

 </div>

 <div class="itemizedlist">

 <ul type="disc">

 <li>

 <p>Reject ボタン，Withdraw ボタン</p>

 <div class="itemizedlist">

 <ul type="circle">

 <li>

 <p>フォーム (name = 'cancel_certify') に以下のパラメータをセットして submit する</p>

 <div class="itemizedlist">

 <ul type="square">

 <li>

 <p>index_id = 承認を取り消すインデックスの ID</p>

 </li>

 <li>

 <p>item_id = 承認を取り消すアイテムの ID</p>

 </li>

 <li>

 <p>op = 'cancel_certify'</p>

 </li>

 </ul>

 </div>

 </li>

 </ul>

 </div>

 </li>

 <li>

 <p>Accept ボタン</p>

 <div class="itemizedlist">

 <ul type="circle">

 <li>

 <p>フォーム (name = 'accept_certify') に以下のパラメータをセットして submit する</p>

 <div class="itemizedlist">

 <ul type="square">

 <li>

 <p>index_id = 承認するインデックスのID</p>

 </li>

 <li>

 <p>item_id = 承認するアイテムのID</p>

 </li>

 <li>

 <p>op = 'accept_certify'</p>

 </li>

 </ul>

 </div>

 </li>

 </ul>

 </div>

 </li>

 <li>

 <p>ボタンに共通する事柄</p>

 <div class="itemizedlist">

 <ul type="circle">

 <li>

 <p>ボタン押下時に JavaScript のダイアログで OK/Cancel を問い合わせる．</p>

 </li>

 <li>

 <p>フォームは <code class="filename">detail.php</code> の Smarty テンプレートに定義する．</p>

 </li>

 </ul>

 </div>

 </li>

 </ul>

 </div>

 </div>

 </div>

 <div class="section" lang="ja" xml:lang="ja">

 <div xmlns="" class="titlepage">

 <div>

 <div>

 <h2 xmlns="http://www.w3.org/1999/xhtml" class="title" style="clear: both"><a id="func-xnpGetIndexEditBlock"></a>2. array xnpGetIndexEditBlock( int item_id )</h2>

 </div>

 </div>

 </div>

 <p>アイテム編集画面の Index 欄に表示するフォームを生成します．</p>

 <div class="section" lang="ja" xml:lang="ja">

 <div xmlns="" class="titlepage">

 <div>

 <div>

 <h3 xmlns="http://www.w3.org/1999/xhtml" class="title"><a id="func-xnpGetIndexEditBlock-postvar"></a>2.1. 内部で参照する $_POST 変数</h3>

 </div>

 </div>

 </div>

 <div class="itemizedlist">

 <ul type="disc">

 <li>

 <p>$_POST['xnpindexCheckedXID']</p>

 </li>

 </ul>

 </div>

 </div>

 <div class="section" lang="ja" xml:lang="ja">

 <div xmlns="" class="titlepage">

 <div>

 <div>

 <h3 xmlns="http://www.w3.org/1999/xhtml" class="title"><a id="func-xnpGetIndexEditBlock-view"></a>2.2. 画面</h3>

 </div>

 </div>

 </div>

 <p>$_POST['xnpindexCheckedXID'] に指定されたインデックスキーワードを以下の様に表示します．</p>

 <div class="blockquote">

 <blockquote class="blockquote">

 <div class="informalfigure">

 <div class="mediaobject">

 <img src="images\xnpGetIndexEditBlock.gif" />

 </div>

 </div>

 </blockquote>

 </div>

 </div>

 <div class="section" lang="ja" xml:lang="ja">

 <div xmlns="" class="titlepage">

 <div>

 <div>

 <h3 xmlns="http://www.w3.org/1999/xhtml" class="title"><a id="func-xnpGetIndexEditBlock-putvar"></a>2.3. 送信データ</h3>

 </div>

 </div>

 </div>

 <p>なし</p>

 </div>

 </div>

 <div class="section" lang="ja" xml:lang="ja">

 <div xmlns="" class="titlepage">

 <div>

 <div>

 <h2 xmlns="http://www.w3.org/1999/xhtml" class="title" style="clear: both"><a id="func-xnpGetIndexConfirmBlock"></a>3. array xnpGetIndexConfirmBlock( int item_id )</h2>

 </div>

 </div>

 </div>

 <p>登録確認画面，編集確認画面の Index 欄のフォームを生成します．</p>

 <div class="section" lang="ja" xml:lang="ja">

 <div xmlns="" class="titlepage">

 <div>

 <div>

 <h3 xmlns="http://www.w3.org/1999/xhtml" class="title"><a id="func-xnpGetIndexConfirmBlock-postvar"></a>3.1. 内部で参照する $_POST 変数</h3>

 </div>

 </div>

 </div>

 <div class="itemizedlist">

 <ul type="disc">

 <li>

 <p>$_POST['xnpindexCheckedXID']</p>

 </li>

 </ul>

 </div>

 </div>

 <div class="section" lang="ja" xml:lang="ja">

 <div xmlns="" class="titlepage">

 <div>

 <div>

 <h3 xmlns="http://www.w3.org/1999/xhtml" class="title"><a id="func-xnpGetIndexConfirmBlock-view"></a>3.2. 画面</h3>

 </div>

 </div>

 </div>

 <p>$_POST['xnpindexCheckedXID'] に指定されたインデックスキーワードを以下の様に表示します．</p>

 <div class="blockquote">

 <blockquote class="blockquote">

 <div class="informalfigure">

 <div class="mediaobject">

 <img src="images\xnpGetIndexConfirmBlock.gif" />

 </div>

 </div>

 </blockquote>

 </div>

 </div>

 <div class="section" lang="ja" xml:lang="ja">

 <div xmlns="" class="titlepage">

 <div>

 <div>

 <h3 xmlns="http://www.w3.org/1999/xhtml" class="title"><a id="func-xnpGetIndexConfirmBlock-putvar"></a>3.3. 送信データ</h3>

 </div>

 </div>

 </div>

 <p>なし</p>

 </div>

 </div>

 <div class="section" lang="ja" xml:lang="ja">

 <div xmlns="" class="titlepage">

 <div>

 <div>

 <h2 xmlns="http://www.w3.org/1999/xhtml" class="title" style="clear: both"><a id="func-xnpGetIndexRegisterBlock"></a>4. array xnpGetIndexRegisterBlock()</h2>

 </div>

 </div>

 </div>

 <p>アイテム登録画面の Index 欄に表示するフォームを生成します．</p>

 <div class="section" lang="ja" xml:lang="ja">

 <div xmlns="" class="titlepage">

 <div>

 <div>

 <h3 xmlns="http://www.w3.org/1999/xhtml" class="title"><a id="func-xnpGetIndexRegisterBlock-postvar"></a>4.1. 内部で参照する $_POST 変数</h3>

 </div>

 </div>

 </div>

 <div class="itemizedlist">

 <ul type="disc">

 <li>

 <p>$_POST['xnpindexCheckedXID']</p>

 </li>

 </ul>

 </div>

 </div>

 <div class="section" lang="ja" xml:lang="ja">

 <div xmlns="" class="titlepage">

 <div>

 <div>

 <h3 xmlns="http://www.w3.org/1999/xhtml" class="title"><a id="func-xnpGetIndexRegisterBlock-view"></a>4.2. 画面</h3>

 </div>

 </div>

 </div>

 <p>$_POST['xnpindexCheckedXID'] に指定されたインデックスキーワードを以下の様に表示します．</p>

 <div class="blockquote">

 <blockquote class="blockquote">

 <div class="informalfigure">

 <div class="mediaobject">

 <img src="images\xnpGetIndexRegisterBlock.gif" />

 </div>

 </div>

 </blockquote>

 </div>

 </div>

 <div class="section" lang="ja" xml:lang="ja">

 <div xmlns="" class="titlepage">

 <div>

 <div>

 <h3 xmlns="http://www.w3.org/1999/xhtml" class="title"><a id="func-xnpGetIndexRegisterBlock-putvar"></a>4.3. 送信データ</h3>

 </div>

 </div>

 </div>

 <p>なし</p>

 </div>

 </div>

 <div class="section" lang="ja" xml:lang="ja">

 <div xmlns="" class="titlepage">

 <div>

 <div>

 <h2 xmlns="http://www.w3.org/1999/xhtml" class="title" style="clear: both"><a id="func-xnpInsertIndex"></a>5. xnpInsertIndex : (無し)</h2>

 </div>

 </div>

 </div>

 <p>代わりに <a href="itemindex.html#func-xnpUpdateIndex" title="6. bool xnpUpdateIndex( int item_id )">項6. 「bool xnpUpdateIndex( int item_id )」</a> を使用してください．</p>

 </div>

 <div class="section" lang="ja" xml:lang="ja">

 <div xmlns="" class="titlepage">

 <div>

 <div>

 <h2 xmlns="http://www.w3.org/1999/xhtml" class="title" style="clear: both"><a id="func-xnpUpdateIndex"></a>6. bool xnpUpdateIndex( int item_id )</h2>

 </div>

 </div>

 </div>

 <p>引数 item_id で指定されるアイテムを，選択されたインデックスに登録します．選択を解除されたインデックスから登録を抹消します．</p>

 <p>グループ管理者，モデレータの承認が必要な設定であれば，インデックスに対応する管理者のメールアドレスに承認要求メールを送信します．</p>

 <div class="section" lang="ja" xml:lang="ja">

 <div xmlns="" class="titlepage">

 <div>

 <div>

 <h3 xmlns="http://www.w3.org/1999/xhtml" class="title"><a id="func-xnpUpdateIndex-postvar"></a>6.1. 内部で参照する $_POST 変数</h3>

 </div>

 </div>

 </div>

 <p>選択されたインデックスキーワードを以下の変数から取得します．</p>

 <div class="itemizedlist">

 <ul type="disc">

 <li>

 <p>$_POST['xnpindexCheckedXID']</p>

 </li>

 </ul>

 </div>

 </div>

 </div>

 <div class="section" lang="ja" xml:lang="ja">

 <div xmlns="" class="titlepage">

 <div>

 <div>

 <h2 xmlns="http://www.w3.org/1999/xhtml" class="title" style="clear: both"><a id="func-xnpDeleteIndex"></a>7. xnpDeleteIndex : (無し)</h2>

 </div>

 </div>

 </div>

 <p><a href="basicinfo.html#func-xnpDeleteBasicInformation" title="9. bool xnpDeleteBasicInformation( int item_id )">項9. 「bool xnpDeleteBasicInformation( int item_id )」</a> が Index の削除を行うので，この関数はありません．</p>

 </div>

 </div>

 <div xmlns="http://www.w3.org/1999/xhtml" class="navfooter">

 <hr />

 <table width="100%" summary="Navigation footer">

 <tr>

 <td width="40%" align="left"><a accesskey="p" href="basicinfo.html"><img src="images\prev.gif" alt="前のページ" /></a> </td>

 <td width="20%" align="center"> </td>

 <td width="40%" align="right"> <a accesskey="n" href="preview.html"><img src="images\next.gif" alt="次のページ" /></a></td>

 </tr>

 <tr>

 <td width="40%" align="left" valign="top"> </td>

 <td width="20%" align="center">

 <a accesskey="h" href="index.html">

 <img src="images\home.gif" alt="ホーム" />

 </a>

 </td>

 <td width="40%" align="right" valign="top"> </td>

 </tr>

 </table>

 </div>

 <div class="lastupdated">Last updated: 2010/04/15</div>

 </div>

 </body>

</html>



