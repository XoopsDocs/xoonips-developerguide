# Chapter 4: Module Management

Item type is implemented in the form of XOOPS modules. Add an item type, update, or delete will use the framework of the XOOPS module management. Here, the installation of the module, updates, describes the item type module performs processing and its implementation at the time of uninstall.

### 1. Installation process

During the installation of the item type, record the following information to the item type table \(to insert\) you need.

name: module name

display\_name: Module Display Name

mid: module ID

viewphp: Section 1. "callback function" PHP file names that have been defined. Specify a relative path from the XOOPS\_ROOT\_PATH / modules /.

Please implement the processing of the following function to be called back when the module is installed

Table 4.1. The installation process callback function

|  | Format | Example \(using xnpdata module as example\) |
| :--- | :--- | :--- |
| folder | modules folder/include/ | xnpdata/include |
| file name | oninstall.inc.php | oninstall.inc.php |
| Name of the function | xoops_\_module\_install_ item type name \(lowercase\) | xoops\_module\_install\_xnpdata |

```php
function xoops_module_install_xnpdata ($xoopsMod) {
global $xoopsDB; 

// Register itemtype 
$Table = $xoopsDB-> prefix ( 'xoonips_item_type'); 
$Mid = $xoopsMod-> getVar ( 'mid'); 
$Sql ​​= "INSERT INTO $ table (name, display_name, mid, viewphp) VALUES ( 'xnpdata', 'Data', $mid, 'xnpdata/include/view.php')"; 
if ($xoopsDB->query($sql) === FALSE) { // If can not register, itemtype returns false; 
} 
....
```

## 第4章 モジュール管理

&lt;/div&gt;

&lt;/div&gt;

&lt;/div&gt;

アイテムタイプはXOOPSのモジュールの形で実装されます．アイテム タイプを追加，更新，削除するにはXOOPSのモジュール管理の枠組を利用し ます．ここでは，モジュールのインストール，アップデート，アンインス トール時にアイテムタイプモジュールが行う処理とその実装に付いて説明 します．

## 1. インストール処理

&lt;/div&gt;

&lt;/div&gt;

アイテムタイプのインストール時に，アイテムタイプテーブルに以下の情報を記録する\(insertする\)必要があります．

* name: モジュール名
* display\_name: モジュール表示名
* mid: モジュールID
* viewphp: [項1. 「コールバック関数」](https://github.com/XoopsDocs/xoonips-developerguide/tree/a6a58e91b3c2fbad05284b6a55d66570e12e94d6/en/book/itemtype0/md_files/itemtype.html#itemtype.callback)が定義されているPHPファイル名．XOOPS\_ROOT\_PATH/modules/ からの相対パスで指定します．

モジュールインストール時にコールバックされる以下の関数に処理を実装してください

 **表 4.1. インストール処理コールバック関数**

|  | 書式 | 例\(xnpdataモジュールの場合\) |
| :--- | :--- | :--- |
| フォルダ | モジュールフォルダ/include/ | xnpdata/include/ |
| ファイル名 | oninstall.inc.php | oninstall.inc.php |
| 関数名 | xoops\_module\_install\_アイテムタイプ名\(小文字\) | xoops\_module\_install\_xnpdata |

&lt;/div&gt;

 Dataタイプの場合は以下のように実装します．

```text


function xoops_module_install_xnpdata( $xoopsMod ) {

 global $xoopsDB;

 // register itemtype

 $table = $xoopsDB->prefix( 'xoonips_item_type' );

 $mid = $xoopsMod->getVar( 'mid' );

 $sql = "INSERT INTO $table ( name, display_name, mid, viewphp ) VALUES ( 'xnpdata', 'Data', $mid, 'xnpdata/include/view.php' )";

 if ( $xoopsDB->query( $sql ) == FALSE ) {

 // cannot register itemtype

 return false;

 }

 ....

```

&lt;/div&gt;

## 2. アップデート処理

&lt;/div&gt;

&lt;/div&gt;

アイテムタイプモジュールを更新する処理を実装します．

モジュールアップデート時にコールバックされる以下の関数に処理を実装してください

 **表 4.2. アップデート処理コールバック関数**

|  | 書式 | 例\(xnpdataモジュールの場合\) |
| :--- | :--- | :--- |
| フォルダ | モジュールフォルダ/include/ | xnpdata/include/ |
| ファイル名 | onupdate.inc.php | onupdate.inc.php |
| 関数名 | xoops\_module\_update\_アイテムタイプ名\(小文字\) | xoops\_module\_update\_xnpdata |

&lt;/div&gt;

 Dataタイプの場合は以下のように実装します．アップデートに成功したらtrue，失敗したらfalseを返します．

```text


```php
function xoops_module_update_xnpdata( $xoopsMod, $oldversion ) {
 global $xoopsDB;
 $table = $xoopsDB->prefix( 'xnpdata_item_detail' );

 echo '<code>Updating modules...</code><br />';
 switch ( $oldversion ) {
 case 200:
 //Ver. 2.00から3.10までの更新処理

 ....

 case 310:
 //Ver. 3.10から3.11までの更新処理

 ....

 case 311:
 //Ver. 3.11から最新版までの更新処理

 ....
 if ( $is_error ) {

 echo $xoopsDB->error();

 return false;

 }

 default:
 return true;
 }
}
```
```

&lt;/div&gt;

## 3. アンインストール処理

&lt;/div&gt;

&lt;/div&gt;

インストール時にアイテムタイプテーブルに書き込んだ情報を，アイテムタイプのアンインストール時に削除する必要があります．また，作成されたアイテムの情報もモジュールの削除と同時にデータベースから削除する必要があります．

モジュールアンインストール時にコールバックされる以下の関数に処理を実装してください

 **表 4.3. アンインストール処理コールバック関数**

|  | 書式 | 例\(xnpdataモジュールの場合\) |
| :--- | :--- | :--- |


| フォルダ | モジュールフォルダ/include/ | xnpdata/include/ |
| :--- | :--- | :--- |


| ファイル名 | onuninstall.inc.php | onuninstall.inc.php |
| :--- | :--- | :--- |


|  |
| :--- |


| 関数名 |
| :--- |


| xoops\_module\_uninstall\_アイテムタイプ名\(小文字\) |
| :--- |


| xoops\_module\_uninstall\_xnpdata |
| :--- |


## 3. uninstall process <a id="table.module.uninstall"></a>

The information written to the item type table at the time of installation, you must remove it during the uninstallation of the item type. In addition, you will need to be removed from the database at the same time as the deletion of even module information of the items that have been created.

Please implement the processing of the following function to be called back when the module is uninstalled

Table 4.3. Uninstall process callback function

FormatExample \(in the case of xnpdata module\)folderModules folder / include /xnpdata / include /file nameonuninstall.inc.phponuninstall.inc.phpName of the functionxoops_module\_uninstall_ item type name \(lowercase\)xoops\_module\_uninstall\_xnpdata

In the case of Data type and implemented as follows.

```php
function xoops_module_uninstall_xnpdata( $xoopsMod ) {

 global $xoopsDB;
....

 // unregister itemtype
 $table = $xoopsDB-&gt;prefix('xoonips_item_type');

 $mid = $xoopsMod-&gt;getVar('mid');

 $sql = "DELETE FROM $table where mid = $mid";

 if ( $xoopsDB-&gt;query($sql) == FALSE ){

 // cannot unregister itemtype

 return false;

 }
 ....
```

