

 <body>

 <div id="page">

 <div xmlns="http://www.w3.org/1999/xhtml" class="navheader">

 </div>

 <div xmlns="http://www.w3.org/1999/xhtml" class="book" lang="ja" id="id349852" xml:lang="ja">

 <div xmlns="" class="titlepage">

 <div>

 <div>

 <h1 xmlns="http://www.w3.org/1999/xhtml" class="title">

 <a id="id349852"></a>

 <span class="application">XooNIps</span>

 </h1>

 </div>

 <div>

 <h2 xmlns="http://www.w3.org/1999/xhtml" class="subtitle">共通ライブラリ関数一覧</h2>

 </div>

 <div>

 <p class="edition">RELEASE 3.40</p>

 </div>

 <div>

 <p xmlns="http://www.w3.org/1999/xhtml" class="pubdate">2008年11月28日</p>

 </div>

 <div>

 <div xmlns="http://www.w3.org/1999/xhtml" class="abstract">

 <p class="title">

 <b>概要</b>

 </p>

 <p><code class="filename">xoonips/include/lib.php</code>で定義された関数について説明します．ここで紹介する関数の使用法はアイテムタイプ作成手順書を参照してください．</p>

 </div>

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

 <a href="intro.html">1. はじめに</a>

 </span>

 </dt>

 <dd>

 <dl>

 <dt>

 <span class="section">

 <a href="intro.html#intro-function">1. type function_name( argument, …. ) </a>

 </span>

 </dt>

 </dl>

 </dd>

 <dt>

 <span class="chapter">

 <a href="notice.html">2. 注意事項</a>

 </span>

 </dt>

 <dd>

 <dl>

 <dt>

 <span class="section">

 <a href="notice.html#notice-funcname">1. 関数名の規則</a>

 </span>

 </dt>

 <dt>

 <span class="section">

 <a href="notice.html#notice-form">2. フォーム生成関数の注意事項</a>

 </span>

 </dt>

 </dl>

 </dd>

 <dt>

 <span class="chapter">

 <a href="basicinfo.html">3. Basic Information</a>

 </span>

 </dt>

 <dd>

 <dl>

 <dt>

 <span class="section">

 <a href="basicinfo.html#basicinfo.datastructure">1. Basic Informationのデータ構造</a>

 </span>

 </dt>

 <dt>

 <span class="section">

 <a href="basicinfo.html#basicinfo.formdatastructure">2. Basic Informationのフォームデータ構造</a>

 </span>

 </dt>

 <dt>

 <span class="section">

 <a href="basicinfo.html#func-xnpGetBasicInformationDetailBlock">3. array xnpGetBasicInformationDetailBlock( int item_id )</a>

 </span>

 </dt>

 <dt>

 <span class="section">

 <a href="basicinfo.html#func-xnpGetBasicInformationEditBlock">4. array xnpGetBasicInformationEditBlock( int item_id )</a>

 </span>

 </dt>

 <dt>

 <span class="section">

 <a href="basicinfo.html#func-xnpGetBasicInformationConfirmBlock">5. array xnpGetBasicInformationConfirmBlock( int item_id )</a>

 </span>

 </dt>

 <dt>

 <span class="section">

 <a href="basicinfo.html#func-xnpGetBasicInformationRegisterBlock">6. array xnpGetBasicInformationRegisterBlock()</a>

 </span>

 </dt>

 <dt>

 <span class="section">

 <a href="basicinfo.html#func-xnpInsertBasicInformation">7. bool xnpInsertBasicInformation( int &amp;item_id )</a>

 </span>

 </dt>

 <dt>

 <span class="section">

 <a href="basicinfo.html#func-xnpUpdateBasicInformation">8. bool xnpUpdateBasicInformation( int item_id )</a>

 </span>

 </dt>

 <dt>

 <span class="section">

 <a href="basicinfo.html#func-xnpDeleteBasicInformation">9. bool xnpDeleteBasicInformation( int item_id )</a>

 </span>

 </dt>

 </dl>

 </dd>

 <dt>

 <span class="chapter">

 <a href="itemindex.html">4. Index</a>

 </span>

 </dt>

 <dd>

 <dl>

 <dt>

 <span class="section">

 <a href="itemindex.html#func-xnpGetIndexDetailBlock">1. array xnpGetIndexDetailBlock( int item_id, bool button_flag = true )</a>

 </span>

 </dt>

 <dt>

 <span class="section">

 <a href="itemindex.html#func-xnpGetIndexEditBlock">2. array xnpGetIndexEditBlock( int item_id )</a>

 </span>

 </dt>

 <dt>

 <span class="section">

 <a href="itemindex.html#func-xnpGetIndexConfirmBlock">3. array xnpGetIndexConfirmBlock( int item_id )</a>

 </span>

 </dt>

 <dt>

 <span class="section">

 <a href="itemindex.html#func-xnpGetIndexRegisterBlock">4. array xnpGetIndexRegisterBlock()</a>

 </span>

 </dt>

 <dt>

 <span class="section">

 <a href="itemindex.html#func-xnpInsertIndex">5. xnpInsertIndex : (無し)</a>

 </span>

 </dt>

 <dt>

 <span class="section">

 <a href="itemindex.html#func-xnpUpdateIndex">6. bool xnpUpdateIndex( int item_id )</a>

 </span>

 </dt>

 <dt>

 <span class="section">

 <a href="itemindex.html#func-xnpDeleteIndex">7. xnpDeleteIndex : (無し)</a>

 </span>

 </dt>

 </dl>

 </dd>

 <dt>

 <span class="chapter">

 <a href="preview.html">5. Preview</a>

 </span>

 </dt>

 <dd>

 <dl>

 <dt>

 <span class="section">

 <a href="preview.html#func-xnpGetPreviewDetailBlock">1. array xnpGetPreviewDetailBlock( int item_id )</a>

 </span>

 </dt>

 <dt>

 <span class="section">

 <a href="preview.html#func-xnpGetPreviewEditBlock">2. array xnpGetPreviewEditBlock( int item_id )</a>

 </span>

 </dt>

 <dt>

 <span class="section">

 <a href="preview.html#func-xnpGetPreviewConfirmBlock">3. array xnpGetPreviewConfirmBlock( int item_id )</a>

 </span>

 </dt>

 <dt>

 <span class="section">

 <a href="preview.html#func-xnpGetPreviewRegisterBlock">4. array xnpGetPreviewRegisterBlock()</a>

 </span>

 </dt>

 <dt>

 <span class="section">

 <a href="preview.html#func-xnpInsertPreview">5. xnpInsertPreview : (無し)</a>

 </span>

 </dt>

 <dt>

 <span class="section">

 <a href="preview.html#func-xnpUpdatePreview">6. bool xnpUpdatePreview( int item_id )</a>

 </span>

 </dt>

 <dt>

 <span class="section">

 <a href="preview.html#func-xnpDeletePreview">7. xnpDeletePreview : (無し)</a>

 </span>

 </dt>

 </dl>

 </dd>

 <dt>

 <span class="chapter">

 <a href="attachment.html">6. Attachment</a>

 </span>

 </dt>

 <dd>

 <dl>

 <dt>

 <span class="section">

 <a href="attachment.html#func-xnpGetAttachmentDetailBlock">1. array xnpGetAttachmentDetailBlock( int item_id, string name )</a>

 </span>

 </dt>

 <dt>

 <span class="section">

 <a href="attachment.html#func-xnpGetAttachmentEditBlock">2. array xnpGetAttachmentEditBlock( int item_id, string name )</a>

 </span>

 </dt>

 <dt>

 <span class="section">

 <a href="attachment.html#func-xnpGetAttachmentConfirmBlock">3. array xnpGetAttachmentConfirmBlock( int item_id, string name )</a>

 </span>

 </dt>

 <dt>

 <span class="section">

 <a href="attachment.html#func-xnpGetAttachmentRegisterBlock">4. array xnpGetAttachmentRegisterBlock( string name )</a>

 </span>

 </dt>

 <dt>

 <span class="section">

 <a href="attachment.html#func-xnpInsertAttachemnt">5. xnpInsertAttachemnt : (無し)</a>

 </span>

 </dt>

 <dt>

 <span class="section">

 <a href="attachment.html#func-xnpUpdateAttachment">6. bool xnpUpdateAttachment( int item_id, string name )</a>

 </span>

 </dt>

 <dt>

 <span class="section">

 <a href="attachment.html#func-xnpDeleteAttachment">7. xnpDeleteAttachemnt : (無し)</a>

 </span>

 </dt>

 <dt>

 <span class="section">

 <a href="attachment.html#func-xnpGetDownloadLimitationOptionRegisterBlock">8. bool xnpGetDownloadLimitationOptionRegisterBlock( string dirname, int option = 0 )</a>

 </span>

 </dt>

 <dt>

 <span class="section">

 <a href="attachment.html#func-xnpGetDownloadLimitationOptionEditBlock">9. bool xnpGetDownloadLimitationOptionEditBlock( string dirname, int option )</a>

 </span>

 </dt>

 <dt>

 <span class="section">

 <a href="attachment.html#func-xnpGetDownloadLimitationOptionConfirmBlock">10. bool xnpGetDownloadLimitationOptionConfirmBlock( string dirname )</a>

 </span>

 </dt>

 <dt>

 <span class="section">

 <a href="attachment.html#func-xnpGetDownloadNotificationOptionRegisterBlock">11. bool xnpGetDownloadNotificationOptionRegisterBlock( string dirname, int option = 0 )</a>

 </span>

 </dt>

 <dt>

 <span class="section">

 <a href="attachment.html#func-xnpGetDownloadNotificationOptionEditBlock">12. bool xnpGetDownloadNotificationOptionEditBlock( string dirname, int option )</a>

 </span>

 </dt>

 <dt>

 <span class="section">

 <a href="attachment.html#func-xnpGetDownloadNotificationOptionConfirmBlock">13. bool xnpGetDownloadNotificationOptionConfirmBlock( string dirname )</a>

 </span>

 </dt>

 <dt>

 <span class="section">

 <a href="attachment.html#func-xnpGetDownloadConfirmationBlock">14. bool xnpGetDownloadConfirmationBlock( int item_id, int download_file_id, bool attachment_dl_notify, bool use_license, int use_cc, string rights )</a>

 </span>

 </dt>

 </dl>

 </dd>

 <dt>

 <span class="chapter">

 <a href="textfile.html">7. TextFile</a>

 </span>

 </dt>

 <dd>

 <dl>

 <dt>

 <span class="section">

 <a href="textfile.html#func-xnpGetTextFileDetailBlock">1. array xnpGetTextFileDetailBlock( int item_id, string name, string text )</a>

 </span>

 </dt>

 <dt>

 <span class="section">

 <a href="textfile.html#func-xnpGetTextFileEditBlock">2. array xnpGetTextFileEditBlock( int item_id, string name, string text )</a>

 </span>

 </dt>

 <dt>

 <span class="section">

 <a href="textfile.html#func-xnpGetTextFileConfirmBlock">3. array xnpGetTextFileConfirmBlock( int item_id, string name, int maxlen=65535 )</a>

 </span>

 </dt>

 <dt>

 <span class="section">

 <a href="textfile.html#func-xnpGetTextFileRegisterBlock">4. array xnpGetTextFileRegisterBlock( string name )</a>

 </span>

 </dt>

 <dt>

 <span class="section">

 <a href="textfile.html#func-xnpGetTextFile">5. string xnpGetTextFile( string name )</a>

 </span>

 </dt>

 </dl>

 </dd>

 <dt>

 <span class="chapter">

 <a href="rights.html">8. Rights</a>

 </span>

 </dt>

 <dd>

 <dl>

 <dt>

 <span class="section">

 <a href="rights.html#func-xnpGetRightsDetailBlock">1. array xnpGetRightsDetailBlock( int item_id, int use_cc=1, string text='', int cc_commercial_use=1, int cc_modification=2 )</a>

 </span>

 </dt>

 <dt>

 <span class="section">

 <a href="rights.html#func-xnpGetRightsEditBlock">2. array xnpGetRightsEditBlock( int item_id, int use_cc=1, string text='', int cc_commercial_use=1, int cc_modification=2 )</a>

 </span>

 </dt>

 <dt>

 <span class="section">

 <a href="rights.html#func-xnpGetRightsConfirmBlock">3. array xnpGetRightsConfirmBlock( int item_id, int maxlen=65535 )</a>

 </span>

 </dt>

 <dt>

 <span class="section">

 <a href="rights.html#func-xnpGetRightsRegisterBlock">4. array xnpGetRightsRegisterBlock( )</a>

 </span>

 </dt>

 <dt>

 <span class="section">

 <a href="rights.html#func-xnpGetRights">5. array xnpGetRights()</a>

 </span>

 </dt>

 </dl>

 </dd>

 <dt>

 <span class="chapter">

 <a href="metainfo.html">9. メタ情報</a>

 </span>

 </dt>

 <dd>

 <dl>

 <dt>

 <span class="section">

 <a href="metainfo.html#func-xnpGetBasicInformationArray">1. array xnpGetBasicInformationArray( int item_id )</a>

 </span>

 </dt>

 <dt>

 <span class="section">

 <a href="metainfo.html#func-xnpBasicInformation2XML">2. bool xnpBasicInformation2XML( resource fhdl, array item, bool is_absolute, int base_index_id=false )</a>

 </span>

 </dt>

 </dl>

 </dd>

 <dt>

 <span class="chapter">

 <a href="search.html">10. 検索</a>

 </span>

 </dt>

 <dd>

 <dl>

 <dt>

 <span class="section">

 <a href="search.html#func-xnpGetBasicInformationAdvancedSearchBlock">1. array xnpGetBasicInformationAdvancedSearchBlock( string modulename, array &amp;search_var )</a>

 </span>

 </dt>

 <dt>

 <span class="section">

 <a href="search.html#func-xnpGetBasicInformationAdvancedSearchQuery">2. string xnpGetBasicInformationAdvancedSearchQuery( string moduleName )</a>

 </span>

 </dt>

 <dt>

 <span class="section">

 <a href="search.html#func-xnpGetKeywordQuery">3. string xnpGetKeywordQuery ( string dbVarName, string postVarName )</a>

 </span>

 </dt>

 <dt>

 <span class="section">

 <a href="search.html#func-xnpGetKeywordsQueries">4. array xnpGetKeywordsQueries( array dbVarNames, array keywords )</a>

 </span>

 </dt>

 <dt>

 <span class="section">

 <a href="search.html#func-xnpKeywordsToFulltextSql">5. array xnpKeywordsToFulltextSql( keywords )</a>

 </span>

 </dt>

 </dl>

 </dd>

 <dt>

 <span class="chapter">

 <a href="oaipmh.html">11. OAI-PMH</a>

 </span>

 </dt>

 <dd>

 <dl>

 <dt>

 <span class="section">

 <a href="oaipmh.html#func-xnpGetBasicInformationMetadata">1. string xnpGetBasicInformationMetadata( string metadataPrefix, int item_id )</a>

 </span>

 </dt>

 </dl>

 </dd>

 <dt>

 <span class="chapter">

 <a href="lengthlimit.html">12. 文字数制限</a>

 </span>

 </dt>

 <dd>

 <dl>

 <dt>

 <span class="section">

 <a href="lengthlimit.html#func-xnpTrimString">1. array xnpTrimString( string str, int length, string enc=null )</a>

 </span>

 </dt>

 <dt>

 <span class="section">

 <a href="lengthlimit.html#func-xnpTrimColumn">2. void xnpTrimColumn( array &amp;assoc, string table_without_prefix, array names=null, string enc=null )</a>

 </span>

 </dt>

 <dt>

 <span class="section">

 <a href="lengthlimit.html#func-xnpConfirmHtml">3. void xnpConfirmHtml( array &amp;assoc, string table_without_prefix, array names=null, string enc=null )</a>

 </span>

 </dt>

 <dt>

 <span class="section">

 <a href="lengthlimit.html#func-xnpHasWithout">4. bool xnpHasWithout( array assoc )</a>

 </span>

 </dt>

 <dt>

 <span class="section">

 <a href="lengthlimit.html#func-xnpGetColumnLengths">5. array xnpGetColumnLengths( string table_without_prefix )</a>

 </span>

 </dt>

 <dt>

 <span class="section">

 <a href="lengthlimit.html#func-xnpWithinWithoutHtml">6. string xnpWithinWithoutHtml( string within, string without )</a>

 </span>

 </dt>

 </dl>

 </dd>

 <dt>

 <span class="chapter">

 <a href="others.html">13. その他</a>

 </span>

 </dt>

 <dd>

 <dl>

 <dt>

 <span class="section">

 <a href="others.html#func-xnpGetTotalFileSize">1. double xnpGetTotalFileSize( array iids )</a>

 </span>

 </dt>

 <dt>

 <span class="section">

 <a href="others.html#func-xnpIsPending">2. bool xnpIsPending( int item_id )</a>

 </span>

 </dt>

 <dt>

 <span class="section">

 <a href="others.html#func-xnpGetTopBlock">3. string xnpGetTopBlock( string moduleName, string displayName, string iconPath, string explanation, string subtypeVarName, array subtypes )</a>

 </span>

 </dt>

 <dt>

 <span class="section">

 <a href="others.html#func-xnpIsAttachmentModified">4. bool xnpIsAttachmentModified( string file_type_name, int item_id )</a>

 </span>

 </dt>

 <dt>

 <span class="section">

 <a href="others.html#func-xnpISO8601">5. string xnpISO8601( int year, int month, int day )</a>

 </span>

 </dt>

 <dt>

 <span class="section">

 <a href="others.html#func-xnpDate">6. string xnpDate( int year, int month, int day )</a>

 </span>

 </dt>

 <dt>

 <span class="section">

 <a href="others.html#func-xnpExportFile">7. bool xnpExportFile( string export_path, resource fhdl, int item_id )</a>

 </span>

 </dt>

 </dl>

 </dd>

 <dt>

 <span class="chapter">

 <a href="auxil.html">14. 補足: Attachment, TextFile 系関数の $name 引数について</a>

 </span>

 </dt>

 <dt>

 <span class="chapter">

 <a href="changelog.html">15. 変更履歴</a>

 </span>

 </dt>

 </dl>

 </div>

 </div>

 <div xmlns="http://www.w3.org/1999/xhtml" class="navfooter">



 </div>

 </body>


