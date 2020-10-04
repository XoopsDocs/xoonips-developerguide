# README

## index <a id="index"></a>

|  |  | ![&#x6B21;&#x306E;&#x30DA;&#x30FC;&#x30B8;](https://github.com/XoopsDocs/xoonips-developerguide/tree/a6a58e91b3c2fbad05284b6a55d66570e12e94d6/en/book/assets/commonlib/next.gif) |
| :--- | :---: | :--- |


## XooNIps <a id="xoonips"></a>

### 共通ライブラリ関数一覧

RELEASE 3.40

2008年11月28日

**概要**

`xoonips/include/lib.php`で定義された関数について説明します．ここで紹介する関数の使用法はアイテムタイプ作成手順書を参照してください．

Copyright © 2005-2008-NaN RIKEN \(The Institute of Physical and Chemical Science Research\)

**目次**

* 1. はじめに
* * 1. type function\_name\( argument, …. \)
* 2. 注意事項
* * 1. 関数名の規則
  * 2. フォーム生成関数の注意事項
* 3. Basic Information
* * 1. Basic Informationのデータ構造
  * 2. Basic Informationのフォームデータ構造
  * 3. array xnpGetBasicInformationDetailBlock\( int item\_id \)
  * 4. array xnpGetBasicInformationEditBlock\( int item\_id \)
  * 5. array xnpGetBasicInformationConfirmBlock\( int item\_id \)
  * 6. array xnpGetBasicInformationRegisterBlock\(\)
  * 7. bool xnpInsertBasicInformation\( int &item\_id \)
  * 8. bool xnpUpdateBasicInformation\( int item\_id \)
  * 9. bool xnpDeleteBasicInformation\( int item\_id \)
* 4. Index
* * 1. array xnpGetIndexDetailBlock\( int item\_id, bool button\_flag = true \)
  * 2. array xnpGetIndexEditBlock\( int item\_id \)
  * 3. array xnpGetIndexConfirmBlock\( int item\_id \)
  * 4. array xnpGetIndexRegisterBlock\(\)
  * 5. xnpInsertIndex : \(無し\)
  * 6. bool xnpUpdateIndex\( int item\_id \)
  * 7. xnpDeleteIndex : \(無し\)
* 5. Preview
* * 1. array xnpGetPreviewDetailBlock\( int item\_id \)
  * 2. array xnpGetPreviewEditBlock\( int item\_id \)
  * 3. array xnpGetPreviewConfirmBlock\( int item\_id \)
  * 4. array xnpGetPreviewRegisterBlock\(\)
  * 5. xnpInsertPreview : \(無し\)
  * 6. bool xnpUpdatePreview\( int item\_id \)
  * 7. xnpDeletePreview : \(無し\)
* 6. Attachment
* * 1. array xnpGetAttachmentDetailBlock\( int item\_id, string name \)
  * 2. array xnpGetAttachmentEditBlock\( int item\_id, string name \)
  * 3. array xnpGetAttachmentConfirmBlock\( int item\_id, string name \)
  * 4. array xnpGetAttachmentRegisterBlock\( string name \)
  * 5. xnpInsertAttachemnt : \(無し\)
  * 6. bool xnpUpdateAttachment\( int item\_id, string name \)
  * 7. xnpDeleteAttachemnt : \(無し\)
  * 8. bool xnpGetDownloadLimitationOptionRegisterBlock\( string dirname, int option = 0 \)
  * 9. bool xnpGetDownloadLimitationOptionEditBlock\( string dirname, int option \)
  * 10. bool xnpGetDownloadLimitationOptionConfirmBlock\( string dirname \)
  * 11. bool xnpGetDownloadNotificationOptionRegisterBlock\( string dirname, int option = 0 \)
  * 12. bool xnpGetDownloadNotificationOptionEditBlock\( string dirname, int option \)
  * 13. bool xnpGetDownloadNotificationOptionConfirmBlock\( string dirname \)
  * 14. bool xnpGetDownloadConfirmationBlock\( int item\_id, int download\_file\_id, bool attachment\_dl\_notify, bool use\_license, int use\_cc, string rights \)
* 7. TextFile
* * 1. array xnpGetTextFileDetailBlock\( int item\_id, string name, string text \)
  * 2. array xnpGetTextFileEditBlock\( int item\_id, string name, string text \)
  * 3. array xnpGetTextFileConfirmBlock\( int item\_id, string name, int maxlen=65535 \)
  * 4. array xnpGetTextFileRegisterBlock\( string name \)
  * 5. string xnpGetTextFile\( string name \)
* 8. Rights
* * 1. array xnpGetRightsDetailBlock\( int item\_id, int use\_cc=1, string text='', int cc\_commercial\_use=1, int cc\_modification=2 \)
  * 2. array xnpGetRightsEditBlock\( int item\_id, int use\_cc=1, string text='', int cc\_commercial\_use=1, int cc\_modification=2 \)
  * 3. array xnpGetRightsConfirmBlock\( int item\_id, int maxlen=65535 \)
  * 4. array xnpGetRightsRegisterBlock\( \)
  * 5. array xnpGetRights\(\)
* 9. メタ情報
* * 1. array xnpGetBasicInformationArray\( int item\_id \)
  * 2. bool xnpBasicInformation2XML\( resource fhdl, array item, bool is\_absolute, int base\_index\_id=false \)
* 10. 検索
* * 1. array xnpGetBasicInformationAdvancedSearchBlock\( string modulename, array &search\_var \)
  * 2. string xnpGetBasicInformationAdvancedSearchQuery\( string moduleName \)
  * 3. string xnpGetKeywordQuery \( string dbVarName, string postVarName \)
  * 4. array xnpGetKeywordsQueries\( array dbVarNames, array keywords \)
  * 5. array xnpKeywordsToFulltextSql\( keywords \)
* 11. OAI-PMH
* * 1. string xnpGetBasicInformationMetadata\( string metadataPrefix, int item\_id \)
* 12. 文字数制限
* * 1. array xnpTrimString\( string str, int length, string enc=null \)
  * 2. void xnpTrimColumn\( array &assoc, string table\_without\_prefix, array names=null, string enc=null \)
  * 3. void xnpConfirmHtml\( array &assoc, string table\_without\_prefix, array names=null, string enc=null \)
  * 4. bool xnpHasWithout\( array assoc \)
  * 5. array xnpGetColumnLengths\( string table\_without\_prefix \)
  * 6. string xnpWithinWithoutHtml\( string within, string without \)
* 13. その他
* * 1. double xnpGetTotalFileSize\( array iids \)
  * 2. bool xnpIsPending\( int item\_id \)
  * 3. string xnpGetTopBlock\( string moduleName, string displayName, string iconPath, string explanation, string subtypeVarName, array subtypes \)
  * 4. bool xnpIsAttachmentModified\( string file\_type\_name, int item\_id \)
  * 5. string xnpISO8601\( int year, int month, int day \)
  * 6. string xnpDate\( int year, int month, int day \)
  * 7. bool xnpExportFile\( string export\_path, resource fhdl, int item\_id \)
* 14. 補足: Attachment, TextFile 系関数の $name 引数について
* 15. 変更履歴

|  |  | ![&#x6B21;&#x306E;&#x30DA;&#x30FC;&#x30B8;](https://github.com/XoopsDocs/xoonips-developerguide/tree/a6a58e91b3c2fbad05284b6a55d66570e12e94d6/en/book/assets/commonlib/next.gif) |
| :--- | :--- | :--- |


Last updated: 2010/04/15

