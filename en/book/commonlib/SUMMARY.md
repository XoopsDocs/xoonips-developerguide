# Table of Content (in - book - commonlib)

## Item type module creation procedure manual

* [About this document](book/itemtype/intro.md)

* [Overview of items](book/itemtype/item.md)

* Basic Information

* Detail Information

* en book  commonlib correspondence of Basic Information and Detail Information

[Overview of the item type module](book/itemtype/itemtype.md)

* callback function

* Create a screen

* data manipulation

[The module management](book/itemtype/module.md)

* installation process

* update process

* uninstall process

[ORM object](book/itemtype/orm.md)

* implementation of the data class

* implementation of the handler class

[common library](book/itemtype/commonlib.md)

* Basic Information

* index keyword

* Detail Information

3.1. Attachments

3.2. Download attachments limit

3.3. Image file

3.4. Text

[1. item registration](book/itemtype/register.md)

2. Registration Form request

1.1. Registration form creation of Basic Information

1.2. Registration form creation of Detail Information

1.3. Parameter check function

1.4. Reserved parameter names

1. registration content confirmation form request

2.1. Callback parameter check function

2.2. Registration content confirmation form creation of Basic Information

2.3. Registration content confirmation form creation of Detail Information

2.4. Reserved parameter names

1. The item registration request

3.1. Registration of Basic Information

3.2. Registration of Detail Information

[1. item editing](book/itemtype/edit.md)

2. edit form request

1.1. Edit form creation of Basic Information

1.2. Edit form creation of Detail Information

1.3. Parameter check function

1.4. Reserved parameter names

1. Edit content confirmation form request

2.1. Callback parameter check function

2.2. Callback of change field check function

2.3. Edit content confirmation form creation of Basic Information

2.4. Edit content confirmation form creation of Detail Information

2.5. Reserved parameter names

1. item update request

3.1. Updating the Basic Information

3.2. Updating Detail Information

[1. Item List](book/itemtype/list.md)

2. generation of items Overview

[3. Item List Printable](book/itemtype/printlist.md)

[4. Item Details screen](book/itemtype/detail.md)

5. generation form of Basic Information

6. generation form of Detail Information

[7. Item Details Printable](book/itemtype/print.md)

[8. Delete Items](book/itemtype/delete.md)

9. Delete the Basic Information

Delete of 2. Detail Information

[1. meta-information](book/itemtype/metainfo.md)

2. BasicInformation meta-information

Meta-information of 2. Detail Information

[1. Simple Search](book/itemtype/quicksearch.md)

[2. Advanced Search](book/itemtype/advancedsearch.md)

3. Search form creation

1.1. About $ search\_var argument

1. statement create a search query \(SQL\)

[2. Items capacity](book/itemtype/capacity.md)

[The top screen of 18. XooNIps module](book/itemtype/module_top.md)

[1. Export](book/itemtype/export.md)

2. license agreement)

3. Export of Detail Information)

[4. Import](book/itemtype/import.md)

5. Class

6. class name

7. The file name, file path

8. implementation of import items class

4.1. Predefined member variable

4.2. Overriding methods

4.3. Constructor

1. implementation of import items handler class

5.1. Predefined member variable

5.2. Overriding methods

5.3. Constructor

5.4. Start element handler \(xmlStartElementHandler\)

5.5. End element handler \(xmlEndElementHandler\)

5.6. The item of the insert \(insert\)

5.7. Items of new flag set \(setNew\)

5.8. New flag cancellation of item \(unsetNew\)

5.9. Items of dirty flag set \(setDirty\)

5.10. Dirty flag cancellation of item \(unsetDirty\)

5.11. Creating an import log \(getImportLog\)

5.12. Corresponding to the attachment

1. Other function

6.1. Error function \(setErrors\)

[1. OAI-PMH](book/itemtype/oaipmh.md)

2. OAI-PMH processing

1.1. Enumeration of the corresponding meta-data format

1.2. Generation of metadata

1. Download previous agreement request

[2. presence or absence of a license agreement request](book/itemtype/)

3. presence or absence of a download of notification

4. agreement request block

5. change history

##Common library function list

[1.First of all](book/commonlib/intro.md)

 1. type function_name( argument, …. )

[2. Notes](book/commonlib/notice.md)

1. function name rules

2. Notes of form generation function

[3. Basic Information](book/commonlib/basicinfo.md)

1. Data structure of Basic Information

2. form data structure of Basic Information

