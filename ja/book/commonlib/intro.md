# index {#index}



# XooNIps {#xoonips}



## 共通ライブラリ関数一覧



RELEASE 3.40



2008年11月28日



**概要**



`xoonips/include/lib.php`で定義された関数について説明します．ここで紹介する関数の使用法はアイテムタイプ作成手順書を参照してください．



Copyright © 2005-2008-NaN RIKEN (The Institute of Physical and Chemical Science Research)



**目次**





* 1\. はじめに

* * 1\. type function_name( argument, …. )

* 2\. 注意事項

* * 1\. 関数名の規則

 * 2\. フォーム生成関数の注意事項

* 3\. Basic Information

* * 1\. Basic Informationのデータ構造

 * 2\. Basic Informationのフォームデータ構造

 * 3\. array xnpGetBasicInformationDetailBlock( int item_id )

 * 4\. array xnpGetBasicInformationEditBlock( int item_id )

 * 5\. array xnpGetBasicInformationConfirmBlock( int item_id )

 * 6\. array xnpGetBasicInformationRegisterBlock()

 * 7\. bool xnpInsertBasicInformation( int &amp;item_id )

 * 8\. bool xnpUpdateBasicInformation( int item_id )

 * 9\. bool xnpDeleteBasicInformation( int item_id )

* 4\. Index

* * 1\. array xnpGetIndexDetailBlock( int item_id, bool button_flag = true )

 * 2\. array xnpGetIndexEditBlock( int item_id )

 * 3\. array xnpGetIndexConfirmBlock( int item_id )

 * 4\. array xnpGetIndexRegisterBlock()

 * 5\. xnpInsertIndex : (無し)

 * 6\. bool xnpUpdateIndex( int item_id )

 * 7\. xnpDeleteIndex : (無し)

* 5\. Preview

* * 1\. array xnpGetPreviewDetailBlock( int item_id )

 * 2\. array xnpGetPreviewEditBlock( int item_id )

 * 3\. array xnpGetPreviewConfirmBlock( int item_id )

 * 4\. array xnpGetPreviewRegisterBlock()

 * 5\. xnpInsertPreview : (無し)

 * 6\. bool xnpUpdatePreview( int item_id )

 * 7\. xnpDeletePreview : (無し)

* 6\. Attachment

* * 1\. array xnpGetAttachmentDetailBlock( int item_id, string name )

 * 2\. array xnpGetAttachmentEditBlock( int item_id, string name )

 * 3\. array xnpGetAttachmentConfirmBlock( int item_id, string name )

 * 4\. array xnpGetAttachmentRegisterBlock( string name )

 * 5\. xnpInsertAttachemnt : (無し)

 * 6\. bool xnpUpdateAttachment( int item_id, string name )

 * 7\. xnpDeleteAttachemnt : (無し)

 * 8\. bool xnpGetDownloadLimitationOptionRegisterBlock( string dirname, int option = 0 )

 * 9\. bool xnpGetDownloadLimitationOptionEditBlock( string dirname, int option )

 * 10\. bool xnpGetDownloadLimitationOptionConfirmBlock( string dirname )

 * 11\. bool xnpGetDownloadNotificationOptionRegisterBlock( string dirname, int option = 0 )

 * 12\. bool xnpGetDownloadNotificationOptionEditBlock( string dirname, int option )

 * 13\. bool xnpGetDownloadNotificationOptionConfirmBlock( string dirname )

 * 14\. bool xnpGetDownloadConfirmationBlock( int item_id, int download_file_id, bool attachment_dl_notify, bool use_license, int use_cc, string rights )

* 7\. TextFile

* * 1\. array xnpGetTextFileDetailBlock( int item_id, string name, string text )

 * 2\. array xnpGetTextFileEditBlock( int item_id, string name, string text )

 * 3\. array xnpGetTextFileConfirmBlock( int item_id, string name, int maxlen=65535 )

 * 4\. array xnpGetTextFileRegisterBlock( string name )

 * 5\. string xnpGetTextFile( string name )

* 8\. Rights

* * 1\. array xnpGetRightsDetailBlock( int item_id, int use_cc=1, string text=&#039;&#039;, int cc_commercial_use=1, int cc_modification=2 )

 * 2\. array xnpGetRightsEditBlock( int item_id, int use_cc=1, string text=&#039;&#039;, int cc_commercial_use=1, int cc_modification=2 )

 * 3\. array xnpGetRightsConfirmBlock( int item_id, int maxlen=65535 )

 * 4\. array xnpGetRightsRegisterBlock( )

 * 5\. array xnpGetRights()

* 9\. メタ情報

* * 1\. array xnpGetBasicInformationArray( int item_id )

 * 2\. bool xnpBasicInformation2XML( resource fhdl, array item, bool is_absolute, int base_index_id=false )

* 10\. 検索

* * 1\. array xnpGetBasicInformationAdvancedSearchBlock( string modulename, array &amp;search_var )

 * 2\. string xnpGetBasicInformationAdvancedSearchQuery( string moduleName )

 * 3\. string xnpGetKeywordQuery ( string dbVarName, string postVarName )

 * 4\. array xnpGetKeywordsQueries( array dbVarNames, array keywords )

 * 5\. array xnpKeywordsToFulltextSql( keywords )

* 11\. OAI-PMH

* * 1\. string xnpGetBasicInformationMetadata( string metadataPrefix, int item_id )

* 12\. 文字数制限

* * 1\. array xnpTrimString( string str, int length, string enc=null )

 * 2\. void xnpTrimColumn( array &amp;assoc, string table_without_prefix, array names=null, string enc=null )

 * 3\. void xnpConfirmHtml( array &amp;assoc, string table_without_prefix, array names=null, string enc=null )

 * 4\. bool xnpHasWithout( array assoc )

 * 5\. array xnpGetColumnLengths( string table_without_prefix )

 * 6\. string xnpWithinWithoutHtml( string within, string without )

* 13\. その他

* * 1\. double xnpGetTotalFileSize( array iids )

 * 2\. bool xnpIsPending( int item_id )

 * 3\. string xnpGetTopBlock( string moduleName, string displayName, string iconPath, string explanation, string subtypeVarName, array subtypes )

 * 4\. bool xnpIsAttachmentModified( string file_type_name, int item_id )

 * 5\. string xnpISO8601( int year, int month, int day )

 * 6\. string xnpDate( int year, int month, int day )

 * 7\. bool xnpExportFile( string export_path, resource fhdl, int item_id )

* 14\. 補足: Attachment, TextFile 系関数の $name 引数について

* 15\. 変更履歴

