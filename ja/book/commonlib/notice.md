 <body>

 <div id="page">

 <div xmlns="http://www.w3.org/1999/xhtml" class="navheader">

 </div>

 <div xmlns="http://www.w3.org/1999/xhtml" class="chapter" lang="ja" id="notice" xml:lang="ja">

 <div xmlns="" class="titlepage">

 <div>

 <div>

 <h2 xmlns="http://www.w3.org/1999/xhtml" class="title"><a id="notice"></a>第2章 注意事項</h2>

 </div>

 </div>

 </div>

 <p>ここで紹介する関数は，フォームを生成する関数とデータベースを操作する関数に大別されます．関数は以下の規則で命名されています．</p>

 <div class="section" lang="ja" xml:lang="ja">

 <div xmlns="" class="titlepage">

 <div>

 <div>

 <h2 xmlns="http://www.w3.org/1999/xhtml" class="title" style="clear: both"><a id="notice-funcname"></a>1. 関数名の規則</h2>

 </div>

 </div>

 </div>

 <div class="section" lang="ja" xml:lang="ja">

 <div xmlns="" class="titlepage">

 <div>

 <div>

 <h3 xmlns="http://www.w3.org/1999/xhtml" class="title"><a id="notice-funcname-form"></a>1.1. フォーム生成関数</h3>

 </div>

 </div>

 </div>

 <p>フォーム生成のための関数名は一部の例外を除き以下の規則に従います．</p>

 <div class="blockquote">

 <blockquote class="blockquote">

 <pre class="programlisting">xnpGet&lt;TYPE&gt;&lt;METHOD&gt;Block( 引数 )</pre>

 </blockquote>

 </div>

 <div class="itemizedlist">

 <ul type="disc">

 <li>

 <p>&lt;TYPE&gt;</p>

 <div class="itemizedlist">

 <ul type="circle">

 <li>

 <p>BasicInformation : アイテム基本情報</p>

 </li>

 <li>

 <p>Index : インデックス</p>

 </li>

 <li>

 <p>Preview : 添付画像</p>

 </li>

 <li>

 <p>Attachment : 添付ファイル</p>

 </li>

 <li>

 <p>TextFile : テキスト(長文入力)</p>

 </li>

 <li>

 <p>Rights : ライセンス</p>

 </li>

 </ul>

 </div>

 </li>

 <li>

 <p>&lt;METHOD&gt;</p>

 <div class="itemizedlist">

 <ul type="circle">

 <li>

 <p>Detail : アイテム詳細表示画面を生成するときに呼び出されます．</p>

 </li>

 <li>

 <p>Confirm : アイテム内容確認画面を生成するときに呼び出されます．</p>

 </li>

 <li>

 <p>Register : アイテム登録画面を生成するときに呼び出されます．</p>

 </li>

 <li>

 <p>Edit : アイテム編集画面を生成するときに呼び出されます．</p>

 </li>

 <li>

 <p>PrinterFriendly : 印刷用画面を生成するときに呼び出されます．(内部処理はほぼ Detail と同じなので，個々の関数の解説は省略します．)</p>

 </li>

 </ul>

 </div>

 </li>

 </ul>

 </div>

 <p>上から解かるように，例えばアイテム内容確認画面にインデックスを表示するための関数は xnpGetIndexDetailBlock となります．</p>

 </div>

 <div class="section" lang="ja" xml:lang="ja">

 <div xmlns="" class="titlepage">

 <div>

 <div>

 <h3 xmlns="http://www.w3.org/1999/xhtml" class="title"><a id="notice-funcname-db"></a>1.2. データベース操作関数</h3>

 </div>

 </div>

 </div>

 <p>アイテムの登録，編集，削除などの操作を行なう関数名は一部の例外を除き以下の規則に従います．</p>

 <div class="blockquote">

 <blockquote class="blockquote">

 <pre class="programlisting">xnp&lt;METHOD&gt;&lt;TYPE&gt; ( 引数 )</pre>

 </blockquote>

 </div>

 <div class="itemizedlist">

 <ul type="disc">

 <li>

 <p>&lt;TYPE&gt;</p>

 <div class="itemizedlist">

 <ul type="circle">

 <li>

 <p>(フォーム生成関数と同じなので省略)</p>

 </li>

 </ul>

 </div>

 </li>

 <li>

 <p>&lt;METHOD&gt;</p>

 <div class="itemizedlist">

 <ul type="circle">

 <li>

 <p>Insert : データベースに情報を登録します．</p>

 </li>

 <li>

 <p>Update : データベースにある情報に上書きします．</p>

 </li>

 <li>

 <p>Delete : データベースから情報を削除します．</p>

 </li>

 </ul>

 </div>

 </li>

 </ul>

 </div>

 <p>※ Update 関数が Insert を兼ねるものもあります．(Index，Preview など)</p>

 <p>※ Basic Information の削除と同時に Delete を実行するものもあります．(Preview，Attatchment など)</p>

 </div>

 </div>

 <div class="section" lang="ja" xml:lang="ja">

 <div xmlns="" class="titlepage">

 <div>

 <div>

 <h2 xmlns="http://www.w3.org/1999/xhtml" class="title" style="clear: both"><a id="notice-form"></a>2. フォーム生成関数の注意事項</h2>

 </div>

 </div>

 </div>

 <div class="itemizedlist">

 <ul type="disc">

 <li>

 <p>生成したテキストだけではフォームとして機能しません．</p>

 <p>関数が生成したフォームは &lt;form&gt; タグを含まないことに注意してください．&lt;form&gt; タグの内側に使用できる HTML だけを生成します．従って，生成結果単体ではフォームとして不完全です．関数を呼び出した側で &lt;form&gt; タグを定義して利用してください．</p>

 </li>

 <li>

 <p>JavaScript の定義が必要なフォームがあります．</p>

 <p>関数が生成したフォームと &lt;form&gt; タグの定義だけでは動作しないものもあります．JavaScript の定義が必要か否かは関数によって異なります．定義が必要な場合は，その関数の説明の中に JavaScriptが 記載されています． &lt;form&gt; タグの定義とあわせて HTML にその JavaScript を定義してください．</p>

 </li>

 <li>

 <p>生成したフォームは連想配列で出力されます．</p>

 <p>関数は連想配列を返します．連想配列の構造は以下の通りです．</p>

 <div class="itemizedlist">

 <ul type="circle">

 <li>

 <p>&lt;TYPE&gt;がBasicInformationの場合</p>

 <div class="blockquote">

 <blockquote class="blockquote">

 <pre class="programlisting">array(

 'フィールド名' =&gt; array(

 'name'=&gt;'表示フィールド名',

 'value'=&gt;'表示フィールド値'

 'within'=&gt;'フィールド値のDBに書き込める部分' /* Confirmの場合だけ存在する */

 'without'=&gt;'フィールド値のDBに書き込めない部分' /* Confirmの場合だけ存在する */

 ),

 (繰り返し) …

 'hidden' =&gt; '表示hidden値' /* Detailの場合だけ存在する */

)</pre>

 </blockquote>

 </div>

 </li>

 <li>

 <p>&lt;TYPE&gt;がBasicInformation以外の場合</p>

 <div class="blockquote">

 <blockquote class="blockquote">

 <pre class="programlisting">array(

 'name'=&gt;'表示フィールド名',

 'value'=&gt;'表示フィールド値'

 'within'=&gt;'フィールド値のDBに書き込める部分' /* Confirmの場合だけ存在する */

 'without'=&gt;'フィールド値のDBに書き込めない部分' /* Confirmの場合だけ存在する */

 'hidden' =&gt; '表示hidden値' /* Detailの場合だけ存在する */

)</pre>

 </blockquote>

 </div>

 </li>

 </ul>

 </div>

 <p>Basic Information の登録，編集，確認，詳細表示フォームは，タイトル，コメントといったフィールド毎に分割して生成されます．関数を呼び出した側が必要とするフィールドだけを組合せてフォームの形にして利用してください．</p>

 <p>これは，アイテムタイプ作成者がアイテムタイプにとって必要なフィールドだけを選んで登録，編集，閲覧画面を作成するための枠組みです．この枠組みによって，登録画面にタイトルとコメントしかないアイテムタイプも可能になります．</p>

 <p>フィールド名には 'titile', 'keywords' などのフィールドを識別するための内部処理用の文字列が入ります．</p>

 <p>表示フィールド名は画面に出力するためのフィールド名です．表示フィールド値はデータベースや変数で与えられた具体的な値です．登録や編集の場合はフォームの HTML になることもあります．</p>

 <p>&lt;METHOD&gt;がDetailの場合だけ，特別なキー'hidden'があります． この場合，登録画面・編集画面と同じデータを送信するための見えないinputタグが 表示hidden値 として設定されます． 以降の章では特に記述しませんが，全てのxnpGet〜DetailBlockについてこのキーが存在します． </p>

 <p>&lt;METHOD&gt;がConfirmの場合だけ，特別なキー'within' 'without'があります． この場合，'within'にはDBに書き込める部分が、'without'にはDBに書き込めない部分(DBのカラムサイズによる)が設定されます．

 以降の章では特に記述しませんが，valueが文字列型ならこのキーが存在します． </p>

 </li>

 </ul>

 </div>

 </div>

 </div>

 <div xmlns="http://www.w3.org/1999/xhtml" class="navfooter">



 </body>


