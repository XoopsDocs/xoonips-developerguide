# oaipmh {#oaipmh}


## 第11章 OAI-PMH {#11-oai-pmh}

## 1\. string xnpGetBasicInformationMetadata( string metadataPrefix, int item_id ) {#1-string-xnpgetbasicinformationmetadata-string-metadataprefix-int-item-id}

item_id 引数で指定したアイテムの Basic Information を，OAI-PMHで交換するXMLに変換します．各アイテムタイプが生成するメタデータの Basic Information 部のXML生成を代行します．

この関数が生成したXMLと，各アイテムタイプで生成した Detail Information のXML文字列をあわせたものを，アイテムのメタ情報とします

### 1.1\. 入力 {#1-1}

* metadataPrefix : 変換したいXMLの書式(&#039;junii&#039;, &#039;junii2&#039;, &#039;oai_dc&#039;の何れかを指定できます)．

 item_id : 変換したいアイテムのID

### 1.2\. 戻り値 {#1-2}

XML文字列，または変換できなかったときfalse

