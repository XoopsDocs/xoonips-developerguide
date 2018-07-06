 <body>

 <div id="page">

 <div xmlns="http://www.w3.org/1999/xhtml" class="navheader">

 </div>

 <div xmlns="http://www.w3.org/1999/xhtml" class="chapter" lang="ja" id="itemtype" xml:lang="ja">

 <div xmlns="" class="titlepage">

 <div>

 <div>

 <h2 xmlns="http://www.w3.org/1999/xhtml" class="title"><a id="itemtype"></a>第3章 アイテムタイプモジュールの概要</h2>

 </div>

 </div>

 </div>

 <p>アイテムタイプモジュールは，<span class="application">XooNIps</span> 上のアイテム登録，編集，削除などの操作を受けて，操作に対応した画面の作成，DB の操作などを行なう <span class="application">XOOPS</span> のモジュールです．したがってアイテムタイプを追加するには <span class="application">XOOPS</span> にモジュールをインストールできる権限が必要となります．</p>

 <div class="section" lang="ja" xml:lang="ja">

 <div xmlns="" class="titlepage">

 <div>

 <div>

 <h2 xmlns="http://www.w3.org/1999/xhtml" class="title" style="clear: both"><a id="itemtype.callback"></a>1. コールバック関数</h2>

 </div>

 </div>

 </div>

 <p>アイテムの登録や編集等の，アイテムタイプごとに異なる画面や DB 操作が必要な場合には，システムがアイテムタイプの関数をコールバックして画面や DB 操作を要求します．コールバックする関数の名前，引数などは予め決まっていますので，アイテムタイプ作成者はそれに従って関数を定義します．</p>

 </div>

 <div class="section" lang="ja" xml:lang="ja">

 <div xmlns="" class="titlepage">

 <div>

 <div>

 <h2 xmlns="http://www.w3.org/1999/xhtml" class="title" style="clear: both"><a id="itemtype.view"></a>2. 画面の作成</h2>

 </div>

 </div>

 </div>

 <p>アイテムの登録，編集，表示などの画面を表示するための HTML は，アイテムタイプモジュールが生成します．作成した画面は XOOPS の中央部のカラムに挿入されます． </p>

 </div>

 <div class="section" lang="ja" xml:lang="ja">

 <div xmlns="" class="titlepage">

 <div>

 <div>

 <h2 xmlns="http://www.w3.org/1999/xhtml" class="title" style="clear: both"><a id="itemtype.op"></a>3. データ操作</h2>

 </div>

 </div>

 </div>

 <p>アイテムの登録，更新，削除，検索のデータ操作機能はアイテムタイプモジュールで実装します．ただし Basic Information の操作は共通ライブラリに予め用意されているので，アイテムタイプモジュールからその機能を呼び出して行ないます．Detail Information の操作についてはアイテム ID の対応づけ以外に規定はありません．他のアイテムタイプやシステムに影響を与えないものであれば，Detail Information をどのような方法で管理しても問題ありません．</p>

 </div>

 </div>

 <div xmlns="http://www.w3.org/1999/xhtml" class="navfooter">



 </div>

 </div>

 </body>









