3. array xnpGetBasicInformationDetailBlock( int item_id )

4. array xnpGetBasicInformationEditBlock( int item_id )

5. array xnpGetBasicInformationConfirmBlock( int item_id )

6. array xnpGetBasicInformationRegisterBlock()

7. bool xnpInsertBasicInformation( int &item_id )

8. bool xnpUpdateBasicInformation( int item_id )

9. bool xnpDeleteBasicInformation( int item_id )

[4. Index](book/commonlib/itemindex.md)

1. array xnpGetIndexDetailBlock( int item_id, bool button_flag = true )

2. array xnpGetIndexEditBlock( int item_id )

3. array xnpGetIndexConfirmBlock( int item_id )

4. array xnpGetIndexRegisterBlock()

5. xnpInsertIndex: (none)

6. bool xnpUpdateIndex( int item_id )

7. xnpDeleteIndex: (none)

[5. Preview](book/commonlib/preview.md)

1. array xnpGetPreviewDetailBlock( int item_id )

2. array xnpGetPreviewEditBlock( int item_id )

3. array xnpGetPreviewConfirmBlock( int item_id )

4. array xnpGetPreviewRegisterBlock()

5. xnpInsertPreview: (none)

6. bool xnpUpdatePreview( int item_id )

7. xnpDeletePreview: (none)

[6. Attachment](book/commonlib/attachment.md)

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

[7. TextFile](book/commonlib/textfile.md)

1. array xnpGetTextFileDetailBlock( int item_id, string name, string text )

2. array xnpGetTextFileEditBlock( int item_id, string name, string text )

3. array xnpGetTextFileConfirmBlock( int item_id, string name, int maxlen=65535 )

4. array xnpGetTextFileRegisterBlock( string name )

5. string xnpGetTextFile( string name )

[8. Rights](book/commonlib/rights.md)

1. array xnpGetRightsDetailBlock( int item_id, int use_cc=1, string text='', int cc_commercial_use=1, int cc_modification=2 ))

2. array xnpGetRightsEditBlock( int item_id, int use_cc=1, string text='', int cc_commercial_use=1, int cc_modification=2 ))

3. array xnpGetRightsConfirmBlock( int item_id, int maxlen=65535 ))

4. array xnpGetRightsRegisterBlock( ))

5. array xnpGetRights())

[9. meta-information](book/commonlib/metainfo.md)

1. array xnpGetBasicInformationArray( int item_id )

2. bool xnpBasicInformation2XML( resource fhdl, array item, bool is_absolute, int base_index_id=false )

[10. Search](book/commonlib/search.md)

1. array xnpGetBasicInformationAdvancedSearchBlock( string modulename, array &search_var )

2. string xnpGetBasicInformationAdvancedSearchQuery( string moduleName )

3. string xnpGetKeywordQuery (string dbVarName, string postVarName)

4. array xnpGetKeywordsQueries( array dbVarNames, array keywords )

5. array xnpKeywordsToFulltextSql( keywords )

[11. OAI-PMH](book/commonlib/oaipmh.md)

1. string xnpGetBasicInformationMetadata( string metadataPrefix, int item_id )

[12. The system limits the number of characters](book/commonlib/lengthlimit.md)

1. array xnpTrimString( string str, int length, string enc=null )

2. void xnpTrimColumn( array &assoc, string table_without_prefix, array names=null, string enc=null )

3. void xnpConfirmHtml( array &assoc, string table_without_prefix, array names=null, string enc=null )

4. bool xnpHasWithout( array assoc )

5. array xnpGetColumnLengths( string table_without_prefix )

6. string xnpWithinWithoutHtml( string within, string without )

[13. Other](book/commonlib/others.md)

1. double xnpGetTotalFileSize( array iids )

2. bool xnpIsPending( int item_id )

3. string xnpGetTopBlock( string moduleName, string displayName, string iconPath, string explanation, string subtypeVarName, array subtypes )

4. bool xnpIsAttachmentModified( string file_type_name, int item_id )

5. string xnpISO8601( int year, int month, int day )

6. string xnpDate( int year, int month, int day )

7. bool xnpExportFile( string export_path, resource fhdl, int item_id )

[14. Supplement: Attachment, for $ name argument of TextFile system function](book/commonlib/auxil.md)

[15. Biangenglvli](book/commonlib/changelog.md)

* [Credits](book/9credits.md)

* [About XOOPS CMS](book/10aboutxoops.md)




