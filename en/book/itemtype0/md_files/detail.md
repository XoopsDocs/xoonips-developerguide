 <body>

 <div id="page">

 <div xmlns="http://www.w3.org/1999/xhtml" class="navheader">

 </div>

 <div xmlns="http://www.w3.org/1999/xhtml" class="chapter" lang="ja" id="detail" xml:lang="ja">

 <div xmlns="" class="titlepage">

 <div>

 <div>

 <h2 xmlns="http://www.w3.org/1999/xhtml" class="title"><a id="detail"></a>第11章 アイテム詳細画面</h2>

 </div>

 </div>

 </div>

 <p>アイテムの詳しい情報を表示します．処理の流れは図 6のとおりです．</p>

 <div class="figure">

 <a id="fig.detail.workflow"></a>

 <div class="figure-contents">

 <div class="mediaobject">

 <img src="../../assets/itemtype/detail-flow.gif" alt="アイテム詳細画面表示の流れ" />

 </div>

 </div>

 <p class="title">

 <b>図 11.1. アイテム詳細画面表示の流れ</b>

 </p>

 </div>

 <br class="figure-break" />

 <p>アイテムタイプモジュールの以下の関数に詳細画面作成処理を定義してください．システムは詳細画面が必要なときこの関数をコールバックします．</p>

 <div class="itemizedlist">

 <ul type="disc">

 <li>

 <p>function &lt;モジュール名&gt;GetDetailBlock( $item_id )</p>

 <div class="itemizedlist">

 <ul type="circle">

 <li>

 <p>引数 : アイテムID</p>

 </li>

 <li>

 <p>戻り値 : 詳細画面の HTML</p>

 </li>

 </ul>

 </div>

 </li>

 </ul>

 </div>

 <p>ユーザがアイテムを編集する権限を持つなら，詳細画面のHTMLに以下のようなフォームを含めて下さい．</p>

 <div class="blockquote">

 <blockquote class="blockquote">

 <pre class="programlisting">

&lt;form id='xoonips_edit_form'&gt;

 &lt;input type='hidden' ... &gt;

&lt;/form&gt;

 </pre>

 </blockquote>

 </div>

 <p>このフォームは詳細画面の「公開インデックスに登録」ボタンを押したときに確認画面に送信されます．

 アイテム登録画面・編集画面が送信するのと同じデータを送信するよう，適切なinputタグを入れる必要があります．

 </p>

 <p>もし詳細画面の生成で関数xnpGetAttachmentDetailBlockを使用するなら，引数download_file_idをxnpGetDownloadConfirmationBlockに渡し，その結果をHTMLに含めてください．</p>

 <div class="section" lang="ja" xml:lang="ja">

 <div xmlns="" class="titlepage">

 <div>

 <div>

 <h2 xmlns="http://www.w3.org/1999/xhtml" class="title" style="clear: both"><a id="detail.basic"></a>1. Basic Information のフォーム生成</h2>

 </div>

 </div>

 </div>

 <p>共通ライブラリに Basic Information の詳細画面用フォームを作成する関数があります．その関数を呼び出して，Basic Information のフォームを取得します．Basic Information のフィールド毎のフォームが得られるので，その中から必要なフィールドを取り出して組合せ，Basic Information の詳細画面を作成します．</p>

 <p>以下の項目も参照してください．</p>

 <div class="itemizedlist">

 <ul type="disc">

 <li>

 <p>xnpGetBasicInformationDetailBlock</p>

 </li>

 </ul>

 </div>

 </div>

 <div class="section" lang="ja" xml:lang="ja">

 <div xmlns="" class="titlepage">

 <div>

 <div>

 <h2 xmlns="http://www.w3.org/1999/xhtml" class="title" style="clear: both"><a id="detail.detail"></a>2. Detail Informationのフォーム生成</h2>

 </div>

 </div>

 </div>

 <p>Detail Information の詳細画面の作成はアイテムタイプで自由に定義できます．添付ファイル，インデックス，画像などは共有ライブラリに関数が用意されているのでそれを利用できます．</p>

 <p>最後に，Basic Information と Detail Information のフォームをまとめて戻り値とします．</p>

 <p>以下の項目も参照してください．</p>

 <div class="itemizedlist">

 <ul type="disc">

 <li>

 <p>xnpGetPreviewDetailBlock</p>

 </li>

 <li>

 <p>xnpGetAttachmentDetailBlock</p>

 </li>

 <li>

 <p>xnpGetTextFileDetailBlock</p>

 </li>

 <li>

 <p>xnpGetRightsDetailBlock</p>

 </li>

 <li>

 <p>xnpGetIndexDetailBlock</p>

 </li>

 </ul>

 </div>

 </div>

 </div>

 <div xmlns="http://www.w3.org/1999/xhtml" class="navfooter">



 </div>

 <div class="lastupdated">Last updated: 2010/04/15</div>

 </div>

 </body>




