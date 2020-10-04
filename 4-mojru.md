# 第4章 モジュール管理

アイテムタイプはXOOPSのモジュールの形で実装されます．アイテム タイプを追加，更新，削除するにはXOOPSのモジュール管理の枠組を利用し ます．ここでは，モジュールのインストール，アップデート，アンインス トール時にアイテムタイプモジュールが行う処理とその実装に付いて説明 します．

### 1. インストール処理

アイテムタイプのインストール時に，アイテムタイプテーブルに以下の情報を記録する\(insertする\)必要があります．

* name: モジュール名
* display\_name: モジュール表示名
* mid: モジュールID
* viewphp: [項1. 「コールバック関数」](https://xoonips.osdn.jp/manuals/itemtype-340/itemtype.html#itemtype.callback)が定義されているPHPファイル名．XOOPS\_ROOT\_PATH/modules/ からの相対パスで指定します．

モジュールインストール時にコールバックされる以下の関数に処理を実装してください

**表 4.1. インストール処理コールバック関数**

|  | 書式 | 例\(xnpdataモジュールの場合\) |
| :--- | :--- | :--- |
| フォルダ | モジュールフォルダ/include/ | xnpdata/include/ |
| ファイル名 | oninstall.inc.php | oninstall.inc.php |
| 関数名 | xoops\_module\_install\_アイテムタイプ名\(小文字\) | xoops\_module\_install\_xnpdata |

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

### 2. アップデート処理

アイテムタイプモジュールを更新する処理を実装します．

モジュールアップデート時にコールバックされる以下の関数に処理を実装してください

**表 4.2. アップデート処理コールバック関数**

|  | 書式 | 例\(xnpdataモジュールの場合\) |
| :--- | :--- | :--- |
| フォルダ | モジュールフォルダ/include/ | xnpdata/include/ |
| ファイル名 | onupdate.inc.php | onupdate.inc.php |
| 関数名 | xoops\_module\_update\_アイテムタイプ名\(小文字\) | xoops\_module\_update\_xnpdata |

Dataタイプの場合は以下のように実装します．アップデートに成功したらtrue，失敗したらfalseを返します．

```text
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

### 3. アンインストール処理

インストール時にアイテムタイプテーブルに書き込んだ情報を，アイテムタイプのアンインストール時に削除する必要があります．また，作成されたアイテムの情報もモジュールの削除と同時にデータベースから削除する必要があります．

モジュールアンインストール時にコールバックされる以下の関数に処理を実装してください

**表 4.3. アンインストール処理コールバック関数**

|  | 書式 | 例\(xnpdataモジュールの場合\) |
| :--- | :--- | :--- |
| フォルダ | モジュールフォルダ/include/ | xnpdata/include/ |
| ファイル名 | onuninstall.inc.php | onuninstall.inc.php |
| 関数名 | xoops\_module\_uninstall\_アイテムタイプ名\(小文字\) | xoops\_module\_uninstall\_xnpdata |

Dataタイプの場合は以下のように実装します．

```text
function xoops_module_uninstall_xnpdata( $xoopsMod ) {
	global $xoopsDB;
	
    ....
	// unregister itemtype
	$table = $xoopsDB->prefix('xoonips_item_type');
	$mid = $xoopsMod->getVar('mid');
	$sql = "DELETE FROM $table where mid = $mid";
	if ( $xoopsDB->query($sql) == FALSE ){
		// cannot unregister itemtype
		return false;
	}
    ....

```

