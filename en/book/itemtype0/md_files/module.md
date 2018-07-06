#Chapter 4: Module Management

Item type is implemented in the form of XOOPS modules. Add an item type, update, or delete will use the framework of the XOOPS module management. Here, the installation of the module, updates, describes the item type module performs processing and its implementation at the time of uninstall.

###1. Installation process

During the installation of the item type, record the following information to the item type table (to insert) you need.

name: module name

display_name: Module Display Name

mid: module ID

viewphp: Section 1. "callback function" PHP file names that have been defined. Specify a relative path from the XOOPS_ROOT_PATH / modules /.

Please implement the processing of the following function to be called back when the module is installed

Table 4.1. The installation process callback function

| | Format| Example (using xnpdata module as example)  
--- | --- | ---
folder | modules folder/include/ |xnpdata/include 
file name  | oninstall.inc.php | oninstall.inc.php
Name of the function | xoops__module_install_ item type name (lowercase) | xoops_module_install_xnpdata




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


 <h2 xmlns="http://www.w3.org/1999/xhtml" class="title"><a id="module"></a>第4章 モジュール管理</h2>

 </div>

 </div>

 </div>

 <p>アイテムタイプはXOOPSのモジュールの形で実装されます．アイテム

 タイプを追加，更新，削除するにはXOOPSのモジュール管理の枠組を利用し

 ます．ここでは，モジュールのインストール，アップデート，アンインス

 トール時にアイテムタイプモジュールが行う処理とその実装に付いて説明

 します．</p>

 <div class="section" lang="ja" xml:lang="ja">

 <div xmlns="" class="titlepage">

 <div>

 <div>

 <h2 xmlns="http://www.w3.org/1999/xhtml" class="title" style="clear: both"><a id="module.install"></a>1. インストール処理</h2>

 </div>

 </div>

 </div>

 <p>アイテムタイプのインストール時に，アイテムタイプテーブルに以下の情報を記録する(insertする)必要があります．</p>

 <div class="itemizedlist">

 <ul type="disc">

 <li>

 <p>name: モジュール名</p>

 </li>

 <li>

 <p>display_name: モジュール表示名</p>

 </li>

 <li>

 <p>mid: モジュールID</p>

 </li>

 <li>

 <p>viewphp: <a href="itemtype.html#itemtype.callback" title="1. コールバック関数">項1. 「コールバック関数」</a>が定義されているPHPファイル名．XOOPS_ROOT_PATH/modules/ からの相対パスで指定します．</p>

 </li>

 </ul>

 </div>

 <p>モジュールインストール時にコールバックされる以下の関数に処理を実装してください</p>

 <div class="table">

 <a id="table.module.install"></a>

 <p class="title">

 <b>表 4.1. インストール処理コールバック関数</b>

 </p>

 <div class="table-contents">

 <table summary="インストール処理コールバック関数" cellspacing="0" cellpadding="5" border="0" style="border-collapse: collapse;border-top: 0.5pt solid ; border-bottom: 0.5pt solid ; border-left: 0.5pt solid ; border-right: 0.5pt solid ; ">

 <colgroup>

 <col />

 <col />

 <col />

 </colgroup>

 <thead>

 <tr>

 <th style="border-right: 0.5pt solid ; border-bottom: 0.5pt solid ; " align="left"> </th>

 <th style="border-right: 0.5pt solid ; border-bottom: 0.5pt solid ; " align="left">書式</th>

 <th style="border-bottom: 0.5pt solid ; " align="left">例(xnpdataモジュールの場合)</th>

 </tr>

 </thead>

 <tbody>

 <tr>

 <td style="border-right: 0.5pt solid ; border-bottom: 0.5pt solid ; " align="left">フォルダ</td>

 <td style="border-right: 0.5pt solid ; border-bottom: 0.5pt solid ; " align="left">モジュールフォルダ/include/</td>

 <td style="border-bottom: 0.5pt solid ; " align="left">xnpdata/include/</td>

 </tr>

 <tr>

 <td style="border-right: 0.5pt solid ; border-bottom: 0.5pt solid ; " align="left">ファイル名</td>

 <td style="border-right: 0.5pt solid ; border-bottom: 0.5pt solid ; " align="left">oninstall.inc.php</td>

 <td style="border-bottom: 0.5pt solid ; " align="left">oninstall.inc.php</td>

 </tr>

 <tr>

 <td style="border-right: 0.5pt solid ; " align="left">関数名</td>

 <td style="border-right: 0.5pt solid ; " align="left">xoops_module_install_アイテムタイプ名(小文字)</td>

 <td style="" align="left">xoops_module_install_xnpdata</td>

 </tr>

 </tbody>

 </table>

 </div>

 </div>

 <br class="table-break" />

 <p>

 Dataタイプの場合は以下のように実装します．

 </p>

 <pre class="programlisting">

