

 <body>

 <div id="page">

 <div xmlns="http://www.w3.org/1999/xhtml" class="navheader">

 </div>

 <div xmlns="http://www.w3.org/1999/xhtml" class="chapter" lang="ja" id="edit" xml:lang="ja">

 <div xmlns="" class="titlepage">

 <div>

 <div>

 <h2 xmlns="http://www.w3.org/1999/xhtml" class="title"><a id="edit"></a>第8章 アイテム編集</h2>

 </div>

 </div>

 </div>

 <p>アイテムの内容を更新します．</p>

 <div class="figure">

 <a id="fig.edit.workflow"></a>

 <div class="figure-contents">

 <div class="mediaobject">

 <img src="../../assets/itemtype/edit-flow.gif" alt="アイテム編集の流れ" />

 </div>

 </div>

 <p class="title">

 <b>図 8.1. アイテム編集の流れ</b>

 </p>

 </div>

 <br class="figure-break" />

 <div class="figure">

 <a id="fig.edit.view-parameter"></a>

 <div class="figure-contents">

 <div class="mediaobject">

 <img src="../../assets/itemtype/edit-trans.gif" alt="画面遷移と送信パラメータ" />

 </div>

 </div>

 <p class="title">

 <b>図 8.2. 画面遷移と送信パラメータ</b>

 </p>

 </div>

 <br class="figure-break" />

 <div class="section" lang="ja" xml:lang="ja">

 <div xmlns="" class="titlepage">

 <div>

 <div>

 <h2 xmlns="http://www.w3.org/1999/xhtml" class="title" style="clear: both"><a id="edit.form"></a>1. 編集フォーム要求</h2>

 </div>

 </div>

 </div>

 <p>アイテムタイプモジュールは編集要求を受けて，編集フォームを作成します．編集フォームは HTML の形式で出力します．</p>

 <p>アイテムタイプモジュールの以下の関数に編集フォーム作成処理を定義してください．システムは編集フォームが必要なときこの関数をコールバックします．</p>

 <div class="itemizedlist">

 <ul type="disc">

 <li>

 <p>function &lt;モジュール名&gt;GetEditBlock( )</p>

 <div class="itemizedlist">

 <ul type="circle">

 <li>

 <p>引数 : なし</p>

 </li>

 <li>

 <p>戻り値 : 編集フォームの HTML</p>

 </li>

 </ul>

 </div>

 </li>

 </ul>

 </div>

 <div class="section" lang="ja" xml:lang="ja">

 <div xmlns="" class="titlepage">

 <div>

 <div>

 <h3 xmlns="http://www.w3.org/1999/xhtml" class="title"><a id="edit.form.basic"></a>1.1. Basic Information の編集フォーム作成</h3>

 </div>

 </div>

 </div>

 <p>共通ライブラリの機能を呼び出して，Basic Information の編集フォームを作成します．Basic Information のフィールド毎のフォームが得られるので，その中から必要なフィールドを取り出してフォームを作成します．</p>

 <p>以下の項目も参照してください．</p>

 <div class="itemizedlist">

 <ul type="disc">

 <li>

 <p>xnpGetBasicInformationEditBlock</p>

 </li>

 </ul>

 </div>

 </div>

 <div class="section" lang="ja" xml:lang="ja">

 <div xmlns="" class="titlepage">

 <div>

 <div>

 <h3 xmlns="http://www.w3.org/1999/xhtml" class="title"><a id="edit.form.detail"></a>1.2. Detail Information の編集フォーム作成</h3>

 </div>

 </div>

 </div>

 <p>Detail Information の編集フォームの作成方法は規定しません．出力する HTML がシステムの画面構成や動作を妨げないものであれば，どのように作成しても問題ありません．共通ライブラリに用意された機能を利用して，添付ファイルや画像の編集フォームを生成できます．</p>

 <p>システムから編集対象のアイテム ID (<a href="edit.html#fig.edit.view-parameter" title="図 8.2. 画面遷移と送信パラメータ">図 8.2. 「画面遷移と送信パラメータ」</a> の(1)) を指定されるので，その ID を使って DB に記録された値を取得し編集フォームの初期値に設定します．内容確認画面から編集フォームへ戻ってきた場合(<a href="edit.html#fig.edit.view-parameter" title="図 8.2. 画面遷移と送信パラメータ">図 8.2. 「画面遷移と送信パラメータ」</a> の(3)) は，POST で与えられた情報を優先してフォームの初期値に設定してください POST されない情報は，アイテム ID を使って DB から取得して設定してください．</p>

 <p>以下の項目も参照してください．</p>

 <div class="itemizedlist">

 <ul type="disc">

 <li>

 <p>xnpGetBasicInformationEditBlock</p>

 </li>

 <li>

 <p>xnpGetPreviewEditBlock</p>

 </li>

 <li>

 <p>xnpGetAttachmentEditBlock</p>

 </li>

 <li>

 <p>xnpGetTextFileEditBlock</p>

 </li>

 <li>

 <p>xnpGetRightsFileEditBlock</p>

 </li>

 <li>

 <p>xnpGetIndexEditBlock</p>

 </li>

 <li>

 <p>xnpGetDownloadLimitationOptionEditBlock</p>

 </li>

 <li>

 <p>xnpGetDownloadNotificationOptionEditBlock</p>

 </li>

 </ul>

 </div>

 </div>

 <div class="section" lang="ja" xml:lang="ja">

 <div xmlns="" class="titlepage">

 <div>

 <div>

 <h3 xmlns="http://www.w3.org/1999/xhtml" class="title"><a id="edit.form.paramcheck"></a>1.3. パラメータチェック関数</h3>

 </div>

 </div>

 </div>

 <p>Web ブラウザ上でパラメータチェックを行なうチェック関数を，出力する HTML に定義してください．JavaScript で以下の関数を定義してください．パラメータチェックを行なわない場合も定義が必要です．</p>

 <div class="itemizedlist">

 <ul type="disc">

 <li>

 <p>OnSubmitItemType( form )</p>

 </li>

 <li>

 <p>引数 : form (編集フォームのオブジェクト)</p>

 </li>

 <li>

 <p>戻り値 : true (異常なし)，false (異常あり)</p>

 </li>

 </ul>

 </div>

 <p>フォームの Submit ボタンが押されると，OnSubmitItemType 関数がコールバックされます．アイテムタイプ独自の項目で，パラメータチェックが必要な場合はこの関数内にチェック処理を行ないます．エラーダイアログ表示などはこの関数内で行なってください．最後に，パラメータが正常な場合は true を，異常がある場合は false をかえしてください．パラメータチェックを行なわない場合は常に true をかえす処理を定義してください．</p>

 <p>falseを返した場合，編集内容確認画面へは進みません．</p>

 </div>

 <div class="section" lang="ja" xml:lang="ja">

 <div xmlns="" class="titlepage">

 <div>

 <div>

 <h3 xmlns="http://www.w3.org/1999/xhtml" class="title"><a id="edit.form.reservedparam"></a>1.4. 予約済みパラメータ名</h3>

 </div>

 </div>

 </div>

 <p>システムが編集フォームで使用する (編集フォームから POST で送信する) パラメータの名前 (&lt;input&gt; タグの name 属性) は以下のとおりです．アイテムタイプモジュールが使用するパラメータが以下の名前と重複しないように注意してください．重複を避けるために Detail Information のパラメータ名にはプレフィクスとしてモジュール名を与えるとよいでしょう．</p>

 <div class="itemizedlist">

 <ul type="disc">

 <li>

 <p>mode</p>

 </li>

 <li>

 <p>fileID</p>

 </li>

 <li>

 <p>title</p>

 </li>

 <li>

 <p>keywords</p>

 </li>

 <li>

 <p>description</p>

 </li>

 <li>

 <p>doi</p>

 </li>

 <li>

 <p>change_log</p>

 </li>

 <li>

 <p>publicationDateYear</p>

 </li>

 <li>

 <p>publicationDateMonth</p>

 </li>

 <li>

 <p>publicationDateDay</p>

 </li>

 <li>

 <p>publicationDate</p>

 </li>

 <li>

 <p>item_id</p>

 </li>

 <li>

 <p>lang</p>

 </li>

 <li>

 <p>related_to</p>

 </li>

 <li>

 <p>scrollX</p>

 </li>

 <li>

 <p>scrollY</p>

 </li>

 <li>

 <p>xoonipsCheckedXID</p>

 </li>

 <li>

 <p>jump_to_var[]</p>

 </li>

 </ul>

 </div>

 </div>

 </div>

 <div class="section" lang="ja" xml:lang="ja">

 <div xmlns="" class="titlepage">

 <div>

 <div>

 <h2 xmlns="http://www.w3.org/1999/xhtml" class="title" style="clear: both"><a id="edit.confirm"></a>2. 編集内容確認フォーム要求</h2>

 </div>

 </div>

 </div>

 <p>編集内容を確認するフォームを生成します．HTML で出力します．システムはアイテムタイプに対して以下の処理を行ないます．</p>

 <div class="itemizedlist">

 <ul type="disc">

 <li>

 <p>パラメータチェック関数のコールバック</p>

 </li>

 <li>

 <p>変更フィールドチェック関数のコールバック</p>

 </li>

 <li>

 <p>編集内容確認フォームの要求</p>

 </li>

 </ul>

 </div>

 <p>アイテムタイプモジュールの以下の関数に編集内容確認フォーム作成処理を定義してください．システムは編集内容確認フォームが必要なときこの関数をコールバックします．この関数は登録内容確認画面で使用するものと同じです．</p>

 <div class="itemizedlist">

 <ul type="disc">

 <li>

 <p>function &lt;モジュール名&gt;GetConfirmBlock( $item_id )</p>

 <div class="itemizedlist">

 <ul type="circle">

 <li>

 <p>引数 : $item_id (確認したいアイテムの ID)</p>

 </li>

 <li>

 <p>戻り値 : 内容確認画面のHTML</p>

 </li>

 </ul>

 </div>

 </li>

 </ul>

 </div>

 <div class="section" lang="ja" xml:lang="ja">

 <div xmlns="" class="titlepage">

 <div>

 <div>

 <h3 xmlns="http://www.w3.org/1999/xhtml" class="title"><a id="edit.confirm.callback"></a>2.1. パラメータチェック関数のコールバック</h3>

 </div>

 </div>

 </div>

 <p>アイテムタイプは編集内容をチェックするための PHP 関数を定義します．関数の概要は以下のとおりです．</p>

 <div class="itemizedlist">

 <ul type="disc">

 <li>

 <p>書式 : &lt;モジュール名&gt;CheckEditParameters( &amp;$msg )</p>

 </li>

 <li>

 <p>引数 : $msg (チェックしたパラメータのエラーや警告メッセージを代入する)</p>

 </li>

 <li>

 <p>戻り値 : true (異常なし)，false (異常あり)</p>

 </li>

 </ul>

 </div>

 <p>この関数内で Detail Information のパラメータチェックを行ないます．パラメータに異常があれば，その内容を示すメッセージを $msg 引数に設定し，false を返して関数を終了します．異常が無ければ true を返します．false を返した場合，システムは更新処理実行を禁止します．$msg の内容は編集内容確認画面に出力されます．</p>

 </div>

 <div class="section" lang="ja" xml:lang="ja">

 <div xmlns="" class="titlepage">

 <div>

 <div>

 <h3 xmlns="http://www.w3.org/1999/xhtml" class="title"><a id="edit.confirm.modifedfilds"></a>2.2. 変更フィールドチェック関数のコールバック</h3>

 </div>

 </div>

 </div>

 <p>ChangeLog欄が空白の場合に限りChangeLogを自動的に生成します．アイテムタイプモジュールはXooNIpsの要求に応じて，変更されたDetail Informationのフィールド名を返さなければなりません．</p>

 <div class="itemizedlist">

 <ul type="disc">

 <li>

 <p>書式 : &lt;モジュール名&gt;GetModifiedFields( $item_id )</p>

 </li>

 <li>

 <p>引数 : $item_id(比較対象のアイテムのID)</p>

 </li>

 <li>

 <p>戻り値 : フィールド名の配列</p>

 </li>

 </ul>

 </div>

 <p>DB に記録された Detail Information と， $_POSTで与えられる Detail Information の値の違いを調べ，違いが見付かったフィールドの表示名の配列を戻り値とします．</p>

 </div>

 <div class="section" lang="ja" xml:lang="ja">

 <div xmlns="" class="titlepage">

 <div>

 <div>

 <h3 xmlns="http://www.w3.org/1999/xhtml" class="title"><a id="edit.confirm.basic"></a>2.3. Basic Information の編集内容確認フォーム作成</h3>

 </div>

 </div>

 </div>

 <p>共通ライブラリの機能を呼び出して，Basic Information の編集内容確認フォームを作成します．Basic Information のフィールド毎のフォームが得られるので，その中から必要なフィールドを取り出して組合せ，フォームを作成します．</p>

 <p>以下の項目も参照してください．</p>

 <div class="itemizedlist">

 <ul type="disc">

 <li>

 <p>xnpGetBasicInformationConfirmBlock</p>

 </li>

 </ul>

 </div>

 </div>

 <div class="section" lang="ja" xml:lang="ja">

 <div xmlns="" class="titlepage">

 <div>

 <div>

 <h3 xmlns="http://www.w3.org/1999/xhtml" class="title"><a id="edit.confirm.detail"></a>2.4. Detail Information の編集内容確認フォーム作成</h3>

 </div>

 </div>

 </div>

 <p>以下の条件を満たしていれば，Detail Information の編集内容確認フォームの作成方法は規定しません．</p>

 <div class="itemizedlist">

 <ul type="disc">

 <li>

 <p>Detail Information の各フィールド値を次ページへ送信するための &lt;input type='hidden'&gt; タグをつける</p>

 </li>

 <li>

 <p>送信するパラメータに予約済みパラメータ名を使用しない</p>

 </li>

 <li>

 <p>出力するHTMLがシステムの画面構成や動作を妨げない</p>

 </li>

 </ul>

 </div>

 <p>共通ライブラリに用意された機能を利用して，添付ファイルや画像の編集内容確認フォームを生成できます．</p>

 <p>以下の項目も参照してください．</p>

 <div class="itemizedlist">

 <ul type="disc">

 <li>

 <p>xnpGetBasicInformationConfirmBlock</p>

 </li>

 <li>

 <p>xnpGetPreviewConfirmBlock</p>

 </li>

 <li>

 <p>xnpGetAttachmentConfirmBlock</p>

 </li>

 <li>

 <p>xnpGetTextFileConfirmBlock</p>

 </li>

 <li>

 <p>xnpGetRightsConfirmBlock</p>

 </li>

 <li>

 <p>xnpGetIndexConfirmBlock</p>

 </li>

 <li>

 <p>xnpGetDownloadLimitationOptionConfirmBlock</p>

 </li>

 <li>

 <p>xnpGetDownloadNotificationOptionConfirmBlock</p>

 </li>

 </ul>

 </div>

 </div>

 <div class="section" lang="ja" xml:lang="ja">

 <div xmlns="" class="titlepage">

 <div>

 <div>

 <h3 xmlns="http://www.w3.org/1999/xhtml" class="title"><a id="edit.confirm.reservedparam"></a>2.5. 予約済みパラメータ名</h3>

 </div>

 </div>

 </div>

 <p>システムが使用する (POST で送信する) パラメータの名前 (&lt;input&gt; タグの name 属性) は以下のとおりです．アイテムタイプモジュールが使用するパラメータが以下の名前と重複しないように注意してください．重複を避けるために Detail Information のパラメータ名にはプレフィクスとしてモジュール名を与えるとよいでしょう．</p>

 <div class="itemizedlist">

 <ul type="disc">

 <li>

 <p>mode</p>

 </li>

 <li>

 <p>fileID</p>

 </li>

 <li>

 <p>title</p>

 </li>

 <li>

 <p>keywords</p>

 </li>

 <li>

 <p>description</p>

 </li>

 <li>

 <p>doi</p>

 </li>

 <li>

 <p>change_log</p>

 </li>

 <li>

 <p>publicationDateYear</p>

 </li>

 <li>

 <p>publicationDateMonth</p>

 </li>

 <li>

 <p>publicationDateDay</p>

 </li>

 <li>

 <p>publicationDate</p>

 </li>

 <li>

 <p>item_id</p>

 </li>

 <li>

 <p>lang</p>

 </li>

 <li>

 <p>related_to</p>

 </li>

 <li>

 <p>scrollX</p>

 </li>

 <li>

 <p>scrollY</p>

 </li>

 <li>

 <p>xoonipsCheckedXID</p>

 </li>

 <li>

 <p>op</p>

 </li>

 <li>

 <p>related_to_check</p>

 </li>

 </ul>

 </div>

 </div>

 </div>

 <div class="section" lang="ja" xml:lang="ja">

 <div xmlns="" class="titlepage">

 <div>

 <div>

 <h2 xmlns="http://www.w3.org/1999/xhtml" class="title" style="clear: both"><a id="edit.query"></a>3. アイテム更新要求</h2>

 </div>

 </div>

 </div>

 <p>システムからの要求を受けて，アイテム更新処理を実行します．アイテムタイプモジュールの以下の関数に更新処理を定義してください．システムは更新処理が必要なときこの関数をコールバックします．編集フォームに入力された情報は$_POST配列から取得します．</p>

 <div class="itemizedlist">

 <ul type="disc">

 <li>

 <p>function &lt;モジュール名&gt;UpdateItem( )</p>

 <div class="itemizedlist">

 <ul type="circle">

 <li>

 <p>引数 : なし</p>

 </li>

 <li>

 <p>戻り値 : true (成功)，false (失敗)</p>

 </li>

 </ul>

 </div>

 </li>

 </ul>

 </div>

 <div class="section" lang="ja" xml:lang="ja">

 <div xmlns="" class="titlepage">

 <div>

 <div>

 <h3 xmlns="http://www.w3.org/1999/xhtml" class="title"><a id="edit.query.basic"></a>3.1. Basic Informationの更新</h3>

 </div>

 </div>

 </div>

 <p>共通ライブラリにBasic Information更新関数が用意されています．その関数を呼び出してください．呼び出すときに，更新するアイテムのアイテムIDを引数に指定します．</p>

 <p>以下の項目も参照してください．</p>

 <div class="itemizedlist">

 <ul type="disc">

 <li>

 <p>xnpUpdateBasicInformation</p>

 </li>

 </ul>

 </div>

 </div>

 <div class="section" lang="ja" xml:lang="ja">

 <div xmlns="" class="titlepage">

 <div>

 <div>

 <h3 xmlns="http://www.w3.org/1999/xhtml" class="title"><a id="edit.query.detail"></a>3.2. Detail Informationの更新</h3>

 </div>

 </div>

 </div>

 <p>Detail Informationを更新する処理を定義します．</p>

 <p>添付ファイル，画像ファイル，テキストの更新には共通ライブラリを使用できます．Detail Informationの更新方法，DBの使用，DBの種類，処理方法は規定しませんので自由に定義してください．</p>

 <p>以下の項目も参照してください．</p>

 <div class="itemizedlist">

 <ul type="disc">

 <li>

 <p>xnpUpdateBasicInformation</p>

 </li>

 <li>

 <p>xnpUpdateIndex</p>

 </li>

 <li>

 <p>xnpUpdateAttachment</p>

 </li>

 <li>

 <p>xnpUpdatePreview</p>

 </li>

 </ul>

 </div>

 </div>

 </div>

 </div>

 <div xmlns="http://www.w3.org/1999/xhtml" class="navfooter">



 </div>

 <div class="lastupdated">Last updated: 2010/04/15</div>

 </div>

 </body>

</html>


