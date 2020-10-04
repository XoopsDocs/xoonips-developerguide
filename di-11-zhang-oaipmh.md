# 第11章 OAI-PMH

### 1. string xnpGetBasicInformationMetadata\( string metadataPrefix, int item\_id \)

item\_id 引数で指定したアイテムの Basic Information を，OAI-PMHで交換するXMLに変換します．各アイテムタイプが生成するメタデータの Basic Information 部のXML生成を代行します．

この関数が生成したXMLと，各アイテムタイプで生成した Detail Information のXML文字列をあわせたものを，アイテムのメタ情報とします

#### 1.1. 入力

* metadataPrefix : 変換したいXMLの書式\('junii', 'junii2', 'oai\_dc'の何れかを指定できます\)．

  item\_id : 変換したいアイテムのID

#### 1.2. 戻り値

XML文字列，または変換できなかったときfalse