function xoops_module_install_xnpdata( $xoopsMod ) {

 global $xoopsDB;

 // register itemtype

 $table = $xoopsDB-&gt;prefix( 'xoonips_item_type' );

 $mid = $xoopsMod-&gt;getVar( 'mid' );

 $sql = "INSERT INTO $table ( name, display_name, mid, viewphp ) VALUES ( 'xnpdata', 'Data', $mid, 'xnpdata/include/view.php' )";

 if ( $xoopsDB-&gt;query( $sql ) == FALSE ) {

 // cannot register itemtype

 return false;

 }

 ....

 </pre>

 </div>

 <div class="section" lang="ja" xml:lang="ja">

 <div xmlns="" class="titlepage">

 <div>

 <div>

 <h2 xmlns="http://www.w3.org/1999/xhtml" class="title" style="clear: both"><a id="module.update"></a>2. アップデート処理</h2>

 </div>

 </div>

 </div>

 <p>アイテムタイプモジュールを更新する処理を実装します．</p>

 <p>モジュールアップデート時にコールバックされる以下の関数に処理を実装してください</p>

 <div class="table">

 <a id="table.module.update"></a>

 <p class="title">

 <b>表 4.2. アップデート処理コールバック関数</b>

 </p>

 <div class="table-contents">

 <table summary="アップデート処理コールバック関数" cellspacing="0" cellpadding="5" border="0" style="border-collapse: collapse;border-top: 0.5pt solid ; border-bottom: 0.5pt solid ; border-left: 0.5pt solid ; border-right: 0.5pt solid ; ">

 <colgroup>

 <col />

 <col />

 <col />

 </colgroup>

 <thead>

 <tr>

 <th style="border-right: 0.5pt solid ; border-bottom: 0.5pt solid ; " align="left"> </th>

 <th style="border-right: 0.5pt solid ; border-bottom: 0.5pt solid ; " align="left">書式</th>

 <th style="border-bottom: 0.5pt solid ; " align="left">例(xnpdataモジュールの場合)</th>

 </tr>

 </thead>

 <tbody>

 <tr>

 <td style="border-right: 0.5pt solid ; border-bottom: 0.5pt solid ; " align="left">フォルダ</td>

 <td style="border-right: 0.5pt solid ; border-bottom: 0.5pt solid ; " align="left">モジュールフォルダ/include/</td>

 <td style="border-bottom: 0.5pt solid ; " align="left">xnpdata/include/</td>

 </tr>

 <tr>

 <td style="border-right: 0.5pt solid ; border-bottom: 0.5pt solid ; " align="left">ファイル名</td>

 <td style="border-right: 0.5pt solid ; border-bottom: 0.5pt solid ; " align="left">onupdate.inc.php</td>

 <td style="border-bottom: 0.5pt solid ; " align="left">onupdate.inc.php</td>

 </tr>

 <tr>

 <td style="border-right: 0.5pt solid ; " align="left">関数名</td>

 <td style="border-right: 0.5pt solid ; " align="left">xoops_module_update_アイテムタイプ名(小文字)</td>

 <td style="" align="left">xoops_module_update_xnpdata</td>

 </tr>

 </tbody>

 </table>

 </div>

 </div>

 <br class="table-break" />

 <p>

 Dataタイプの場合は以下のように実装します．アップデートに成功したらtrue，失敗したらfalseを返します．

 </p>

 <pre class="programlisting">

```php
function xoops_module_update_xnpdata( $xoopsMod, $oldversion ) {
 global $xoopsDB;
 $table = $xoopsDB-&gt;prefix( 'xnpdata_item_detail' );

 echo '&lt;code&gt;Updating modules...&lt;/code&gt;&lt;br /&gt;';
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

 echo $xoopsDB-&gt;error();

 return false;

 }

 default:
 return true;
 }
}
```
 </pre>

 </div>

 <div class="section" lang="ja" xml:lang="ja">

 <div xmlns="" class="titlepage">

 <div>

 <div>

 <h2 xmlns="http://www.w3.org/1999/xhtml" class="title" style="clear: both"><a id="module.uninstall"></a>3. アンインストール処理</h2>

 </div>

 </div>

 </div>

 <p>インストール時にアイテムタイプテーブルに書き込んだ情報を，アイテムタイプのアンインストール時に削除する必要があります．また，作成されたアイテムの情報もモジュールの削除と同時にデータベースから削除する必要があります．</p>

 <p>モジュールアンインストール時にコールバックされる以下の関数に処理を実装してください</p>

 <div class="table">

 <a id="table.module.uninstall"></a>

 <p class="title">

 <b>表 4.3. アンインストール処理コールバック関数</b>

 </p>

 <div class="table-contents">

 <table summary="アンインストール処理コールバック関数" cellspacing="0" cellpadding="5" border="0" style="border-collapse: collapse;border-top: 0.5pt solid ; border-bottom: 0.5pt solid ; border-left: 0.5pt solid ; border-right: 0.5pt solid ; ">

 <colgroup>

 <col />

 <col />

 <col />

 </colgroup>

 <thead>

 <tr>

 <th style="border-right: 0.5pt solid ; border-bottom: 0.5pt solid ; " align="left"> </th>

 <th style="border-right: 0.5pt solid ; border-bottom: 0.5pt solid ; " align="left">書式</th>

 <th style="border-bottom: 0.5pt solid ; " align="left">例(xnpdataモジュールの場合)</th>

 </tr>

 </thead>

 <tbody>

 <tr>

 <td style="border-right: 0.5pt solid ; border-bottom: 0.5pt solid ; " align="left">フォルダ</td>

 <td style="border-right: 0.5pt solid ; border-bottom: 0.5pt solid ; " align="left">モジュールフォルダ/include/</td>

 <td style="border-bottom: 0.5pt solid ; " align="left">xnpdata/include/</td>

 </tr>

 <tr>

 <td style="border-right: 0.5pt solid ; border-bottom: 0.5pt solid ; " align="left">ファイル名</td>

 <td style="border-right: 0.5pt solid ; border-bottom: 0.5pt solid ; " align="left">onuninstall.inc.php</td>

 <td style="border-bottom: 0.5pt solid ; " align="left">onuninstall.inc.php</td>

 </tr>

 <tr>

 <td style="border-right: 0.5pt solid ; " align="left">関数名</td>

 <td style="border-right: 0.5pt solid ; " align="left">xoops_module_uninstall_アイテムタイプ名(小文字)</td>

 <td style="" align="left">xoops_module_uninstall_xnpdata</td>



##3. uninstall process

The information written to the item type table at the time of installation, you must remove it during the uninstallation of the item type. In addition, you will need to be removed from the database at the same time as the deletion of even module information of the items that have been created.

Please implement the processing of the following function to be called back when the module is uninstalled

Table 4.3. Uninstall process callback function

FormatExample (in the case of xnpdata module)folderModules folder / include /xnpdata / include /file nameonuninstall.inc.phponuninstall.inc.phpName of the functionxoops_module_uninstall_ item type name (lowercase)xoops_module_uninstall_xnpdata

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
 