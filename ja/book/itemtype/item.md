 <body>

 <div id="page">

 <div xmlns="http://www.w3.org/1999/xhtml" class="navheader">

 </div>

 <div xmlns="http://www.w3.org/1999/xhtml" class="chapter" lang="ja" id="item" xml:lang="ja">

 <div xmlns="" class="titlepage">

 <div>

 <div>

 <h2 xmlns="http://www.w3.org/1999/xhtml" class="title"><a id="item"></a>第2章 アイテムの概要</h2>

 </div>

 </div>

 </div>

 <p>アイテムの情報は以下の様に Basic Information と Detail Information に分けられます．</p>

 <div class="section" lang="ja" xml:lang="ja">

 <div xmlns="" class="titlepage">

 <div>

 <div>

 <h2 xmlns="http://www.w3.org/1999/xhtml" class="title" style="clear: both"><a id="item.basicinfo"></a>1. Basic Information</h2>

 </div>

 </div>

 </div>

 <p>アイテムタイプに拘らずすべてのアイテムが所有する情報(フィールド)を Basic Information と呼びます．これには以下の項目があります．</p>

 <div class="itemizedlist">

 <ul type="disc">

 <li>

 <p>タイトル</p>

 </li>

 <li>

 <p>キーワード</p>

 </li>

 <li>

 <p>コメント</p>

 </li>

 <li>

 <p>DOI</p>

 </li>

 <li>

 <p>アイテムの内容物に関する年月日<sup>[<a id="id360007" href="#ftn.id360007">1</a>]</sup>

 </p>

 </li>

 <li>

 <p>作成ユーザ</p>

 </li>

 <li>

 <p>作成日</p>

 </li>

 <li>

 <p>最終更新日</p>

 </li>

 <li>

 <p>言語</p>

 </li>

 </ul>

 </div>

 <p>これらのうち，作成ユーザ，作成日，最終更新日はシステムが決定します．ユーザは指定できません．</p>

 <p>Basic Information の DB への登録や DB からの取得，パラメータチェック，フォーム作成処理の一部はシステムが担当します．アイテムタイプモジュール作成者はこれらの処理を作成する必要はありません．共通ライブラリに関数の形で提供されるので，必要に応じて呼び出して使用します．</p>

 </div>

 <div class="section" lang="ja" xml:lang="ja">

 <div xmlns="" class="titlepage">

 <div>

 <div>

 <h2 xmlns="http://www.w3.org/1999/xhtml" class="title" style="clear: both"><a id="item.detailinfo"></a>2. Detail Information</h2>

 </div>

 </div>

 </div>

 <p>Basic Information に含まれないアイテムタイプ固有の情報を指します．Detail Information の取扱いはすべてアイテムタイプモジュールが行ないます．記録方法や処理方法はアイテムタイプで自由に決定できます．</p>

 </div>

 <div class="section" lang="ja" xml:lang="ja">

 <div xmlns="" class="titlepage">

 <div>

 <div>

 <h2 xmlns="http://www.w3.org/1999/xhtml" class="title" style="clear: both"><a id="item.basic-detail"></a>3. Basic Information と Detail Information の対応</h2>

 </div>

 </div>

 </div>

 <p>前述の様に 1つのアイテムに関する情報が，Basic Information と Detail Information の二つに分かれて管理されます．両者の対応をとるためにアイテム ID が存在します．アイテムタイプモジュールは，システムから与えられるアイテム ID と Detail Information を対応付けて管理してください．システムは同じアイテム ID を持つ Basic Information と Detail Information を 1つのアイテムとして取り扱います(<a href="item.html#fig.item.basic-detail.example" title="図 2.1. アイテム ID による対応付け (例)">図 2.1. 「アイテム ID による対応付け (例)」</a>)．</p>

 <div class="figure">

 <a id="fig.item.basic-detail.example"></a>

 <div class="figure-contents">

 <div class="mediaobject">

 <img src="../../assets/itemtype/relation.gif" alt="アイテム ID による対応付け (例)" />

 </div>

 </div>

 <p class="title">

 <b>図 2.1. アイテム ID による対応付け (例)</b>

 </p>

 </div>

 <br class="figure-break" />

 </div>

 <div class="footnotes">

 <br />

 <hr width="100" align="left" />

 <div class="footnote">

 <p><sup>[<a id="ftn.id360007" href="#id360007">1</a>] </sup>アイテムが論文なら論文発行日，プログラムならリリース年月日などを指定します．年月日が何を意味するかはアイテムタイプによって変わります．年月日を使わないアイテムタイプもあります．</p>

 </div>

 </div>

 </div>

 <div xmlns="http://www.w3.org/1999/xhtml" class="navfooter">



 </div>

 </div>

 </body>


