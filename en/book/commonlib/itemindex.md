



 <body>







 <div id="page">







 <div xmlns="http://www.w3.org/1999/xhtml" class="navheader">







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







 <img src="../../assets/commonlib/xnpGetIndexDetailBlock.gif" />











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







 <img src="../../assets/commonlib/xnpGetIndexEditBlock.gif" />







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







 <img src="../../assets/commonlib/xnpGetIndexConfirmBlock.gif" />







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







 <img src="../../assets/commonlib/xnpGetIndexRegisterBlock.gif" />







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



 </div>



 </div>



 </body>
