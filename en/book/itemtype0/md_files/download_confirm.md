 <body>

 <div id="page">

 <div xmlns="http://www.w3.org/1999/xhtml" class="navheader">

 </div>

 <div xmlns="http://www.w3.org/1999/xhtml" class="chapter" lang="ja" id="download_confirm" xml:lang="ja">

 <div xmlns="" class="titlepage">

 <div>

 <div>

 <h2 xmlns="http://www.w3.org/1999/xhtml" class="title"><a id="download_confirm"></a>第22章 ダウンロード前の合意要求</h2>

 </div>

 </div>

 </div>

 <p>添付ファイルのダウンロード前に，ライセンスの合意とダウンロード通知の合意を求めます．そのためにアイテムタイプは，以下の関数を実装します．</p>

 <div class="itemizedlist">

 <ul type="disc">

 <li>

 <p>ライセンスの合意要求の有無を返す関数</p>

 </li>

 <li>

 <p>ダウンロードの通知の有無を返す関数</p>

 </li>

 <li>

 <p>合意を問い合わせるブロックを生成する関数</p>

 </li>

 </ul>

 </div>

 <p>合意のパターンは以下の4種類です。</p>

 <div class="itemizedlist">

 <ul type="disc">

 <li>

 <p>ライセンスとダウンロード通知の合意が必要</p>

 </li>

 <li>

 <p>ライセンスの合意が必要</p>

 </li>

 <li>

 <p>ダウンロード通知の合意が必要</p>

 </li>

 <li>

 <p>どちらの合意も不要</p>

 </li>

 </ul>

 </div>

 <p>ライセンスの合意が必要な添付ファイルの場合、システムはユーザ

 にアイテムのライセンス文を提示し合意を求めます。ダウンロードを通知

 する場合、システムはユーザにダウンロードが通知される旨を告知して合

 意を求めます。合意されない場合はダウンロードできません。</p>

 <p>この機能を利用するには，次の &lt;モジュール名&gt;GetDownloadConfirmationBlock( $item_id, $download_file_id ) を定義する必要があります．

 </p>

 <p>以下の項目も参照してください．</p>

 <div class="itemizedlist">

 <ul type="disc">

 <li>

 <p>xnpGetAttachmentDetailBlock</p>

 </li>

 <li>

 <p>xnpGetDownloadConfirmationBlock</p>

 </li>

 <li>

 <p>&lt;モジュール名&gt;GetDownloadConfirmationBlock</p>

 </li>

 </ul>

 </div>

 <div class="section" lang="ja" xml:lang="ja">

 <div xmlns="" class="titlepage">

 <div>

 <div>

 <h2 xmlns="http://www.w3.org/1999/xhtml" class="title" style="clear: both"><a id="download_confirm.required"></a>1. ライセンスの合意要求の有無</h2>

 </div>

 </div>

 </div>

 <p>アイテムタイプモジュールの以下の関数で，ダウンロード前の合意が必要かどうかを返してください．</p>

 <pre class="programlisting">bool &lt;モジュール名&gt;GetDownloadConfirmationRequired( $item_id )</pre>

 <div class="itemizedlist">

 <ul type="disc">

 <li>

 <p>戻り値 : true(ダウンロード前に合意が必要)</p>

 </li>

 <li>

 <p>戻り値 : false(ダウンロード前に合意が不要)</p>

 </li>

 </ul>

 </div>

 </div>

 <div class="section" lang="ja" xml:lang="ja">

 <div xmlns="" class="titlepage">

 <div>

 <div>

 <h2 xmlns="http://www.w3.org/1999/xhtml" class="title" style="clear: both"><a id="download_confirm.notify"></a>2. ダウンロードの通知の有無</h2>

 </div>

 </div>

 </div>

 <p>添付ファイルのダウンロードをアイテム作成者に通知することができます．通知の要否を返す以下の関数を実装してください．実装のないアイテムタイプは，通知しないものとみなされます．</p>

 <pre class="programlisting">bool &lt;モジュール名&gt;GetAttachmentDownloadNotifyOption( $item_id )</pre>

 <div class="itemizedlist">

 <ul type="disc">

 <li>

 <p>引数 item_id: ダウンロードする添付ファイルを持つアイテムのID</p>

 </li>

 <li>

 <p>戻り値 : true(ダウンロードを通知する)</p>

 </li>

 <li>

 <p>戻り値 : false(ダウンロードを通知しない)</p>

 </li>

 </ul>

 </div>

 </div>

 <div class="section" lang="ja" xml:lang="ja">

 <div xmlns="" class="titlepage">

 <div>

 <div>

 <h2 xmlns="http://www.w3.org/1999/xhtml" class="title" style="clear: both"><a id="download_confirm.block"></a>3. 合意要求ブロック</h2>

 </div>

 </div>

 </div>

 <p>合意を求めるブロックを返す以下の関数を定義してください．</p>

 <pre class="programlisting">string &lt;モジュール名&gt;GetDownloadConfirmationBlock( $item_id, $download_file_id )</pre>

 <div class="itemizedlist">

 <ul type="disc">

 <li>

 <p>引数 item_id: アイテムのID</p>

 </li>

 <li>

 <p>引数 download_file_id: ダウンロードするファイルのID．</p>

 </li>

 <li>

 <p>戻り値 : ライセンスとダウンロード通知の合意を求めるブロック</p>

 </li>

 </ul>

 </div>

 <p>関数xnpGetDownloadConfirmationBlock()を呼び，その戻り値をそのまま返してください．</p>

 <p>以下の項目も参照してください．</p>

 <div class="itemizedlist">

 <ul type="disc">

 <li>

 <p>xnpGetDownloadConfirmationBlock</p>

 </li>

 </ul>

 </div>

 </div>

 </div>

 <div xmlns="http://www.w3.org/1999/xhtml" class="navfooter">



 </div>

 
 </div>

 </body>



