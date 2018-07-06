# Table of Content en
## アイテムタイプモジュール作成手順書
* [このドキュメントについて](book/itemtype/intro.md)
* [アイテムの概要](book/itemtype/item.md)
 Basic Information
 Detail Information
 ja correspondence of Basic Information and Detail Information
* [アイテムタイプモジュールの概要](book/itemtype/itemtype.md)
	callback function
	Create a screen
	data manipulation
* [モジュール管理](book/itemtype/module.md)
	 installation process
	 update process
	 uninstall process
* [ORMオブジェクト](book/itemtype/orm.md)
	implementation of the data class
	implementation of the handler class
* [共通ライブラリ](book/itemtype/commonlib.md)
	Basic Information
	index keyword
	Detail Information
	3.1. Attachments
	3.2. Download attachments limit
	3.3. Image file
	3.4. Text
* [アイテム登録](book/itemtype/register.md)
	1. Registration Form request
		1.1. Registration form creation of Basic Information
		1.2. Registration form creation of Detail Information
		1.3. Parameter check function
		1.4. Reserved parameter names
	2. registration content confirmation form request
		2.1. Callback parameter check function
		2.2. Registration content confirmation form creation of Basic Information
		2.3. Registration content confirmation form creation of Detail Information
		2.4. Reserved parameter names
	3. The item registration request
		3.1. Registration of Basic Information
		3.2. Registration of Detail Information
* [アイテム編集](book/itemtype/edit.md)
	1. Edit form request
		1.1. Edit form creation of Basic Information
		1.2. Edit form creation of Detail Information
		1.3. Parameter check function
		1.4. Reserved parameter names
	2. Edit content confirmation form request
		2.1. Callback parameter check function
		2.2. Callback of change field check function
		2.3. Edit content confirmation form creation of Basic Information
		2.4. Edit content confirmation form creation of Detail Information
		2.5. Reserved parameter names
	3. item update request
		3.1. Updating the Basic Information
		3.2. Updating Detail Information
* [アイテム一覧](book/itemtype/list.md)
	1. generation of items Overview
* [アイテム一覧印刷用画面](book/itemtype/printlist.md)
* [4. Item Details screen](book/itemtype/detail.md)
	1. generation form of Basic Information
	2. generation form of Detail Information
* [12. アイテム詳細印刷用画面](book/itemtype/print.md)
* [13. アイテム削除](book/itemtype/delete.md)
	1. Delete the Basic Information
	2. Delete of Detail Information
* [14. メタ情報](book/itemtype/metainfo.md)
	1. BasicInformation meta-information
	Meta-information of 2. Detail Information
* [15. 簡易検索](book/itemtype/quicksearch.md)
* [16. 詳細検索](book/itemtype/advancedsearch.md)
	1. Search form creation
		1.1. About $ search_var argument
	1. statement create a search query (SQL)
* [17. アイテム容量](book/itemtype/capacity.md)
* [18. XooNIpsモジュールのトップ画面](book/itemtype/module_top.md)
* [19. Export](book/itemtype/export.md)
	1. license agreement)
	2. Export of Detail Information)
* [20. Import](book/itemtype/import.md)
	1. Class
	2. class name
	3. The file name, file path
	4. implementation of import items class
		4.1. Predefined member variable
		4.2. Overriding methods
		4.3. Constructor
	5. implementation of import items handler class
		5.1. Predefined member variable
		5.2. Overriding methods
		5.3. Constructor
		5.4. Start element handler (xmlStartElementHandler)
		5.5. End element handler (xmlEndElementHandler)
		5.6. The item of the insert (insert)
		5.7. Items of new flag set (setNew)
		5.8. New flag cancellation of item (unsetNew)
		5.9. Items of dirty flag set (setDirty)
		5.10. Dirty flag cancellation of item (unsetDirty)
		5.11. Creating an import log (getImportLog)
		5.12. Corresponding to the attachment
	6. Other function
		6.1. Error function (setErrors)
* [21. OAI-PMH](book/itemtype/oaipmh.md)
	1. OAI-PMH processing
	1.1. Enumeration of the corresponding meta-data format
	1.2. Generation of metadata
* [22. ダウンロード前の合意要求](book/itemtype/download_confirm.md)
    1. presence or absence of a license agreement request
	1. presence or absence of a download of notification
	2. agreement request block
	3. change history
* [23. 変更履歴](book/itemtype/changelog.md)	
## 共通ライブラリ関数一覧
* [1.はじめに](book/commonlib/intro.md)
	1. type function_name( argument, …. )
* [2. 注意事項](book/commonlib/notice.md)
	1. function name rules
	2. Notes of form generation function
* [3. Basic Information](book/commonlib/basicinfo.md)
	1. Data structure of Basic Information
	2. form data structure of Basic Information
	3. array xnpGetBasicInformationDetailBlock( int item_id )
	4. array xnpGetBasicInformationEditBlock( int item_id )
	5. array xnpGetBasicInformationConfirmBlock( int item_id )
	6. array xnpGetBasicInformationRegisterBlock()
	7. bool xnpInsertBasicInformation( int &item_id )
	8. bool xnpUpdateBasicInformation( int item_id )
	9. bool xnpDeleteBasicInformation( int item_id )
