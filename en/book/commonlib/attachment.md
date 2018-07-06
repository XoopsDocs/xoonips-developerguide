 <body>

 <div id="page">

 <div xmlns="http://www.w3.org/1999/xhtml" class="navheader">

 </div>

 <div xmlns="http://www.w3.org/1999/xhtml" class="chapter" lang="ja" id="attachment" xml:lang="ja">

 <div xmlns="" class="titlepage">

 <div>

 <div>

 <h2 xmlns="http://www.w3.org/1999/xhtml" class="title"><a id="attachment"></a>第6章 Attachment</h2>

 </div>

 </div>

 </div>

 <p>アイテムにファイルを添付したい場合に使用します．($name 引数については <a href="auxil.html" title="第14章 補足: Attachment, TextFile 系関数の $name 引数について">章 14. <i>補足: Attachment, TextFile 系関数の $name 引数について</i></a> を参照)</p>

 <div class="section" lang="ja" xml:lang="ja">

 <div xmlns="" class="titlepage">

 <div>

 <div>

 <h2 xmlns="http://www.w3.org/1999/xhtml" class="title" style="clear: both"><a id="func-xnpGetAttachmentDetailBlock"></a>1. array xnpGetAttachmentDetailBlock( int item_id, string name )</h2>

 </div>

 </div>

 </div>

 <p>アイテム詳細画面に表示するフォームを作成します．ファイル名とサイズを表示します．ファイルをダウンロードするにはファイル名をクリックします．</p>

 <div class="section" lang="ja" xml:lang="ja">

 <div xmlns="" class="titlepage">

 <div>

 <div>

 <h3 xmlns="http://www.w3.org/1999/xhtml" class="title"><a id="func-xnpGetAttachmentDetailBlock-postvar"></a>1.1. 内部で参照する $_POST 変数</h3>

 </div>

 </div>

 </div>

 <p>なし</p>

 </div>

 <div class="section" lang="ja" xml:lang="ja">

 <div xmlns="" class="titlepage">

 <div>

 <div>

 <h3 xmlns="http://www.w3.org/1999/xhtml" class="title"><a id="func-xnpGetAttachmentDetailBlock-view"></a>1.2. 画面</h3>

 </div>

 </div>

 </div>

 <p>誰でもダウンロード可能な場合</p>

 <div class="blockquote">

 <blockquote class="blockquote">

 <div class="informalfigure">

 <div class="mediaobject">

 <img src="images\xnpGetAttachmentDetailBlock3.gif" />

 </div>

 </div>

 </blockquote>

 </div>

 <p>ログインユーザのみダウンロード可能, かつログインユーザの場合</p>

 <div class="blockquote">

 <blockquote class="blockquote">

 <div class="informalfigure">

 <div class="mediaobject">

 <img src="images\xnpGetAttachmentDetailBlock4.gif" />

 </div>

 </div>

 </blockquote>

 </div>

 <p>ログインユーザのみダウンロード可能, かつゲストユーザの場合</p>

 <div class="blockquote">

 <blockquote class="blockquote">

 <div class="informalfigure">

 <div class="mediaobject">

 <img src="images\xnpGetAttachmentDetailBlock2.gif" />

 </div>

 </div>

 </blockquote>

 </div>

 </div>

 <div class="section" lang="ja" xml:lang="ja">

 <div xmlns="" class="titlepage">

 <div>

 <div>

 <h3 xmlns="http://www.w3.org/1999/xhtml" class="title"><a id="func-xnpGetAttachmentDetailBlock-putvar"></a>1.3. 送信データ</h3>

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

 <h2 xmlns="http://www.w3.org/1999/xhtml" class="title" style="clear: both"><a id="func-xnpGetAttachmentEditBlock"></a>2. array xnpGetAttachmentEditBlock( int item_id, string name )</h2>

 </div>

 </div>

 </div>

 <p>アイテム編集画面に表示するフォームを作成します．アップロードするファイルの指定と，アップ済みファイルの情報とその削除ボタンを表示します．</p>

 <div class="section" lang="ja" xml:lang="ja">

 <div xmlns="" class="titlepage">

 <div>

 <div>

 <h3 xmlns="http://www.w3.org/1999/xhtml" class="title"><a id="func-xnpGetAttachmentEditBlock-postvar"></a>2.1. 内部で参照する $_POST 変数</h3>

 </div>

 </div>

 </div>

 <div class="itemizedlist">

 <ul type="disc">

 <li>

 <p>$_POST['mode']</p>

 </li>

 <li>

 <p>$_POST['fileID']</p>

 </li>

 <li>

 <p>$_POST["${name}FileID"]</p>

 </li>

 </ul>

 </div>

 </div>

 <div class="section" lang="ja" xml:lang="ja">

 <div xmlns="" class="titlepage">

 <div>

 <div>

 <h3 xmlns="http://www.w3.org/1999/xhtml" class="title"><a id="func-xnpGetAttachmentEditBlock-view"></a>2.2. 画面</h3>

 </div>

 </div>

 </div>

 <div class="blockquote">

 <blockquote class="blockquote">

 <div class="informalfigure">

 <div class="mediaobject">

 <img src="images\xnpGetAttachmentEditBlock.gif" />

 </div>

 </div>

 </blockquote>

 </div>

 </div>

 <div class="section" lang="ja" xml:lang="ja">

 <div xmlns="" class="titlepage">

 <div>

 <div>

 <h3 xmlns="http://www.w3.org/1999/xhtml" class="title"><a id="func-xnpGetAttachmentEditBlock-putvar"></a>2.3. 送信データ</h3>

 </div>

 </div>

 </div>

 <p>Delete ボタン → 現在の画面へ以下を送信する．</p>

 <div class="itemizedlist">

 <ul type="disc">

 <li>

 <p>$_POST['mode'] = 'Delete'</p>

 </li>

 <li>

 <p>$_POST["${name}FileID"] = $file_id</p>

 </li>

 <li>

 <p>$_POST['fileID']</p>

 </li>

 </ul>

 </div>

 <p>Submit ボタン → 確認画面へ以下を送信する</p>

 <div class="itemizedlist">

 <ul type="disc">

 <li>

 <p>$_POST['mode']</p>

 </li>

 <li>

 <p>$_POST["${name}FileID"]</p>

 </li>

 <li>

 <p>$_FILES["${name}"]</p>

 </li>

 </ul>

 </div>

 </div>

 </div>

 <div class="section" lang="ja" xml:lang="ja">

 <div xmlns="" class="titlepage">

 <div>

 <div>

 <h2 xmlns="http://www.w3.org/1999/xhtml" class="title" style="clear: both"><a id="func-xnpGetAttachmentConfirmBlock"></a>3. array xnpGetAttachmentConfirmBlock( int item_id, string name )</h2>

 </div>

 </div>

 </div>

 <p>登録確認画面，編集確認画面に表示するフォームを作成します．</p>

 <div class="section" lang="ja" xml:lang="ja">

 <div xmlns="" class="titlepage">

 <div>

 <div>

 <h3 xmlns="http://www.w3.org/1999/xhtml" class="title"><a id="func-xnpGetAttachmentConfirmBlock-postvar"></a>3.1. 内部で参照する $_POST 変数</h3>

 </div>

 </div>

 </div>

 <div class="itemizedlist">

 <ul type="disc">

 <li>

 <p>$_POST["${name}FileID"]</p>

 </li>

 <li>

 <p>$_FILES["${name}"]</p>

 </li>

 </ul>

 </div>

 </div>

 <div class="section" lang="ja" xml:lang="ja">

 <div xmlns="" class="titlepage">

 <div>

 <div>

 <h3 xmlns="http://www.w3.org/1999/xhtml" class="title"><a id="func-xnpGetAttachmentConfirmBlock-view"></a>3.2. 画面</h3>

 </div>

 </div>

 </div>

 <div class="blockquote">

 <blockquote class="blockquote">

 <div class="informalfigure">

 <div class="mediaobject">

 <img src="images\xnpGetAttachmentConfirmBlock.gif" />

 </div>

 </div>

 </blockquote>

 </div>

 </div>

 <div class="section" lang="ja" xml:lang="ja">

 <div xmlns="" class="titlepage">

 <div>

 <div>

 <h3 xmlns="http://www.w3.org/1999/xhtml" class="title"><a id="func-xnpGetAttachmentConfirmBlock-putvar"></a>3.3. 送信データ</h3>

 </div>

 </div>

 </div>

 <div class="itemizedlist">

 <ul type="disc">

 <li>

 <p>$_POST["${name}FileID"] = $file_id</p>

 </li>

 </ul>

 </div>

 </div>

 </div>

 <div class="section" lang="ja" xml:lang="ja">

 <div xmlns="" class="titlepage">

 <div>

 <div>

 <h2 xmlns="http://www.w3.org/1999/xhtml" class="title" style="clear: both"><a id="func-xnpGetAttachmentRegisterBlock"></a>4. array xnpGetAttachmentRegisterBlock( string name )</h2>

 </div>

 </div>

 </div>

 <p>→ <a href="attachment.html#func-xnpGetAttachmentEditBlock" title="2. array xnpGetAttachmentEditBlock( int item_id, string name )">項2. 「array xnpGetAttachmentEditBlock( int item_id, string name )」</a> と同じ</p>

 </div>

 <div class="section" lang="ja" xml:lang="ja">

 <div xmlns="" class="titlepage">

 <div>

 <div>

 <h2 xmlns="http://www.w3.org/1999/xhtml" class="title" style="clear: both"><a id="func-xnpInsertAttachemnt"></a>5. xnpInsertAttachemnt : (無し)</h2>

 </div>

 </div>

 </div>

 <p>代わりに <a href="attachment.html#func-xnpUpdateAttachment" title="6. bool xnpUpdateAttachment( int item_id, string name )">項6. 「bool xnpUpdateAttachment( int item_id, string name )」</a> を使用してください</p>

 </div>

 <div class="section" lang="ja" xml:lang="ja">

 <div xmlns="" class="titlepage">

 <div>

 <div>

 <h2 xmlns="http://www.w3.org/1999/xhtml" class="title" style="clear: both"><a id="func-xnpUpdateAttachment"></a>6. bool xnpUpdateAttachment( int item_id, string name )</h2>

 </div>

 </div>

 </div>

 <p>添付ファイルをアイテムに登録します．既に添付ファイルがある場合はその情報を上書きします．</p>

 <div class="section" lang="ja" xml:lang="ja">

 <div xmlns="" class="titlepage">

 <div>

 <div>

 <h3 xmlns="http://www.w3.org/1999/xhtml" class="title"><a id="func-xnpUpdateAttachment-postvar"></a>6.1. 内部で参照する $_POST 変数</h3>

 </div>

 </div>

 </div>

 <div class="itemizedlist">

 <ul type="disc">

 <li>

 <p>$_POST['fileID']</p>

 </li>

 </ul>

 </div>

 </div>

 </div>

 <div class="section" lang="ja" xml:lang="ja">

 <div xmlns="" class="titlepage">

 <div>

 <div>

 <h2 xmlns="http://www.w3.org/1999/xhtml" class="title" style="clear: both"><a id="func-xnpDeleteAttachment"></a>7. xnpDeleteAttachemnt : (無し)</h2>

 </div>

 </div>

 </div>

 <p><a href="basicinfo.html#func-xnpDeleteBasicInformation" title="9. bool xnpDeleteBasicInformation( int item_id )">項9. 「bool xnpDeleteBasicInformation( int item_id )」</a> が Attachment の削除を行うので，この関数はありません．</p>

 </div>

 <div class="section" lang="ja" xml:lang="ja">

 <div xmlns="" class="titlepage">

 <div>

 <div>

 <h2 xmlns="http://www.w3.org/1999/xhtml" class="title" style="clear: both"><a id="func-xnpGetDownloadLimitationOptionRegisterBlock"></a>8. bool xnpGetDownloadLimitationOptionRegisterBlock( string dirname, int option = 0 )</h2>

 </div>

 </div>

 </div>

 <p>添付ファイルのダウンロード制限を登録するフォームを生成します．アイテムタイプがアイテム登録画面を作成する際に使用します．</p>

 <p>dirname引数で添付ファイルが属するモジュールのフォルダ名を指定します．option引数で，制限の初期値を指定します．1でログインユーザに限定，0で全てのユーザに解放，を意味します．option引数省略時のデフォルト値は0です．</p>

 <p>$_POST['attachment_dl_limit']が定義されている場合はoption引数の値は無視されます．</p>

 <div class="section" lang="ja" xml:lang="ja">

 <div xmlns="" class="titlepage">

 <div>

 <div>

 <h3 xmlns="http://www.w3.org/1999/xhtml" class="title"><a id="func-xnpGetDownloadLimitationOptionRegisterBlock-postvar"></a>8.1. 内部で参照する $_POST 変数</h3>

 </div>

 </div>

 </div>

 <div class="itemizedlist">

 <ul type="disc">

 <li>

 <p>$_POST['attachment_dl_limit']</p>

 </li>

 </ul>

 </div>

 </div>

 <div class="section" lang="ja" xml:lang="ja">

 <div xmlns="" class="titlepage">

 <div>

 <div>

 <h3 xmlns="http://www.w3.org/1999/xhtml" class="title"><a id="func-xnpGetDownloadLimitationOptionRegisterBlock-putvar"></a>8.2. 送信データ</h3>

 </div>

 </div>

 </div>

 <div class="itemizedlist">

 <ul type="disc">

 <li>

 <p>$_POST['attachment_dl_limit']</p>

 </li>

 </ul>

 </div>

 </div>

 </div>

 <div class="section" lang="ja" xml:lang="ja">

 <div xmlns="" class="titlepage">

 <div>

 <div>

 <h2 xmlns="http://www.w3.org/1999/xhtml" class="title" style="clear: both"><a id="func-xnpGetDownloadLimitationOptionEditBlock"></a>9. bool xnpGetDownloadLimitationOptionEditBlock( string dirname, int option )</h2>

 </div>

 </div>

 </div>

 <p>添付ファイルのダウンロード制限を編集するフォームを生成します．アイテムタイプがアイテム編集画面を作成する際に使用します．</p>

 <p>dirname引数で添付ファイルが属するモジュールのフォルダ名を指定します．option引数で，制限の初期値を指定します．1でログインユーザに限定，0で全てのユーザに解放，を意味します．</p>

 <p>$_POST['attachment_dl_limit']が定義されている場合はoption引数の値は無視されます．</p>

 <div class="section" lang="ja" xml:lang="ja">

 <div xmlns="" class="titlepage">

 <div>

 <div>

 <h3 xmlns="http://www.w3.org/1999/xhtml" class="title"><a id="func-xnpGetDownloadLimitationOptionEditBlock-postvar"></a>9.1. 内部で参照する $_POST 変数</h3>

 </div>

 </div>

 </div>

 <div class="itemizedlist">

 <ul type="disc">

 <li>

 <p>$_POST['attachment_dl_limit']</p>

 </li>

 </ul>

 </div>

 </div>

 <div class="section" lang="ja" xml:lang="ja">

 <div xmlns="" class="titlepage">

 <div>

 <div>

 <h3 xmlns="http://www.w3.org/1999/xhtml" class="title"><a id="func-xnpGetDownloadLimitationOptionEditBlock-putvar"></a>9.2. 送信データ</h3>

 </div>

 </div>

 </div>

 <div class="itemizedlist">

 <ul type="disc">

 <li>

 <p>$_POST['attachment_dl_limit']</p>

 </li>

 </ul>

 </div>

 </div>

 </div>

 <div class="section" lang="ja" xml:lang="ja">

 <div xmlns="" class="titlepage">

 <div>

 <div>

 <h2 xmlns="http://www.w3.org/1999/xhtml" class="title" style="clear: both"><a id="func-xnpGetDownloadLimitationOptionConfirmBlock"></a>10. bool xnpGetDownloadLimitationOptionConfirmBlock( string dirname )</h2>

 </div>

 </div>

 </div>

 <p>添付ファイルのダウンロード制限を確認するフォームを生成します．</p>

 <p>dirname引数で添付ファイルが属するモジュールのフォルダ名を指定します．</p>

 <div class="section" lang="ja" xml:lang="ja">

 <div xmlns="" class="titlepage">

 <div>

 <div>

 <h3 xmlns="http://www.w3.org/1999/xhtml" class="title"><a id="func-xnpGetDownloadLimitationOptionConfirmBlock-postvar"></a>10.1. 内部で参照する $_POST 変数</h3>

 </div>

 </div>

 </div>

 <div class="itemizedlist">

 <ul type="disc">

 <li>

 <p>$_POST['attachment_dl_limit']</p>

 </li>

 </ul>

 </div>

 </div>

 <div class="section" lang="ja" xml:lang="ja">

 <div xmlns="" class="titlepage">

 <div>

 <div>

 <h3 xmlns="http://www.w3.org/1999/xhtml" class="title"><a id="func-xnpGetDownloadLimitationOptionConfirmBlock-putvar"></a>10.2. 送信データ</h3>

 </div>

 </div>

 </div>

 <div class="itemizedlist">

 <ul type="disc">

 <li>

 <p>$_POST['attachment_dl_limit']</p>

 </li>

 </ul>

 </div>

 </div>

 </div>

 <div class="section" lang="ja" xml:lang="ja">

 <div xmlns="" class="titlepage">

 <div>

 <div>

 <h2 xmlns="http://www.w3.org/1999/xhtml" class="title" style="clear: both"><a id="func-xnpGetDownloadNotificationOptionRegisterBlock"></a>11. bool xnpGetDownloadNotificationOptionRegisterBlock( string dirname, int option = 0 )</h2>

 </div>

 </div>

 </div>

 <p>添付ファイルのダウンロード通知を登録するフォームを生成します．アイテムタイプがアイテム登録画面を作成する際に使用します．</p>

 <p>dirname引数で添付ファイルが属するモジュールのフォルダ名を指定します．option引数で，通知の初期値を指定します．1で通知する，0で通知しない，を意味します．option引数省略時のデフォルト値は0です．</p>

 <p>$_POST['attachment_dl_notify']が定義されている場合はoption引数の値は無視されます．</p>

 <div class="section" lang="ja" xml:lang="ja">

 <div xmlns="" class="titlepage">

 <div>

 <div>

 <h3 xmlns="http://www.w3.org/1999/xhtml" class="title"><a id="func-xnpGetDownloadNotificationOptionRegisterBlock-postvar"></a>11.1. 内部で参照する $_POST 変数</h3>

 </div>

 </div>

 </div>

 <div class="itemizedlist">

 <ul type="disc">

 <li>

 <p>$_POST['attachment_dl_notify']</p>

 </li>

 </ul>

 </div>

 </div>

 <div class="section" lang="ja" xml:lang="ja">

 <div xmlns="" class="titlepage">

 <div>

 <div>

 <h3 xmlns="http://www.w3.org/1999/xhtml" class="title"><a id="func-xnpGetDownloadNotificationOptionRegisterBlock-putvar"></a>11.2. 送信データ</h3>

 </div>

 </div>

 </div>

 <div class="itemizedlist">

 <ul type="disc">

 <li>

 <p>$_POST['attachment_dl_notify']</p>

 </li>

 </ul>

 </div>

 </div>

 </div>

 <div class="section" lang="ja" xml:lang="ja">

 <div xmlns="" class="titlepage">

 <div>

 <div>

 <h2 xmlns="http://www.w3.org/1999/xhtml" class="title" style="clear: both"><a id="func-xnpGetDownloadNotificationOptionEditBlock"></a>12. bool xnpGetDownloadNotificationOptionEditBlock( string dirname, int option )</h2>

 </div>

 </div>

 </div>

 <p>添付ファイルのダウンロード通知を編集するフォームを生成します．アイテムタイプがアイテム編集画面を作成する際に使用します．</p>

 <p>dirname引数で添付ファイルが属するモジュールのフォルダ名を指定します．option引数で，通知の初期値を指定します．1で通知する，0で通知しない，を意味します．</p>

 <p>$_POST['attachment_dl_notify']が定義されている場合はoption引数の値は無視されます．</p>

 <div class="section" lang="ja" xml:lang="ja">

 <div xmlns="" class="titlepage">

 <div>

 <div>

 <h3 xmlns="http://www.w3.org/1999/xhtml" class="title"><a id="func-xnpGetDownloadNotificationOptionEditBlock-postvar"></a>12.1. 内部で参照する $_POST 変数</h3>

 </div>

 </div>

 </div>

 <div class="itemizedlist">

 <ul type="disc">

 <li>

 <p>$_POST['attachment_dl_notify']</p>

 </li>

 </ul>

 </div>

 </div>

 <div class="section" lang="ja" xml:lang="ja">

 <div xmlns="" class="titlepage">

 <div>

 <div>

 <h3 xmlns="http://www.w3.org/1999/xhtml" class="title"><a id="func-xnpGetDownloadNotificationOptionEditBlock-putvar"></a>12.2. 送信データ</h3>

 </div>

 </div>

 </div>

 <div class="itemizedlist">

 <ul type="disc">

 <li>

 <p>$_POST['attachment_dl_notify']</p>

 </li>

 </ul>

 </div>

 </div>

 </div>

 <div class="section" lang="ja" xml:lang="ja">

 <div xmlns="" class="titlepage">

 <div>

 <div>

 <h2 xmlns="http://www.w3.org/1999/xhtml" class="title" style="clear: both"><a id="func-xnpGetDownloadNotificationOptionConfirmBlock"></a>13. bool xnpGetDownloadNotificationOptionConfirmBlock( string dirname )</h2>

 </div>

 </div>

 </div>

 <p>添付ファイルのダウンロード通知を確認するフォームを生成します．</p>

 <p>dirname引数で添付ファイルが属するモジュールのフォルダ名を指定します．</p>

 <div class="section" lang="ja" xml:lang="ja">

 <div xmlns="" class="titlepage">

 <div>

 <div>

 <h3 xmlns="http://www.w3.org/1999/xhtml" class="title"><a id="func-xnpGetDownloadNotificationOptionConfirmBlock-postvar"></a>13.1. 内部で参照する $_POST 変数</h3>

 </div>

 </div>

 </div>

 <div class="itemizedlist">

 <ul type="disc">

 <li>

 <p>$_POST['attachment_dl_notify']</p>

 </li>

 </ul>

 </div>

 </div>

 <div class="section" lang="ja" xml:lang="ja">

 <div xmlns="" class="titlepage">

 <div>

 <div>

 <h3 xmlns="http://www.w3.org/1999/xhtml" class="title"><a id="func-xnpGetDownloadNotificationOptionConfirmBlock-putvar"></a>13.2. 送信データ</h3>

 </div>

 </div>

 </div>

 <div class="itemizedlist">

 <ul type="disc">

 <li>

 <p>$_POST['attachment_dl_notify']</p>

 </li>

 </ul>

 </div>

 </div>

 </div>

 <div class="section" lang="ja" xml:lang="ja">

 <div xmlns="" class="titlepage">

 <div>

 <div>

 <h2 xmlns="http://www.w3.org/1999/xhtml" class="title" style="clear: both"><a id="func-xnpGetDownloadConfirmationBlock"></a>14. bool xnpGetDownloadConfirmationBlock( int item_id, int download_file_id, bool attachment_dl_notify, bool use_license, int use_cc, string rights )</h2>

 </div>

 </div>

 </div>

 <p>添付ファイルのダウンロード前に合意を求めるポップアップを表示するブロックを生成します。</p>

 <p>download_file_id引数がfalseでないなら，download_file_idで指定されたファイルのダウンロードボタンを自動で押します．falseなら押しません．

 attachment_dl_notifyがtrueならダウンロード前にダウンロード通知の合意を求め，falseなら求めません．

 use_licenseがtrueならダウンロード前にライセンスの合意を求め，falseなら求めません．</p>

 <p>rightsにはライセンス文を指定します．use_ccには，rightsがテキスト形式なら0を指定し，HTML形式なら1を指定します．</p>

 <p>attachment_dl_notifyとuse_licenseの片方でもtrueなら，ユーザは求められた全ての合意で「合意します」を選択しないとファイルをダウンロードできません．</p>

 <div class="section" lang="ja" xml:lang="ja">

 <div xmlns="" class="titlepage">

 <div>

 <div>

 <h3 xmlns="http://www.w3.org/1999/xhtml" class="title"><a id="func-xnpGetDownloadConfirmationBlock-postvar"></a>14.1. 内部で参照する $_POST 変数</h3>

 </div>

 </div>

 </div>

 <div class="itemizedlist">

 <ul type="disc">

 <li>

 <p>なし</p>

 </li>

 </ul>

 </div>

 </div>

 <div class="section" lang="ja" xml:lang="ja">

 <div xmlns="" class="titlepage">

 <div>

 <div>

 <h3 xmlns="http://www.w3.org/1999/xhtml" class="title"><a id="func-xnpGetDownloadConfirmationBlock-putvar"></a>14.2. 送信データ</h3>

 </div>

 </div>

 </div>

 <div class="itemizedlist">

 <ul type="disc">

 <li>

 <p>$_POST['file_id']</p>

 </li>

 <li>

 <p>$_POST['xoonips_download_with_token']</p>

 </li>

 <li>

 <p>(XOOPSのXoopsToken．名前は'xoonips_download_token')</p>

 </li>

 </ul>

 </div>

 </div>

 </div>

 </div>

 <div xmlns="http://www.w3.org/1999/xhtml" class="navfooter">



 </div>

 </body>


