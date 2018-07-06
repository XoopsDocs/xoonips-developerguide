 <body>

 <div id="page">

 <div xmlns="http://www.w3.org/1999/xhtml" class="navheader">

 </div>

 <div xmlns="http://www.w3.org/1999/xhtml" class="book" lang="ja" id="id335815" xml:lang="ja">

 <div xmlns="" class="titlepage">

 <div>

 <div>

 <h1 xmlns="http://www.w3.org/1999/xhtml" class="title">

 <a id="id335815"></a>

 <span class="application">XooNIps</span>

 </h1>

 </div>

 <div>

 <h2 xmlns="http://www.w3.org/1999/xhtml" class="subtitle">アイテムタイプモジュール作成手順書</h2>

 </div>

 <div>

 <p class="edition">RELEASE 3.40</p>

 </div>

 <div>

 <p xmlns="http://www.w3.org/1999/xhtml" class="pubdate">2008年11月28日</p>

 </div>

 <div>

 <p xmlns="http://www.w3.org/1999/xhtml" class="copyright">Copyright © 2005-2008-NaN RIKEN (The Institute of Physical and Chemical Science Research)</p>

 </div>

 </div>

 <hr />

 </div>

 <div class="toc">

 <p>

 <b>目次</b>

 </p>

 <dl>

 <dt>

 <span class="chapter">

 <a href="intro.html">1. このドキュメントについて</a>

 </span>

 </dt>

 <dt>

 <span class="chapter">

 <a href="item.html">2. アイテムの概要</a>

 </span>

 </dt>

 <dd>

 <dl>

 <dt>

 <span class="section">

 <a href="item.html#item.basicinfo">1. Basic Information</a>

 </span>

 </dt>

 <dt>

 <span class="section">

 <a href="item.html#item.detailinfo">2. Detail Information</a>

 </span>

 </dt>

 <dt>

 <span class="section">

 <a href="item.html#item.basic-detail">3. Basic Information と Detail Information の対応</a>

 </span>

 </dt>

 </dl>

 </dd>

 <dt>

 <span class="chapter">

 <a href="itemtype.html">3. アイテムタイプモジュールの概要</a>

 </span>

 </dt>

 <dd>

 <dl>

 <dt>

 <span class="section">

 <a href="itemtype.html#itemtype.callback">1. コールバック関数</a>

 </span>

 </dt>

 <dt>

 <span class="section">

 <a href="itemtype.html#itemtype.view">2. 画面の作成</a>

 </span>

 </dt>

 <dt>

 <span class="section">

 <a href="itemtype.html#itemtype.op">3. データ操作</a>

 </span>

 </dt>

 </dl>

 </dd>

 <dt>

 <span class="chapter">

 <a href="module.html">4. モジュール管理</a>

 </span>

 </dt>

 <dd>

 <dl>

 <dt>

 <span class="section">

 <a href="module.html#module.install">1. インストール処理</a>

 </span>

 </dt>

 <dt>

 <span class="section">

 <a href="module.html#module.update">2. アップデート処理</a>

 </span>

 </dt>

 <dt>

 <span class="section">

 <a href="module.html#module.uninstall">3. アンインストール処理</a>

 </span>

 </dt>

 </dl>

 </dd>

 <dt>

 <span class="chapter">

 <a href="orm.html">5. ORMオブジェクト</a>

 </span>

 </dt>

 <dd>

 <dl>

 <dt>

 <span class="section">

 <a href="orm.html#orm.dataclass">1. データクラスの実装</a>

 </span>

 </dt>

 <dt>

 <span class="section">

 <a href="orm.html#orm.handlerclass">2. ハンドラクラスの実装</a>

 </span>

 </dt>

 </dl>

 </dd>

 <dt>

 <span class="chapter">

 <a href="commonlib.html">6. 共通ライブラリ</a>

 </span>

 </dt>

 <dd>

 <dl>

 <dt>

 <span class="section">

 <a href="commonlib.html#commonlib.basic">1. Basic Information</a>

 </span>

 </dt>

 <dt>

 <span class="section">

 <a href="commonlib.html#comomnlib.indexkeyword">2. インデックスキーワード</a>

 </span>

 </dt>

 <dt>

 <span class="section">

 <a href="commonlib.html#commonlib.detail">3. Detail Information</a>

 </span>

 </dt>

 <dd>

 <dl>

 <dt>

 <span class="section">

 <a href="commonlib.html#commonlib.detail.attachment">3.1. 添付ファイル</a>

 </span>

 </dt>

 <dt>

 <span class="section">

 <a href="commonlib.html#commonlib.detail.attachment_dl_limit">3.2. 添付ファイルのダウンロード制限</a>

 </span>

 </dt>

 <dt>

 <span class="section">

 <a href="commonlib.html#commonlib.detail.imagefile">3.3. 画像ファイル</a>

 </span>

 </dt>

 <dt>

 <span class="section">

 <a href="commonlib.html#commonlib.detail.text">3.4. テキスト</a>

 </span>

 </dt>

 </dl>

 </dd>

 </dl>

 </dd>

 <dt>

 <span class="chapter">

 <a href="register.html">7. アイテム登録</a>

 </span>

 </dt>

 <dd>

 <dl>

 <dt>

 <span class="section">

 <a href="register.html#register.form">1. 登録フォーム要求</a>

 </span>

 </dt>

 <dd>

 <dl>

 <dt>

 <span class="section">

 <a href="register.html#register.form.basic">1.1. Basic Information の登録フォーム作成</a>

 </span>

 </dt>

 <dt>

 <span class="section">

 <a href="register.html#register.form.detail">1.2. Detail Information の登録フォーム作成</a>

 </span>

 </dt>

 <dt>

 <span class="section">

 <a href="register.html#register.form.paramcheck">1.3. パラメータチェック関数</a>

 </span>

 </dt>

 <dt>

 <span class="section">

 <a href="register.html#register.form.reservedparam">1.4. 予約済みパラメータ名</a>

 </span>

 </dt>

 </dl>

 </dd>

 <dt>

 <span class="section">

 <a href="register.html#register.confirm">2. 登録内容確認フォーム要求</a>

 </span>

 </dt>

 <dd>

 <dl>

 <dt>

 <span class="section">

 <a href="register.html#register.confirm.callback">2.1. パラメータチェック関数のコールバック</a>

 </span>

 </dt>

 <dt>

 <span class="section">

 <a href="register.html#register.confirm.basic">2.2. Basic Information の登録内容確認フォーム作成</a>

 </span>

 </dt>

 <dt>

 <span class="section">

 <a href="register.html#register.confirm.detail">2.3. Detail Information の登録内容確認フォーム作成</a>

 </span>

 </dt>

 <dt>

 <span class="section">

 <a href="register.html#register.confirm.reservedparam">2.4. 予約済みパラメータ名</a>

 </span>

 </dt>

 </dl>

 </dd>

 <dt>

 <span class="section">

 <a href="register.html#register.query">3. アイテム登録要求</a>

 </span>

 </dt>

 <dd>

 <dl>

 <dt>

 <span class="section">

 <a href="register.html#register.query.basic">3.1. Basic Information の登録</a>

 </span>

 </dt>

 <dt>

 <span class="section">

 <a href="register.html#register.query.detail">3.2. Detail Information の登録</a>

 </span>

 </dt>

 </dl>

 </dd>

 </dl>

 </dd>

 <dt>

 <span class="chapter">

 <a href="edit.html">8. アイテム編集</a>

 </span>

 </dt>

 <dd>

 <dl>

 <dt>

 <span class="section">

 <a href="edit.html#edit.form">1. 編集フォーム要求</a>

 </span>

 </dt>

 <dd>

 <dl>

 <dt>

 <span class="section">

 <a href="edit.html#edit.form.basic">1.1. Basic Information の編集フォーム作成</a>

 </span>

 </dt>

 <dt>

 <span class="section">

 <a href="edit.html#edit.form.detail">1.2. Detail Information の編集フォーム作成</a>

 </span>

 </dt>

 <dt>

 <span class="section">

 <a href="edit.html#edit.form.paramcheck">1.3. パラメータチェック関数</a>

 </span>

 </dt>

 <dt>

 <span class="section">

 <a href="edit.html#edit.form.reservedparam">1.4. 予約済みパラメータ名</a>

 </span>

 </dt>

 </dl>

 </dd>

 <dt>

 <span class="section">

 <a href="edit.html#edit.confirm">2. 編集内容確認フォーム要求</a>

 </span>

 </dt>

 <dd>

 <dl>

 <dt>

 <span class="section">

 <a href="edit.html#edit.confirm.callback">2.1. パラメータチェック関数のコールバック</a>

 </span>

 </dt>

 <dt>

 <span class="section">

 <a href="edit.html#edit.confirm.modifedfilds">2.2. 変更フィールドチェック関数のコールバック</a>

 </span>

 </dt>

 <dt>

 <span class="section">

 <a href="edit.html#edit.confirm.basic">2.3. Basic Information の編集内容確認フォーム作成</a>

 </span>

 </dt>

 <dt>

 <span class="section">

 <a href="edit.html#edit.confirm.detail">2.4. Detail Information の編集内容確認フォーム作成</a>

 </span>

 </dt>

 <dt>

 <span class="section">

 <a href="edit.html#edit.confirm.reservedparam">2.5. 予約済みパラメータ名</a>

 </span>

 </dt>

 </dl>

 </dd>

 <dt>

 <span class="section">

 <a href="edit.html#edit.query">3. アイテム更新要求</a>

 </span>

 </dt>

 <dd>

 <dl>

 <dt>

 <span class="section">

 <a href="edit.html#edit.query.basic">3.1. Basic Informationの更新</a>

 </span>

 </dt>

 <dt>

 <span class="section">

 <a href="edit.html#edit.query.detail">3.2. Detail Informationの更新</a>

 </span>

 </dt>

 </dl>

 </dd>

 </dl>

 </dd>

 <dt>

 <span class="chapter">

 <a href="list.html">9. アイテム一覧</a>

 </span>

 </dt>

 <dd>

 <dl>

 <dt>

 <span class="section">

 <a href="list.html#list.summary">1. アイテム概要の生成</a>

 </span>

 </dt>

 </dl>

 </dd>

 <dt>

 <span class="chapter">

 <a href="printlist.html">10. アイテム一覧印刷用画面</a>

 </span>

 </dt>

 <dt>

 <span class="chapter">

 <a href="detail.html">11. アイテム詳細画面</a>

 </span>

 </dt>

 <dd>

 <dl>

 <dt>

 <span class="section">

 <a href="detail.html#detail.basic">1. Basic Information のフォーム生成</a>

 </span>

 </dt>

 <dt>

 <span class="section">

 <a href="detail.html#detail.detail">2. Detail Informationのフォーム生成</a>

 </span>

 </dt>

 </dl>

 </dd>

 <dt>

 <span class="chapter">

 <a href="print.html">12. アイテム詳細印刷用画面</a>

 </span>

 </dt>

 <dt>

 <span class="chapter">

 <a href="delete.html">13. アイテム削除</a>

 </span>

 </dt>

 <dd>

 <dl>

 <dt>

 <span class="section">

 <a href="delete.html#delete.basic">1. Basic Information の削除</a>

 </span>

 </dt>

 <dt>

 <span class="section">

 <a href="delete.html#delete.detail">2. Detail Information の削除</a>

 </span>

 </dt>

 </dl>

 </dd>

 <dt>

 <span class="chapter">

 <a href="metainfo.html">14. メタ情報</a>

 </span>

 </dt>

 <dd>

 <dl>

 <dt>

 <span class="section">

 <a href="metainfo.html#metainfo.basic">1. BasicInformation のメタ情報</a>

 </span>

 </dt>

 <dt>

 <span class="section">

 <a href="metainfo.html#metainfo.detail">2. Detail Information のメタ情報</a>

 </span>

 </dt>

 </dl>

 </dd>

 <dt>

 <span class="chapter">

 <a href="quicksearch.html">15. 簡易検索</a>

 </span>

 </dt>

 <dt>

 <span class="chapter">

 <a href="advancedsearch.html">16. 詳細検索</a>

 </span>

 </dt>

 <dd>

 <dl>

 <dt>

 <span class="section">

 <a href="advancedsearch.html#advancedsearch.form">1. 検索フォーム作成</a>

 </span>

 </dt>

 <dd>

 <dl>

 <dt>

 <span class="section">

 <a href="advancedsearch.html#advancedsearch.form.arguments">1.1. $search_var 引数について</a>

 </span>

 </dt>

 </dl>

 </dd>

 <dt>

 <span class="section">

 <a href="advancedsearch.html#advancedsearch.query">2. 検索クエリ (SQL) 文作成</a>

 </span>

 </dt>

 </dl>

 </dd>

 <dt>

 <span class="chapter">

 <a href="capacity.html">17. アイテム容量</a>

 </span>

 </dt>

 <dt>

 <span class="chapter">

 <a href="module_top.html">18. XooNIpsモジュールのトップ画面</a>

 </span>

 </dt>

 <dt>

 <span class="chapter">

 <a href="export.html">19. Export</a>

 </span>

 </dt>

 <dd>

 <dl>

 <dt>

 <span class="section">

 <a href="export.html#export.license">1. ライセンスの合意</a>

 </span>

 </dt>

 <dt>

 <span class="section">

 <a href="export.html#export.detail">2. Detail Information の Export</a>

 </span>

 </dt>

 </dl>

 </dd>

 <dt>

 <span class="chapter">

 <a href="import.html">20. Import</a>

 </span>

 </dt>

 <dd>

 <dl>

 <dt>

 <span class="section">

 <a href="import.html#import.classstructure">1. クラス</a>

 </span>

 </dt>

 <dt>

 <span class="section">

 <a href="import.html#import.implement.classname">2. クラス名</a>

 </span>

 </dt>

 <dt>

 <span class="section">

 <a href="import.html#import.filename">3. ファイル名，ファイルパス</a>

 </span>

 </dt>

 <dt>

 <span class="section">

 <a href="import.html#import.implement.importitem">4. インポートアイテムクラスの実装</a>

 </span>

 </dt>

 <dd>

 <dl>

 <dt>

 <span class="section">

 <a href="import.html#import.implement.importitem.members">4.1. 定義済みのメンバー変数</a>

 </span>

 </dt>

 <dt>

 <span class="section">

 <a href="import.html#import.implement.importitem.override">4.2. オーバーライドするメソッド</a>

 </span>

 </dt>

 <dt>

 <span class="section">

 <a href="import.html#import.implement.importitem.constructor">4.3. コンストラクタ</a>

 </span>

 </dt>

 </dl>

 </dd>

 <dt>

 <span class="section">

 <a href="import.html#import.implement.importitemhandler">5. インポートアイテムハンドラクラスの実装</a>

 </span>

 </dt>

 <dd>

 <dl>

 <dt>

 <span class="section">

 <a href="import.html#import.implement.importitemhandler.members">5.1. 定義済みのメンバー変数</a>

 </span>

 </dt>

 <dt>

 <span class="section">

 <a href="import.html#import.implement.importitemhandler.override">5.2. オーバーライドするメソッド</a>

 </span>

 </dt>

 <dt>

 <span class="section">

 <a href="import.html#import.implement.importitemhandler.constructor">5.3. コンストラクタ</a>

 </span>

 </dt>

 <dt>

 <span class="section">

 <a href="import.html#import.implement.importitemhandler.startelementhandler">5.4. 開始要素ハンドラ(xmlStartElementHandler)</a>

 </span>

 </dt>

 <dt>

 <span class="section">

 <a href="import.html#import.implement.importitemhandler.endelementhandler">5.5. 終了要素ハンドラ(xmlEndElementHandler)</a>

 </span>

 </dt>

 <dt>

 <span class="section">

 <a href="import.html#import.implement.importitemhandler.insert">5.6. アイテムのインサート(insert)</a>

 </span>

 </dt>

 <dt>

 <span class="section">

 <a href="import.html#import.implement.importitemhandler.setnew">5.7. アイテムのnewフラグセット(setNew)</a>

 </span>

 </dt>

 <dt>

 <span class="section">

 <a href="import.html#import.implement.importitemhandler.unsetnew">5.8. アイテムのnewフラグ解除(unsetNew)</a>

 </span>

 </dt>

 <dt>

 <span class="section">

 <a href="import.html#import.implement.importitemhandler.setdirty">5.9. アイテムのdirtyフラグセット(setDirty)</a>

 </span>

 </dt>

 <dt>

 <span class="section">

 <a href="import.html#import.implement.importitemhandler.unsetdirty">5.10. アイテムのdirtyフラグ解除(unsetDirty)</a>

 </span>

 </dt>

 <dt>

 <span class="section">

 <a href="import.html#import.implement.importitemhandler.getimportlog">5.11. インポートログの作成(getImportLog)</a>

 </span>

 </dt>

 <dt>

 <span class="section">

 <a href="import.html#import.implement.importitemhandler.attachment">5.12. 添付ファイルへの対応</a>

 </span>

 </dt>

 </dl>

 </dd>

 <dt>

 <span class="section">

 <a href="import.html#import.implement.functions">6. そのほかの関数</a>

 </span>

 </dt>

 <dd>

 <dl>

 <dt>

 <span class="section">

 <a href="import.html#import.implement.functions.seterrors">6.1. エラー関数(setErrors)</a>

 </span>

 </dt>

 </dl>

 </dd>

 </dl>

 </dd>

 <dt>

 <span class="chapter">

 <a href="oaipmh.html">21. OAI-PMH</a>

 </span>

 </dt>

 <dd>

 <dl>

 <dt>

 <span class="section">

 <a href="oaipmh.html#OAI-PMH.abstract">1. OAI-PMH処理</a>

 </span>

 </dt>

 <dd>

 <dl>

 <dt>

 <span class="section">

 <a href="oaipmh.html#OAI-PMH.SupportMetadataFormat">1.1. 対応メタデータフォーマットの列挙</a>

 </span>

 </dt>

 <dt>

 <span class="section">

 <a href="oaipmh.html#OAI-PMH.GetMetadata">1.2. メタデータの生成</a>

 </span>

 </dt>

 </dl>

 </dd>

 </dl>

 </dd>

 <dt>

 <span class="chapter">

 <a href="download_confirm.html">22. ダウンロード前の合意要求</a>

 </span>

 </dt>

 <dd>

 <dl>

 <dt>

 <span class="section">

 <a href="download_confirm.html#download_confirm.required">1. ライセンスの合意要求の有無</a>

 </span>

 </dt>

 <dt>

 <span class="section">

 <a href="download_confirm.html#download_confirm.notify">2. ダウンロードの通知の有無</a>

 </span>

 </dt>

 <dt>

 <span class="section">

 <a href="download_confirm.html#download_confirm.block">3. 合意要求ブロック</a>

 </span>

 </dt>

 </dl>

 </dd>

 <dt>

 <span class="chapter">

 <a href="changelog.html">23. 変更履歴</a>

 </span>

 </dt>

 </dl>

 </div>

 </div>

 <div xmlns="http://www.w3.org/1999/xhtml" class="navfooter">



 </div>

 </div>

 </body>


