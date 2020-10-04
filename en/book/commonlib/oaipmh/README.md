# oaipmh

| ![&#x524D;&#x306E;&#x30DA;&#x30FC;&#x30B8;](https://github.com/XoopsDocs/xoonips-developerguide/tree/a6a58e91b3c2fbad05284b6a55d66570e12e94d6/en/book/assets/commonlib/prev.gif) |  | ![&#x6B21;&#x306E;&#x30DA;&#x30FC;&#x30B8;](https://github.com/XoopsDocs/xoonips-developerguide/tree/a6a58e91b3c2fbad05284b6a55d66570e12e94d6/en/book/assets/commonlib/next.gif) |
| :--- | :---: | :--- |


## 第11章 OAI-PMH <a id="11-oai-pmh"></a>

## 1. string xnpGetBasicInformationMetadata\( string metadataPrefix, int item\_id \) <a id="1-string-xnpgetbasicinformationmetadata-string-metadataprefix-int-item-id"></a>

item\_id 引数で指定したアイテムの Basic Information を，OAI-PMHで交換するXMLに変換します．各アイテムタイプが生成するメタデータの Basic Information 部のXML生成を代行します．

この関数が生成したXMLと，各アイテムタイプで生成した Detail Information のXML文字列をあわせたものを，アイテムのメタ情報とします

### 1.1. 入力 <a id="1-1"></a>

* metadataPrefix : 変換したいXMLの書式\('junii', 'junii2', 'oai\_dc'の何れかを指定できます\)．

  item\_id : 変換したいアイテムのID

### 1.2. 戻り値 <a id="1-2"></a>

XML文字列，または変換できなかったときfalse

| ![&#x524D;&#x306E;&#x30DA;&#x30FC;&#x30B8;](https://github.com/XoopsDocs/xoonips-developerguide/tree/a6a58e91b3c2fbad05284b6a55d66570e12e94d6/en/book/assets/commonlib/prev.gif) |  | ![&#x6B21;&#x306E;&#x30DA;&#x30FC;&#x30B8;](https://github.com/XoopsDocs/xoonips-developerguide/tree/a6a58e91b3c2fbad05284b6a55d66570e12e94d6/en/book/assets/commonlib/next.gif) |
| :--- | :--- | :--- |
|  | ![&#x30DB;&#x30FC;&#x30E0;](https://github.com/XoopsDocs/xoonips-developerguide/tree/a6a58e91b3c2fbad05284b6a55d66570e12e94d6/en/book/assets/commonlib/home.gif) |  |

Last updated: 2010/04/15

