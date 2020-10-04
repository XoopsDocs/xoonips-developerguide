# 第20章 Import

ImportされるXMLファイルに記録されたアイテムの情報を解析しデータベースに登録します．システムはインポートに必要な以下のクラスを提供します．各アイテムタイプはこれらのクラスを継承し，インポートに必要なメソッドをオーバーライドしアイテムタイプ独自のインポート処理を定義します．

### 1. クラス

システムが提供するクラスは以下の通りです．

* インポートアイテムクラス
  * クラス名：XooNIpsImportItem
  * 概要：インポートするアイテムの情報を保持するクラス
* インポートアイテムハンドラクラス
  * クラス名：XooNIpsImportItemHandler
  * 概要：インポートアイテムクラスのインポート 処理を実装するクラス．XooNIpsImportItemHandlerクラスは， アイテムのインポート処理を実装します．アイテムタイプは XooNIpsImportItemHandlerクラスを継承し，アイテムタイプ 独自のインポート処理を実装（オーバーライド）できます．

### 2. クラス名

クラス名はアイテムタイプ名に基づいて以下のように決まっています．

* class &lt;アイテムタイプ名&gt;ImportItem

  \(例：XNPBookImportItem，XNPDataImportItem,...）

* class &lt;アイテムタイプ名&gt;ImportItemHandler

  \(例：XNPBookImportItemHandler，XNPDataImportItemHandler,...）

* 先頭から4文字は大文字です

### 3. ファイル名，ファイルパス

クラスを定義するPHPファイルのファイル名とパスは，以下の通りです．

* ファイルパス：modules/モジュール名/class/
* ファイル名：&lt;アイテムタイプ名&gt;\_import\_item.class.php

  \(例：xnpbook\_import\_item.class.php，xnpdata\_import\_item.class.php,...）

* ファイル名は全て小文字です

### 4. インポートアイテムクラスの実装

#### 4.1. 定義済みのメンバー変数

インポートアイテムでは以下のメンバー変数を使用します．

**表 20.1. メンバー変数一覧**

| メンバー | 備考 |
| :--- | :--- |
| XooNIpsItemCompo \_item | アイテム情報を保持するオブジェクト．このオブジェクトはコンストラクタで作成します． |

#### 4.2. オーバーライドするメソッド

アイテムタイプがオーバーライドするメソッドは以下の通りです．

**表 20.2. メソッド一覧**

| メソッド | 備考 |
| :--- | :--- |
| int getTotalFileSize\(\) | アイテムに添付されたファイルの合計サイズ\(単位：バイト\)を返す |
| XooNIpsImportItem &getClone\(\) | インポートアイテムオブジェクトの複製\(クローン\)を作成し，そのリファレンスを返す |

#### 4.3. コンストラクタ

メンバー変数$\_itemを初期化します．アイテムタイプごとに定義されたORMオブジェクトを作成し，リファレンスを代入します．以下はDataタイプのコンストラクタの例です．

```text
    function XNPDataImportItem(){
        $handler =& xoonips_getormcompohandler( 'xnpdata', 'item' );
        $this -> _item =& $handler -> create();
    }
```

### 5. インポートアイテムハンドラクラスの実装

#### 5.1. 定義済みのメンバー変数

インポートアイテムハンドラでは以下のメンバー変数を使用します．

**表 20.3. メンバー変数一覧**

| メンバー | 備考 |
| :--- | :--- |
| string\[\] \_tag\_stack | 解析中のXMLの要素名を管理するスタック．配列の先頭にルートの要素名が，最後に現在解析中の要素名が記録されます． |
| string \_cdata | 現在解析中の要素のCDATA部の文字列が格納されます．ただし，xmlEndElementHandler\([項5.5. 「終了要素ハンドラ\(xmlEndElementHandler\)」](https://xoonips.osdn.jp/manuals/itemtype-340/import.html#import.implement.importitemhandler.endelementhandler)\)が呼ばれるまで，このメンバーの値は確定しませんので注意してください． |
| XooNIpsImportItem \_import\_item | インポートアイテムオブジェクト．XMLを解析して得られたアイテムの情報をこのオブジェクトにセットします．このオブジェクトはコンストラクタで作成します． |
| string \_attachment\_dir | インポートされる添付ファイルが一時保存されているファイルパス\(絶対パス\)． |

#### 5.2. オーバーライドするメソッド

アイテムタイプがオーバーライドするメソッドは以下の通りです．

**表 20.4. メソッド一覧**

| メソッド | 備考 |
| :--- | :--- |
| XooNIpsImportItem create\(\) | アイテムタイプに応じたインポートアイテムオブジェクトを作成して返します． |
| void xmlStartElementHandler\( $parser , $name , $attribs \) | XMLファイルの開始要素を解析するときにコールバックされます．Detail Informationの開始要素の解析処理を定義します． |
| void xmlEndElementHandler\( $parser ,$name \) | XMLファイルの終了要素を解析するときにコールバックされます．Detail Informationの終了要素の解析処理を定義します． |
| void onImportFinished\( &$item, &$import\_items \) | インポート成功後のアイテムの操作を定義します． |
| bool insert\( &$item \) | アイテムオブジェクトのinsertを実行します． |
| viod setNew\( &$item \) | アイテムオブジェクトのsetNewを実行します． |
| viod unsetNew\( &$item \) | アイテムオブジェクトのunsetNewを実行します． |
| viod setDirty\( &$item \) | アイテムオブジェクトのsetDirtyを実行します． |
| viod unsetDirty\( &$item \) | アイテムオブジェクトのunsetDirtyを実行します． |
| string getImportLog\($import\_item\) | インポート結果のログを作成します． |
| void import\(&$item\) | インポートを実行します． |

#### 5.3. コンストラクタ

スーパークラスのコンストラクタを呼び出します．以下はDataタイプのコンストラクタの例です．

```text
function XNPDataImportItemHandler(){
    parent::XooNIpsImportItemHandler();
}
```

#### 5.4. 開始要素ハンドラ\(xmlStartElementHandler\)

```text
void xmlStartElementHandler( $parser , $name , $attribs )
```

インポートするXMLファイルをシステムが解析し，開始要素を見つけたときにコールバックされます．要素の属性値を必要とする処理はここに定義します．アイテムタイプはこの関数で以下の処理を行います．

* スーパークラスのxmlStartElementHandlerを呼び出す
* 開始要素の解析を行う

開始要素に付いての情報は引数で与えられます．引数は以下のとおりです．

* $parser：XMLパーザのリファレンス
* $name：要素名
* $attribs：属性の連想配列

$parserはxml\_parser\_createで作成されるXMLパーザのリファレンスです．XMLの解析に関連する情報\(解析中の行番号など\)が必要な場合はこのリファレンスを使用できます．詳細はPHPのXML関数についての情報を参照してください．

$nameは要素名の文字列です．XMLファイル中の書き方に拘わらず，要素名は大文字に変換されます．

$attribは開始要素に定義された属性名と属性値を連想配列の形で保持します．

以上の引数は全て，PHPのXML関数が提供する開始要素ハンドラと同じです．詳細はPHPのXML関数\(xml\_set\_element\_handlerなど\)についての情報を参照してください．

戻り値はありません．

処理中のエラーはすべて，\_import\_itemメンバーのsetErrorsメソッドを使用して記録します．詳しくはXooNIpsImportItemを参照してください．

**5.4.1. スーパークラスの開始要素ハンドラを呼び出す**

```text
parent::xmlStartElementHandler($parser, $name, $attribs);
```

開始要素ハンドラの冒頭で，上のようにしてスーパークラスの開始要素ハンドラを呼び出します．必ず呼び出してください．

**5.4.2. 開始要素の解析を行う**

メンバー変数\_tag\_stackを参照し，現在の解析対象要素を判断し，要素にあった処理を定義します

以下は，要素ごとの処理を定義するサンプルです．

```text
switch( implode( '/', $this -> _tag_stack ) ){
case "ITEM/DETAIL":
    //<item><detail>タグの処理をここに定義します．
    break;
case "ITEM/DETAIL/FOO":
    //<item><detail><foo>タグの処理をここに定義します．
    break;
}
```

#### 5.5. 終了要素ハンドラ\(xmlEndElementHandler\)

```text
void xmlEndElementHandler( $parser ,$name )
```

インポートするXMLファイルをシステムが解析し，終了要素を見つけたときにコールバックされます．要素のCDATAを参照する処理はこのメソッドに定義します．アイテムタイプはこの関数で以下の処理を行います．

* 終了要素の解析を行う
* スーパークラスのxmlEndElementHandlerを呼び出す

終了要素についての情報は引数で与えられます．引数は以下の とおりです．引数の解説は [項5.4. 「開始要素ハンドラ\(xmlStartElementHandler\)」](https://xoonips.osdn.jp/manuals/itemtype-340/import.html#import.implement.importitemhandler.startelementhandler) を参照してください．

* $parser：XMLパーザのリファレンス
* $name：要素名

戻り値はありません．

**5.5.1. 終了要素の解析を行う**

メンバー変数\_tag\_stackを参照し，現在の解析対象要素を判断し，要素にあった処理を定義します

以下は，要素ごとの処理を定義するサンプルです．

```text
switch( implode( '/', $this -> _tag_stack ) ){
case "ITEM/DETAIL":
    //<item><detail>タグの処理をここに定義します．
    break;
case "ITEM/DETAIL/FOO":
    //<item><detail><foo>タグの処理をここに定義します．
    break;
}
```

**5.5.2. スーパークラスの終了要素ハンドラを呼び出す**

```text
parent::xmlEndElementHandler($parser, $name);
```

終了要素ハンドラの最後に，上のようにしてスーパークラスの終了要素ハンドラを呼び出します．必ず呼び出してください．

#### 5.6. アイテムのインサート\(insert\)

```text
bool insert( &$item )
```

XMLを解析して得られたアイテムをデータベースにインサートし，その成否を返します．処理はXooNIpsItemCompoHandlerへ委譲します．

```text
function insert( &$item ){
    $handler =& xoonips_getormcompohandler( 'xnpdata', 'item' );
    return $handler -> insert($item);
}
```

#### 5.7. アイテムのnewフラグセット\(setNew\)

```text
void setNew( &$item )
```

インポートするアイテムオブジェクトに，新規アイテムを表すnewフラグをセットします．処理はXooNIpsItemCompoHandlerへ委譲します．

```text
function setNew( &$item ){
    $handler =& xoonips_getormcompohandler( 'xnpdata', 'item' );
    $handler -> setNew($item);
}
```

#### 5.8. アイテムのnewフラグ解除\(unsetNew\)

```text
void unsetNew( &$item )
```

インポートするアイテムオブジェクトのnewフラグを解除します．処理はXooNIpsItemCompoHandlerへ委譲します．

```text
function unsetNew( &$item ){
    $handler =& xoonips_getormcompohandler( 'xnpdata', 'item' );
    $handler -> unsetNew($item);
}
```

#### 5.9. アイテムのdirtyフラグセット\(setDirty\)

```text
void setDirty( &$item )
```

インポートするアイテムオブジェクトに，内容が変更されたことを表すdirtyフラグをセットします．処理はXooNIpsItemCompoHandlerへ委譲します．

```text
function setDirty( &$item ){
    $handler =& xoonips_getormcompohandler( 'xnpdata', 'item' );
    $handler -> setDirty($item);
}
```

#### 5.10. アイテムのdirtyフラグ解除\(unsetDirty\)

```text
void unsetDirty( &$item )
```

インポートするアイテムオブジェクトのdirtyフラグを解除します．処理はXooNIpsItemCompoHandlerへ委譲します．

```text
function unsetDirty( &$item ){
    $handler =& xoonips_getormcompohandler( 'xnpdata', 'item' );
    $handler -> unsetDirty($item);
}
```

#### 5.11. インポートログの作成\(getImportLog\)

```text
string getImportLog($import_item)
```

インポート処理中のアイテムに関する情報をログ形式の文字列にして返します．以下の手順で処理を行います．

* スーパークラスのgetImportLogを呼び出す
* アイテムタイプ独自のログを追加する

**5.11.1. スーパークラスのgetImportLogを呼び出す**

スーパークラスのgetImportLogを呼び出し，Basic Informationについてのインポートログを取得します．取得した文字列に，アイテムタイプ独自のログを追加します．

```text
$text = parent::getImportLog($import_item);
```

Basic Informationのログは，以下の書式で生成されます．

```text
basic.<フィールド名> <値>(改行)
```

フィールド名とその値は以下の通りです．

**表 20.5. フィールド一覧**

| フィールド名 | 内容 |
| :--- | :--- |
| id | アイテムID\(仮\) |
| title | タイトル |
| contributor | 作成者のUID |
| itemtype | アイテムタイプID |
| keyword | キーワード |
| description | コメント |
| doi | ID |
| last\_update\_date | 最終更新日の整数表現 |
| creation\_date | 作成日の整数表現 |
| publication\_year | 発行年 |
| publication\_month | 発行月 |
| publication\_mday | 発行日 |
| lang | 言語 |
| filename | インポートファイルのXMLファイル名 |
| url | インポートしたアイテムの詳細画面のURL\(インポート失敗時やテスト実行時は空文字列\) |
| related\_to | 関連アイテムのID\(テスト実行時は仮アイテムID\) |
| index | インポート先インデックスID |

**5.11.2. アイテムタイプ独自のログを追加する**

アイテムタイプ独自のログを追加します．Detail Informationの情報を以下の書式に従って作成します．

```text
detail.<フィールド名> <値>(改行)
```

フィールド値に特殊文字を含む場合は下表のとおり，\記号によるエスケープが必要です．

**表 20.6. エスケープ規則**

| エスケープ前 | エスケープ後 |
| :--- | :--- |
| \ | \\ |
| \(改行文字\) | \n |

以下に，例を示します．

```text
$detail =& $import_item -> getVar( 'detail' );
$text .= "\ndetail.readme " . mb_ereg_replace(
    '\n', '\n', mb_ereg_replace(
        '\\\\', '\\\\', $detail -> getVar( 'readme', 'n' )));
```

#### 5.12. 添付ファイルへの対応

アイテムタイプが添付ファイルを持つ場合は，以下の定義も必要です．

* メンバー変数の定義
* 開始要素ハンドラの定義
* 終了要素ハンドラの定義
* インポート終了イベント処理メソッドの定義

**5.12.1. メンバー変数の定義**

添付ファイルを取り扱うため，インポートアイテムハンドラにファイルオブジェクトを保持するメンバー変数を宣言します．

**5.12.2. 開始要素ハンドラの定義**

開始要素ハンドラに添付ファイルの処理を追加します．

添付ファイルの情報はFILE要素で定義されます．開始要素ハ ンドラは，FILE要素の解析で以下の処理を行います．

* ファイルオブジェクトを作成し，メンバー変数にセット
* 添付ファイルのパスをファイルオブジェクトにセット
* ファイルのメタ情報をファイルオブジェクトにセット

始めにファイルオブジェクトを作成します．セッションID，ファイルタイプIDもセットします．ファイルタイプIDは，属性FILE\_TYPE\_NAMEの値に対応するファイルタイプIDをデータベースに問い合わせて取得できます．

```text
$file_type_handler =& xoonips_getormhandler( 'xoonips', 'file_type' );
$criteria = new Criteria( 'name', addslashes( $attribs['FILE_TYPE_NAME'] ) );
$file_type =& $file_type_handler -> getObjects( $criteria );

$file_handler =& xoonips_getormhandler( 'xoonips', 'file' );
$this -> _file_member =& $file_handler -> create();
$this -> _file_member -> set( 'sess_id', session_id() );
$this -> _file_member -> set( 'file_type_id', $file_type[0] -> get( 'file_type_id' ) );
```

次に，添付ファイルが置かれたパスをファイルオブジェクト にセットします．添付ファイルはシステムが確保した一時フォル ダに保存されます．一時フォルダのパスはメンバー変 数\_attachment\_dirで取得できます．添付ファイル名はFILE\_NAME 属性で得られます．以下のようにして，ファイルオブジェクトに 添付ファイルのパスをセットしてください．

```text
$this -> _file_member -> setFilepath( $this -> _attachment_dir . '/' . $attribs['FILE_NAME'] );
```

最後に，FILE要素からファイルに関する属性を取得し，ファイルオブジェクトにセットします．ファイルオブジェクトに以下の情報をセットしてください．

**表 20.7. 属性一覧**

| 属性名 | 備考 |
| :--- | :--- |
| ORIGINAL\_FILE\_NAME | オリジナルファイル名 |
| MIME\_TYPE | mime-type |
| FILE\_SIZE | ファイルサイズ\(バイト\) |

**5.12.3. 終了要素ハンドラの定義**

開始要素ハンドラと同様に，終了要素ハンドラに添付ファイ ルの処理を追加します．終了要素ハンドラでは以下の処理を行います．

* キャプションの解析
* サムネイル画像の解析
* ファイルをデータベースへ記録

**5.12.3.1. キャプションの解析**

添付ファイルがプレビュー画像の場合，画像のキャプションを取得します．キャプションはFILEの子要素のCAPTIONで定義されるので，CAPTIONの終了要素の解析で\_cdataメンバー変数からキャプションを取得します．取得したキャプションはファイルオブジェクトにセットします．

```text
case 'ITEM/DETAIL/FILE/CAPTION':
    $unicode =& xoonips_getutility( 'unicode' );
    $this -> _file_member -> set(
            'caption',
            $unicode->decode_utf8(
                $this -> _cdata ,xoonips_get_server_charset(),'h') );
    }
    break;
```

**5.12.3.2. サムネイル画像の解析**

添付ファイルがプレビュー画像の場合，画像のサムネイル画像を取得します．サムネイル画像はFILEの子要素のCAPTIONで定義されるので，CAPTIONの終了要素の解析で\_cdataメンバー変数からサムネイル画像を取得します．取得したサムネイル画像はbase64でエンコードされた文字列なので，デコードした上でファイルオブジェクトにセットします．

```text
case 'ITEM/DETAIL/FILE/THUMBNAIL':
    $this -> _file_member -> set( 'thumbnail_file',
                                  base64_decode( $this -> _cdata ) );
    break;
```

**5.12.3.3. ファイルをデータベースへ記録**

FILEの終了要素の解析で，ファイルオブジェクトの内容をデータベースに記録します．記録したファイルオブジェクトを，インポートアイテムオブジェクトにセットします．

この時点でアイテムIDは確定していないため，記録されるファイルオブジェクトにもアイテムIDは記録されません．アイテムのインポートが成功しアイテムIDが確定した後，ファイルオブジェクトのアイテムIDを更新します．アイテムIDの更新は，インポート終了イベント処理メソッド\([項5.12.4. 「インポート終了イベント処理メソッドの定義」](https://xoonips.osdn.jp/manuals/itemtype-340/import.html#import.implement.importitemhandler.attachment.onimportfinished)\)で行います．

```text
case "ITEM/DETAIL/FILE":
    $file_handler =& xoonips_getormhandler( 'xoonips', 'file' );
    if( !$file_handler -> insert( $this -> _file_member ) ){
        $this -> _import_item -> setErrors(
            E_XOONIPS_DB_QUERY,
            "can't insert attachment file:"
            . $this -> _file_member -> get( 'original_file_name' )
            . $this -> _get_parser_error_at() );
    }
    $this -> _file_member = $file_handler -> get(
        $this -> _file_member -> get( 'file_id' ) );
    $this -> _import_item -> setVar( 'file_member',
                                     $this -> _file_member );
    $this -> _import_item -> setHasDataFile();
    break;
```

**5.12.4. インポート終了イベント処理メソッドの定義**

```text
void onImportFinished( &$item, &$import_items )
```

要求されたインポートが全て成功した場合に限り，システ ムは，インポート終了イベント処理メソッド関数をコールバッ クします．インポートされた各アイテム毎に，このメソッ ドがコールバックされます．

```text
//コールバック処理のイメージ
//(実際にはそれぞれのアイテムタイプに対応した
//インポートアイテムハンドラのメソッドをコールバックします．)
foreach( $import_items as $item ){
    $handler->onImportFinished($item, $import_items);
}
```

引数は以下の通りです．

* $item：インポートされたアイテム
* $import\_items：インポートされた全てのアイテムの配列

このメソッドでは以下の処理を定義します．

* 既存の添付ファイルの削除
* 添付ファイル情報の更新
* 全文検索インデックスの作成
* スーパークラスの呼び出し

**5.12.4.1. 既存の添付ファイルの削除**

既存アイテムに上書きインポートした場合に限り，以前 添付されていたファイルを削除します．この処理はスーパー クラスのメソッドとして定義されています．以下のように呼 び出してください．呼び出し側で，上書きインポートである か否かをチェックする必要はありません．

```text
$this -> _set_file_delete_flag($item);
```

**5.12.4.2. 添付ファイル情報の更新**

[項5.12.3.3. 「ファイルをデータベースへ記録」](https://xoonips.osdn.jp/manuals/itemtype-340/import.html#import.implement.importitemhandler.attachment.endelementhandler.insert) で述べたように，インポートの成功によって確定したアイテム IDを添付ファイルにセットします．処理はスーパークラスのメ ソッドとして定義されているので，以下のように呼び出してく ださい．$itemはこのメソッドの第一引数で与えられたインポー トアイテムオブジェクトです．

```text
$file_member =& $item -> getVar( 'file_member' );
$this -> _fix_item_id_of_file( $item, $file_member );
```

**5.12.4.3. 全文検索インデックスの作成**

添付ファイルの内容を検索可能にするため，全文検索インデッ クスを作成します．処理はスーパークラスのメソッドとして定 義されているので，以下のように呼び出してください．$itemは このメソッドの第一引数で与えられたインポートアイテムオブ ジェクトです．$itemから添付ファイルのオブジェクトを取得し， それをメソッドの引数に指定してください．

```text
$file_member =& $item -> getVar( 'file_member' );
$this -> _create_text_search_index( $file_member );
```

**5.12.4.4. スーパークラスの呼び出し**

最後に，スーパークラスの同名のメソッドを呼び出します． スーパークラスでは，インポートしたアイテム同士の関連ア イテムを構築するため，確定したアイテムIDを関連アイテム 情報にセットしています．

```text
parent::onImportFinished( $item, $import_items );
```

### 6. そのほかの関数

#### 6.1. エラー関数\(setErrors\)

```text
XooNIpsImportItem::setErrors($err_code, $err_str)
```

処理中にエラーが発生した場合は，このメソッドを使ってエラー情報を記録します．システムがこの情報を参照し，処理の成否の判断，エラー情報の出力などを行います．インポートアイテムハンドラの処理中にエラーが発生したばあいは，以下のように\_import\_itemメンバー変数にoエラー情報をセットします．

```text
$this -> _import_item -> setErrors( E_XOONIPS_ATTACHMENT_HAS_REDUNDANT,
                                    "multiple attachment is not allowed" );
```

引数は以下のとおりです．

* $err\_code：エラーコード
* $err\_str：エラー内容を表すテキスト

$err\_codeはあらかじめ定められた以下のエラーコードから適当なコードを一つ選んで使用します．これらはcondefs.hで定義されます．

**表 20.8. エラーコード一覧**

| エラーコード定義名 | 値 | 概要 |
| :--- | :--- | :--- |
| E\_XOONIPS\_SUCCESS | E0000 | 成功 |
| E\_XOONIPS\_ERROR | E0001 | エラー |
| E\_XOONIPS\_PARSER | E0002 | XMLパース処理のエラー |
| E\_XOONIPS\_USER\_NOT\_FOUND | E0003 | ユーザが見つからない |
| E\_XOONIPS\_DB\_QUERY | E0004 | DB操作中のエラー |
| E\_XOONIPS\_ATTR\_REDUNDANT | E0005 | 冗長\(排他使用の属性が両方指定されているなど\) |
| E\_XOONIPS\_ATTR\_NOT\_FOUND | E0006 | 属性が定義されていない |
| E\_XOONIPS\_ATTR\_INVALID\_VALUE | E0007 | 属性値が無効\(形式異常，未知の属性値など\) |
| E\_XOONIPS\_DATA\_TOO\_LONG | E0008 | 指定されたデータが長すぎる |
| E\_XOONIPS\_INDEX\_NOT\_FOUND | E0009 | 指定インデックスが存在しない |
| E\_XOONIPS\_OPEN\_FILE | E0010 | ファイルのオープンに失敗 |
| E\_XOONIPS\_RELATED\_ITEM\_IS\_NOT\_FOUND | E0011 | 指定された関連アイテムが見つからない |
| E\_XOONIPS\_FILE\_SYSTEM | E0012 | ファイルシステム全般 |
| E\_XOONIPS\_IMPORT | E0013 | インポート操作のエラー |
| E\_XOONIPS\_INVALID\_VALUE | E0014 | CDATA値の形式異常，未知の値 |
| E\_XOONIPS\_VALUE\_IS\_REQUIRED | E0015 | 必須の値が指定されていない |
| E\_XOONIPS\_NO\_PRIVATE\_INDEX | E0016 | インポートするアイテムがプライベートインデックスに登録されない |
| E\_XOONIPS\_ATTACHMENT\_HAS\_REDUNDANT | E0017 | 必要以上の添付ファイルをインポートしようとした |
| E\_XOONIPS\_NOT\_PERMITTED\_ACCESS | E0018 | アイテム，インデックスなどへのアクセス権限がない |
| E\_XOONIPS\_TAG\_NOT\_FOUND | E0019 | 省略できないXMLタグが見つからない |
| E\_XOONIPS\_INVALID\_VERSION | E0020 | 未知のバージョン\(version属性値\) |
| E\_XOONIPS\_PSEUDO\_ID\_CONFLICT | E0021 | 同じIDを持つ複数のXMLファイルがインポートファイル中で見つかった |
| E\_XOONIPS\_RELATED\_TO\_CONFLICTING\_ITEM | E0022 | 関連アイテムが重複している |
| E\_XOONIPS\_TAG\_REDUNDANT | E0023 | 冗長なタグ（タグが重複している、使用回数が多すぎる） |
| E\_XOONIPS\_DOI\_CONFLICT | E0024 | アイテムのDOIフィールドの値が既存のアイテムと重複している |
| E\_XOONIPS\_UPDATE\_CERTIFY\_REQUEST\_LOCKED | E0025 | アイテムがロックされているため更新できない |

