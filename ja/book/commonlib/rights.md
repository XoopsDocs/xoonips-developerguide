 <body>

 <div id="page">

 <div xmlns="http://www.w3.org/1999/xhtml" class="navheader">

 </div>

 <div xmlns="http://www.w3.org/1999/xhtml" class="chapter" lang="ja" id="rights" xml:lang="ja">

 <div xmlns="" class="titlepage">

 <div>

 <div>

 <h2 xmlns="http://www.w3.org/1999/xhtml" class="title"><a id="rights"></a>第8章 Rights</h2>

 </div>

 </div>

 </div>

 <p>Rightsを取り扱います．Creative Commonsのライセンスまたは<a href="textfile.html" title="第7章 TextFile">章 7. <i>TextFile</i></a>同様の長文を設定可能です．</p>

 <div class="section" lang="ja" xml:lang="ja">

 <div xmlns="" class="titlepage">

 <div>

 <div>

 <h2 xmlns="http://www.w3.org/1999/xhtml" class="title" style="clear: both"><a id="func-xnpGetRightsDetailBlock"></a>1. array xnpGetRightsDetailBlock( int item_id, int use_cc=1, string text='', int cc_commercial_use=1, int cc_modification=2 )</h2>

 </div>

 </div>

 </div>

 <div class="section" lang="ja" xml:lang="ja">

 <div xmlns="" class="titlepage">

 <div>

 <div>

 <h3 xmlns="http://www.w3.org/1999/xhtml" class="title"><a id="func-xnpGetRightsDetailBlock-inpval"></a>1.1. 入力</h3>

 </div>

 </div>

 </div>

 <div class="itemizedlist">

 <ul type="disc">

 <li>

 <p>use_cc : Some rights reservedを選択なら1，そうでないなら0</p>

 </li>

 <li>

 <p>text : urlencodeされたLicense Text</p>

 </li>

 <li>

 <p>cc_commercial_use : 営利目的利用を許すなら1, そうでないなら0</p>

 </li>

 <li>

 <p>cc_modification : 翻案・改変を許すなら2, 条件付で許すなら1, そうでないなら0</p>

 </li>

 </ul>

 </div>

 </div>

 <div class="section" lang="ja" xml:lang="ja">

 <div xmlns="" class="titlepage">

 <div>

 <div>

 <h3 xmlns="http://www.w3.org/1999/xhtml" class="title"><a id="func-xnpGetRightsDetailBlock-postvar"></a>1.2. 内部で参照する $_POST 変数</h3>

 </div>

 </div>

 </div>

 <p>なし</p>

 </div>

 <div class="section" lang="ja" xml:lang="ja">

 <div xmlns="" class="titlepage">

 <div>

 <div>

 <h3 xmlns="http://www.w3.org/1999/xhtml" class="title"><a id="func-xnpGetRightsDetailBlock-view"></a>1.3. 画面</h3>

 </div>

 </div>

 </div>

 <p>Some rights reservedを選択した場合は以下のように表示されます．</p>

 <div class="blockquote">

 <blockquote class="blockquote">

 <div class="informalfigure">

 <div class="mediaobject">

 <img src="../../assets/commonlib/xnpGetRightsDetailBlock.gif" />

 </div>

 </div>

 </blockquote>

 </div>

 <p>All rights reservedを選択した場合は、<a href="textfile.html#func-xnpGetTextFileDetailBlock" title="1. array xnpGetTextFileDetailBlock( int item_id, string name, string text )">項1. 「array xnpGetTextFileDetailBlock( int item_id, string name, string text )」</a> と同じです</p>

 </div>

 <div class="section" lang="ja" xml:lang="ja">

 <div xmlns="" class="titlepage">

 <div>

 <div>

 <h3 xmlns="http://www.w3.org/1999/xhtml" class="title"><a id="func-xnpGetRightsDetailBlock-putvar"></a>1.4. 送信データ</h3>

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

 <h2 xmlns="http://www.w3.org/1999/xhtml" class="title" style="clear: both"><a id="func-xnpGetRightsEditBlock"></a>2. array xnpGetRightsEditBlock( int item_id, int use_cc=1, string text='', int cc_commercial_use=1, int cc_modification=2 )</h2>

 </div>

 </div>

 </div>

 <div class="section" lang="ja" xml:lang="ja">

 <div xmlns="" class="titlepage">

 <div>

 <div>

 <h3 xmlns="http://www.w3.org/1999/xhtml" class="title"><a id="func-xnpGetRightsEditBlock-inpval"></a>2.1. 入力</h3>

 </div>

 </div>

 </div>

 <div class="itemizedlist">

 <ul type="disc">

 <li>

 <p>use_cc : Some rights reservedを選択なら1，そうでないなら0</p>

 </li>

 <li>

 <p>text : urlencodeされたLicense Text</p>

 </li>

 <li>

 <p>cc_commercial_use : 営利目的利用を許すなら1, そうでないなら0</p>

 </li>

 <li>

 <p>cc_modification : 翻案・改変を許すなら2, 条件付で許すなら1, そうでないなら0</p>

 </li>

 </ul>

 </div>

 <p>※ $_POST["rightsUseCC"]があれば，これらの引数は全て無視されて以下の$_POST変数が使用されます．</p>

 </div>

 <div class="section" lang="ja" xml:lang="ja">

 <div xmlns="" class="titlepage">

 <div>

 <div>

 <h3 xmlns="http://www.w3.org/1999/xhtml" class="title"><a id="func-xnpGetRightsEditBlock-postvar"></a>2.2. 内部で参照する $_POST 変数</h3>

 </div>

 </div>

 </div>

 <div class="itemizedlist">

 <ul type="disc">

 <li>

 <p>$_POST["rightsUseCC"] = Some rights reservedを選択なら1，そうでないなら0．</p>

 </li>

 <li>

 <p>$_POST["rightsEncText"] = urlencodeされたLicense Text</p>

 </li>

 <li>

 <p>$_POST["rightsCCCommercialUse"] = 営利目的利用を許すなら1, そうでないなら0</p>

 </li>

 <li>

 <p>$_POST["rightsCCModification"] = 翻案・改変を許すなら2, 条件付で許すなら1, そうでないなら0</p>

 </li>

 </ul>

 </div>

 </div>

 <div class="section" lang="ja" xml:lang="ja">

 <div xmlns="" class="titlepage">

 <div>

 <div>

 <h3 xmlns="http://www.w3.org/1999/xhtml" class="title"><a id="func-xnpGetRightsEditBlock-view"></a>2.3. 画面</h3>

 </div>

 </div>

 </div>

 <div class="blockquote">

 <blockquote class="blockquote">

 <div class="informalfigure">

 <div class="mediaobject">

 <img src="../../assets/commonlib/xnpGetRightsEditBlock1.gif" />

 </div>

 </div>

 </blockquote>

 </div>

 </div>

 <div class="section" lang="ja" xml:lang="ja">

 <div xmlns="" class="titlepage">

 <div>

 <div>

 <h3 xmlns="http://www.w3.org/1999/xhtml" class="title"><a id="func-xnpGetRightsEditBlock-putvar"></a>2.4. 送信データ</h3>

 </div>

 </div>

 </div>

 <p>Submit ボタン → 確認画面へ</p>

 <div class="itemizedlist">

 <ul type="disc">

 <li>

 <p>$_POST["rightsEncText"]</p>

 </li>

 <li>

 <p>$_POST["rightsUseCC"]</p>

 </li>

 <li>

 <p>$_POST["rightsCCCommercialUse"]</p>

 </li>

 <li>

 <p>$_POST["rightsCCModification"]</p>

 </li>

 </ul>

 </div>

 </div>

 </div>

 <div class="section" lang="ja" xml:lang="ja">

 <div xmlns="" class="titlepage">

 <div>

 <div>

 <h2 xmlns="http://www.w3.org/1999/xhtml" class="title" style="clear: both"><a id="func-xnpGetRightsConfirmBlock"></a>3. array xnpGetRightsConfirmBlock( int item_id, int maxlen=65535 )</h2>

 </div>

 </div>

 </div>

 <p>Confirm 画面用の HTML を生成する．</p>

 <div class="section" lang="ja" xml:lang="ja">

 <div xmlns="" class="titlepage">

 <div>

 <div>

 <h3 xmlns="http://www.w3.org/1999/xhtml" class="title"><a id="func-xnpGetRightsConfirmBlock-postvar"></a>3.1. 内部で参照する $_POST 変数</h3>

 </div>

 </div>

 </div>

 <div class="itemizedlist">

 <ul type="disc">

 <li>

 <p>$_POST["rightsEncText"]</p>

 </li>

 <li>

 <p>$_POST["rightsUseCC"]</p>

 </li>

 <li>

 <p>$_POST["rightsCCCommercialUse"]</p>

 </li>

 <li>

 <p>$_POST["rightsCCModification"]</p>

 </li>

 </ul>

 </div>

 </div>

 <div class="section" lang="ja" xml:lang="ja">

 <div xmlns="" class="titlepage">

 <div>

 <div>

 <h3 xmlns="http://www.w3.org/1999/xhtml" class="title"><a id="func-xnpGetRightsConfirmBlock-view"></a>3.2. 画面</h3>

 </div>

 </div>

 </div>

 <p>→ <a href="rights.html#func-xnpGetRightsDetailBlock" title="1. array xnpGetRightsDetailBlock( int item_id, int use_cc=1, string text='', int cc_commercial_use=1, int cc_modification=2 )">項1. 「array xnpGetRightsDetailBlock( int item_id, int use_cc=1, string text='', int cc_commercial_use=1, int cc_modification=2 )」</a> と同じ</p>

 </div>

 <div class="section" lang="ja" xml:lang="ja">

 <div xmlns="" class="titlepage">

 <div>

 <div>

 <h3 xmlns="http://www.w3.org/1999/xhtml" class="title"><a id="func-xnpGetRightsConfirmBlock-putvar"></a>3.3. 送信データ</h3>

 </div>

 </div>

 </div>

 <div class="itemizedlist">

 <ul type="disc">

 <li>

 <p>$_POST["rightsEncText"]</p>

 </li>

 <li>

 <p>$_POST["rightsUseCC"]</p>

 </li>

 <li>

 <p>$_POST["rightsCCCommercialUse"]</p>

 </li>

 <li>

 <p>$_POST["rightsCCModification"]</p>

 </li>

 </ul>

 </div>

 </div>

 <div class="section" lang="ja" xml:lang="ja">

 <div xmlns="" class="titlepage">

 <div>

 <div>

 <h3 xmlns="http://www.w3.org/1999/xhtml" class="title"><a id="func-xnpGetRightsConfirmBlock-inpval"></a>3.4. 入力</h3>

 </div>

 </div>

 </div>

 <div class="itemizedlist">

 <ul type="disc">

 <li>

 <p>maxlen : DBのカラムサイズ</p>

 </li>

 </ul>

 </div>

 </div>

 </div>

 <div class="section" lang="ja" xml:lang="ja">

 <div xmlns="" class="titlepage">

 <div>

 <div>

 <h2 xmlns="http://www.w3.org/1999/xhtml" class="title" style="clear: both"><a id="func-xnpGetRightsRegisterBlock"></a>4. array xnpGetRightsRegisterBlock( )</h2>

 </div>

 </div>

 </div>

 <p>→ <a href="rights.html#func-xnpGetRightsEditBlock" title="2. array xnpGetRightsEditBlock( int item_id, int use_cc=1, string text='', int cc_commercial_use=1, int cc_modification=2 )">項2. 「array xnpGetRightsEditBlock( int item_id, int use_cc=1, string text='', int cc_commercial_use=1, int cc_modification=2 )」</a> と同じ</p>

 </div>

 <div class="section" lang="ja" xml:lang="ja">

 <div xmlns="" class="titlepage">

 <div>

 <div>

 <h2 xmlns="http://www.w3.org/1999/xhtml" class="title" style="clear: both"><a id="func-xnpGetRights"></a>5. array xnpGetRights()</h2>

 </div>

 </div>

 </div>

 <p>Confirm 画面で送信したデータを配列 ( $text, $use_cc, $cc_commercial_use, $cc_modification ) にして返す．各アイテムタイプモジュールは，この関数で得た文字列を DB に記録する．</p>

 </div>

 </div>

 <div xmlns="http://www.w3.org/1999/xhtml" class="navfooter">



 </div>

 </div>

 </body>


