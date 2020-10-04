# Table of Content en

## Item type module creation procedure manual

* [About this document]()
* [Overview of items](https://github.com/XoopsDocs/xoonips-developerguide/tree/a6a58e91b3c2fbad05284b6a55d66570e12e94d6/en/book/itemtype/item.md)

    Basic Information

    Detail Information

    en correspondence of Basic Information and Detail Information

* [Overview of the item type module]()

    callback function

    Create a screen

    data manipulation

* [The module management]()

     installation process

     update process

     uninstall process

* [ORM object]()

    implementation of the data class

    implementation of the handler class

* [Common Library](https://github.com/XoopsDocs/xoonips-developerguide/tree/a6a58e91b3c2fbad05284b6a55d66570e12e94d6/en/book/itemtype/commonlib.md)

    Basic Information

    index keyword

    Detail Information

    3.1. Attachments

    3.2. Download attachments limit

    3.3. Image file

    3.4. Text

* [Item Registration](https://github.com/XoopsDocs/xoonips-developerguide/tree/a6a58e91b3c2fbad05284b6a55d66570e12e94d6/en/book/itemtype/register.md)
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
* [Item Editing](https://github.com/XoopsDocs/xoonips-developerguide/tree/a6a58e91b3c2fbad05284b6a55d66570e12e94d6/en/book/itemtype/edit.md)
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
* [Item List](https://github.com/XoopsDocs/xoonips-developerguide/tree/a6a58e91b3c2fbad05284b6a55d66570e12e94d6/en/book/itemtype/list.md)
  1. generation of items Overview
* [Item List Printable](https://github.com/XoopsDocs/xoonips-developerguide/tree/a6a58e91b3c2fbad05284b6a55d66570e12e94d6/en/book/itemtype/printlist.md)
* [4. Item Details screen](https://github.com/XoopsDocs/xoonips-developerguide/tree/a6a58e91b3c2fbad05284b6a55d66570e12e94d6/en/book/itemtype/detail.md)
  1. generation form of Basic Information
  2. generation form of Detail Information
* [7. Item Details Printable](https://github.com/XoopsDocs/xoonips-developerguide/tree/a6a58e91b3c2fbad05284b6a55d66570e12e94d6/en/book/itemtype/print.md)
* [8. Delete Items](https://github.com/XoopsDocs/xoonips-developerguide/tree/a6a58e91b3c2fbad05284b6a55d66570e12e94d6/en/book/itemtype/delete.md)
  1. Delete the Basic Information
  2. Delete of Detail Information
* [1. meta-information](https://github.com/XoopsDocs/xoonips-developerguide/tree/a6a58e91b3c2fbad05284b6a55d66570e12e94d6/en/book/itemtype/metainfo.md)
  1. BasicInformation meta-information

     Meta-information of 2. Detail Information
* [1. Simple Search](https://github.com/XoopsDocs/xoonips-developerguide/tree/a6a58e91b3c2fbad05284b6a55d66570e12e94d6/en/book/itemtype/quicksearch.md)
* [2. Advanced Search](https://github.com/XoopsDocs/xoonips-developerguide/tree/a6a58e91b3c2fbad05284b6a55d66570e12e94d6/en/book/itemtype/advancedsearch.md)
  1. Search form creation

      1.1. About $search\_var argument

  2. statement create a search query \(SQL\)
* [2. Items capacity](https://github.com/XoopsDocs/xoonips-developerguide/tree/a6a58e91b3c2fbad05284b6a55d66570e12e94d6/en/book/itemtype/capacity.md)
* [The top screen of 18. XooNIps module](https://github.com/XoopsDocs/xoonips-developerguide/tree/a6a58e91b3c2fbad05284b6a55d66570e12e94d6/en/book/itemtype/module_top.md)
* [1. Export](https://github.com/XoopsDocs/xoonips-developerguide/tree/a6a58e91b3c2fbad05284b6a55d66570e12e94d6/en/book/itemtype/export.md)
  1. license agreement\)
  2. Export of Detail Information\)
* [4. Import](https://github.com/XoopsDocs/xoonips-developerguide/tree/a6a58e91b3c2fbad05284b6a55d66570e12e94d6/en/book/itemtype/import.md)
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

      5.4. Start element handler \(xmlStartElementHandler\)

      5.5. End element handler \(xmlEndElementHandler\)

      5.6. The item of the insert \(insert\)

      5.7. Items of new flag set \(setNew\)

      5.8. New flag cancellation of item \(unsetNew\)

      5.9. Items of dirty flag set \(setDirty\)

      5.10. Dirty flag cancellation of item \(unsetDirty\)

      5.11. Creating an import log \(getImportLog\)

      5.12. Corresponding to the attachment

  6. Other function

      6.1. Error function \(setErrors\)
* [1. OAI-PMH](https://github.com/XoopsDocs/xoonips-developerguide/tree/a6a58e91b3c2fbad05284b6a55d66570e12e94d6/en/book/itemtype/oaipmh.md)
  1. OAI-PMH processing

     1.1. Enumeration of the corresponding meta-data format

     1.2. Generation of metadata

  2. Download previous agreement request
* [2. presence or absence of a license agreement request]()
  1. presence or absence of a download of notification
  2. agreement request block
  3. change history

     **Common library function list**
* [1.First of all]()
  1. type function\_name\( argument, …. \)
* [2. Notes]()
  1. function name rules
  2. Notes of form generation function
* [3. Basic Information]()
  1. Data structure of Basic Information
  2. form data structure of Basic Information
  3. array xnpGetBasicInformationDetailBlock\( int item\_id \)
  4. array xnpGetBasicInformationEditBlock\( int item\_id \)
  5. array xnpGetBasicInformationConfirmBlock\( int item\_id \)
  6. array xnpGetBasicInformationRegisterBlock\(\)
  7. bool xnpInsertBasicInformation\( int &item\_id \)
  8. bool xnpUpdateBasicInformation\( int item\_id \)
  9. bool xnpDeleteBasicInformation\( int item\_id \)
* [4. Index]()
  1. array xnpGetIndexDetailBlock\( int item\_id, bool button\_flag = true \)
  2. array xnpGetIndexEditBlock\( int item\_id \)
  3. array xnpGetIndexConfirmBlock\( int item\_id \)
  4. array xnpGetIndexRegisterBlock\(\)
  5. xnpInsertIndex: \(none\)
  6. bool xnpUpdateIndex\( int item\_id \)
  7. xnpDeleteIndex: \(none\)
* [5. Preview]()
  1. array xnpGetPreviewDetailBlock\( int item\_id \)
  2. array xnpGetPreviewEditBlock\( int item\_id \)
  3. array xnpGetPreviewConfirmBlock\( int item\_id \)
  4. array xnpGetPreviewRegisterBlock\(\)
  5. xnpInsertPreview: \(none\)
  6. bool xnpUpdatePreview\( int item\_id \)
  7. xnpDeletePreview: \(none\)
* [6. Attachment]()
  1. array xnpGetAttachmentDetailBlock\( int item\_id, string name \)
  2. array xnpGetAttachmentEditBlock\( int item\_id, string name \)
  3. array xnpGetAttachmentConfirmBlock\( int item\_id, string name \)
  4. array xnpGetAttachmentRegisterBlock\( string name \)
  5. xnpInsertAttachemnt: \(none\)
  6. bool xnpUpdateAttachment\( int item\_id, string name \)
  7. xnpDeleteAttachemnt: \(none\)
  8. bool xnpGetDownloadLimitationOptionRegisterBlock\( string dirname, int option = 0 \)
  9. bool xnpGetDownloadLimitationOptionEditBlock\( string dirname, int option \)
  10. bool xnpGetDownloadLimitationOptionConfirmBlock\( string dirname \)
  11. bool xnpGetDownloadNotificationOptionRegisterBlock\( string dirname, int option = 0 \)
  12. bool xnpGetDownloadNotificationOptionEditBlock\( string dirname, int option \)
  13. bool xnpGetDownloadNotificationOptionConfirmBlock\( string dirname \)
  14. bool xnpGetDownloadConfirmationBlock\( int item\_id, int download\_file\_id, bool attachment\_dl\_notify, bool use\_license, int use\_cc, string rights \)
* [7. TextFile]()
  1. array xnpGetTextFileDetailBlock\( int item\_id, string name, string text \)
  2. array xnpGetTextFileEditBlock\( int item\_id, string name, string text \)
  3. array xnpGetTextFileConfirmBlock\( int item\_id, string name, int maxlen=65535 \)
  4. array xnpGetTextFileRegisterBlock\( string name \)
  5. string xnpGetTextFile\( string name \)
* [8. Rights]()
  1. array xnpGetRightsDetailBlock\( int item\_id, int use\_cc=1, string text='', int cc\_commercial\_use=1, int cc\_modification=2 \)\)
  2. array xnpGetRightsEditBlock\( int item\_id, int use\_cc=1, string text='', int cc\_commercial\_use=1, int cc\_modification=2 \)\)
  3. array xnpGetRightsConfirmBlock\( int item\_id, int maxlen=65535 \)\)
  4. array xnpGetRightsRegisterBlock\( \)\)
  5. array xnpGetRights\(\)\)
* [9. meta-information]()
  1. array xnpGetBasicInformationArray\( int item\_id \)
  2. bool xnpBasicInformation2XML\( resource fhdl, array item, bool is\_absolute, int base\_index\_id=false \)
* [10. Search]()

    array xnpGetBasicInformationAdvancedSearchBlock\( string modulename, array &search\_var \)

    string xnpGetBasicInformationAdvancedSearchQuery\( string moduleName \)

    string xnpGetKeywordQuery \(string dbVarName, string postVarName\)

    array xnpGetKeywordsQueries\( array dbVarNames, array keywords \)

    array xnpKeywordsToFulltextSql\( keywords \)

* [11. OAI-PMH]()
  1. string xnpGetBasicInformationMetadata\( string metadataPrefix, int item\_id \)
* [12. The system limits the number of characters]()

    array xnpTrimString\( string str, int length, string enc=null \)

    void xnpTrimColumn\( array &assoc, string table\_without\_prefix, array names=null, string enc=null \)

    void xnpConfirmHtml\( array &assoc, string table\_without\_prefix, array names=null, string enc=null \)

    bool xnpHasWithout\( array assoc \)

    array xnpGetColumnLengths\( string table\_without\_prefix \)

    string xnpWithinWithoutHtml\( string within, string without \)

* [13. Other]()
  1. double xnpGetTotalFileSize\( array iids \)
  2. bool xnpIsPending\( int item\_id \)
  3. string xnpGetTopBlock\( string moduleName, string displayName, string iconPath, string explanation, string subtypeVarName, array subtypes \)
  4. bool xnpIsAttachmentModified\( string file\_type\_name, int item\_id \)
  5. string xnpISO8601\( int year, int month, int day \)
  6. string xnpDate\( int year, int month, int day \)
  7. bool xnpExportFile\( string export\_path, resource fhdl, int item\_id \)
* [14. Supplement: Attachment, for $ name argument of TextFile system function]()
* [15. Biangenglvli]()
* [Credits]()
* [About XOOPS CMS]()