* [4. Index](book/commonlib/itemindex.md)
	1. array xnpGetIndexDetailBlock( int item_id, bool button_flag = true )
	2. array xnpGetIndexEditBlock( int item_id )
	3. array xnpGetIndexConfirmBlock( int item_id )
	4. array xnpGetIndexRegisterBlock()
	5. xnpInsertIndex: (none)
	6. bool xnpUpdateIndex( int item_id )
	7. xnpDeleteIndex: (none)
* [5. Preview](book/commonlib/preview.md)
	1. array xnpGetPreviewDetailBlock( int item_id )
	2. array xnpGetPreviewEditBlock( int item_id )
	3. array xnpGetPreviewConfirmBlock( int item_id )
	4. array xnpGetPreviewRegisterBlock()
	5. xnpInsertPreview: (none)
	6. bool xnpUpdatePreview( int item_id )
	7. xnpDeletePreview: (none)
* [6. Attachment](book/commonlib/attachment.md)
	1. array xnpGetAttachmentDetailBlock( int item_id, string name )
	2. array xnpGetAttachmentEditBlock( int item_id, string name )
	3. array xnpGetAttachmentConfirmBlock( int item_id, string name )
	4. array xnpGetAttachmentRegisterBlock( string name )
	5. xnpInsertAttachemnt: (none)
	6. bool xnpUpdateAttachment( int item_id, string name )
	7. xnpDeleteAttachemnt: (none)
	8. bool xnpGetDownloadLimitationOptionRegisterBlock( string dirname, int option = 0 )
	9. bool xnpGetDownloadLimitationOptionEditBlock( string dirname, int option )
	10. bool xnpGetDownloadLimitationOptionConfirmBlock( string dirname )
	11. bool xnpGetDownloadNotificationOptionRegisterBlock( string dirname, int option = 0 )
	12. bool xnpGetDownloadNotificationOptionEditBlock( string dirname, int option )
	13. bool xnpGetDownloadNotificationOptionConfirmBlock( string dirname )
	14. bool xnpGetDownloadConfirmationBlock( int item_id, int download_file_id, bool attachment_dl_notify, bool use_license, int use_cc, string rights )
* [7. TextFile](book/commonlib/textfile.md)
	1. array xnpGetTextFileDetailBlock( int item_id, string name, string text )
	2. array xnpGetTextFileEditBlock( int item_id, string name, string text )
	3. array xnpGetTextFileConfirmBlock( int item_id, string name, int maxlen=65535 )
	4. array xnpGetTextFileRegisterBlock( string name )
	5. string xnpGetTextFile( string name )
* [8. Rights](book/commonlib/rights.md)
	1. array xnpGetRightsDetailBlock( int item_id, int use_cc=1, string text='', int cc_commercial_use=1, int cc_modification=2 ))
	2. array xnpGetRightsEditBlock( int item_id, int use_cc=1, string text='', int cc_commercial_use=1, int cc_modification=2 ))
	3. array xnpGetRightsConfirmBlock( int item_id, int maxlen=65535 ))
	4. array xnpGetRightsRegisterBlock( ))
	5. array xnpGetRights())
* [9. メタ情報](book/commonlib/metainfo.md)
	1. array xnpGetBasicInformationArray( int item_id )
	2. bool xnpBasicInformation2XML( resource fhdl, array item, bool is_absolute, int base_index_id=false )
* [10. 検索](book/commonlib/search.md)
	array xnpGetBasicInformationAdvancedSearchBlock( string modulename, array &search_var )
	string xnpGetBasicInformationAdvancedSearchQuery( string moduleName )
	string xnpGetKeywordQuery (string dbVarName, string postVarName)
	array xnpGetKeywordsQueries( array dbVarNames, array keywords )
	array xnpKeywordsToFulltextSql( keywords )
* [11. OAI-PMH](book/commonlib/oaipmh.md)
	1. string xnpGetBasicInformationMetadata( string metadataPrefix, int item_id )
* [12. 文字数制限](book/commonlib/lengthlimit.md)
	array xnpTrimString( string str, int length, string enc=null )
	void xnpTrimColumn( array &assoc, string table_without_prefix, array names=null, string enc=null )
	void xnpConfirmHtml( array &assoc, string table_without_prefix, array names=null, string enc=null )
	bool xnpHasWithout( array assoc )
	array xnpGetColumnLengths( string table_without_prefix )
	string xnpWithinWithoutHtml( string within, string without )
* [13. その他](book/commonlib/others.md)
	1. double xnpGetTotalFileSize( array iids )
	2. bool xnpIsPending( int item_id )
	3. string xnpGetTopBlock( string moduleName, string displayName, string iconPath, string explanation, string subtypeVarName, array subtypes )
	4. bool xnpIsAttachmentModified( string file_type_name, int item_id )
	5. string xnpISO8601( int year, int month, int day )
	6. string xnpDate( int year, int month, int day )
	7. bool xnpExportFile( string export_path, resource fhdl, int item_id )
* [14. 補足: Attachment, TextFile 系関数の $name 引数について](book/commonlib/auxil.md)
* [15. 変更履歴](book/commonlib/changelog.md)
* [Credits](book/9credits.md)
* [About XOOPS CMS](book/10aboutxoops.md)