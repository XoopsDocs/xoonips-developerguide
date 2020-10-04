# orm

## 第5章 ORMオブジェクト

XooNIpsはDetail Informationの情報を扱うためのORMオブジェクト を使用します．ORMオブジェクトを使用するためには，以下のようにクラス を定義しなければなりません．これは，使用するデータベースのテーブル 毎に定義する必要があります．

 **表 5.1. ORMオブジェクト情報**

|  | 書式 | 例\(xnpdataモジュールのxnpdata\_item\_detailテーブルの場合\) |
| :--- | :--- | :--- |
| フォルダ | モジュールフォルダ/class/orm/ | xnpdata/class/orm/ |
| ファイル名 | データベーステーブル名\(アイテムタイプ名を含まない\).class.php | item\_detail.class.php |
| データクラス名 | アイテムタイプ名\(xnpを含む最初の4文字は大文字\)＋'Orm'＋データベーステーブル名\(アイテムタイプ名を含まない\)のupper camel case | XNPDataOrmItemDetail |
| データハンドラクラス名 | アイテムタイプ名\(xnpを含む最初の4文字は大文字\)＋'Orm'＋データベーステーブル名\(アイテムタイプ名を含まない\)のupper camel case＋'Handler' | XNPDataOrmItemDetailHandler |

## 1. データクラスの実装

データクラスはデータベーステーブルの内容を保持するためのク ラスで，XooNIpsTableObjectを継承して作成します．１つのオブジェ クトでテーブルの１行分のデータを保持します．

最低でもコンストラクタは必ず実装し，以下のようにinitVarメソッ ドでデータベースと同じフィールドを定義します．そのほかのメソッド の実装は不要です．

```text


function XNPDataOrmItemDetail()

{

 parent::XooNIpsTableObject();

 $this->initVar('data_id', XOBJ_DTYPE_INT, 0, false);

 $this->initVar('data_type', XOBJ_DTYPE_TXTBOX, '', true, $this->lengths['data_type']);

 $this->initVar('readme', XOBJ_DTYPE_TXTBOX, null, false, $this->lengths['readme']);

 $this->initVar('rights', XOBJ_DTYPE_TXTBOX, null, false, $this->lengths['rights']);

 $this->initVar('use_cc', XOBJ_DTYPE_INT, 0, false);

 $this->initVar('cc_commercial_use', XOBJ_DTYPE_INT, null, false);

 $this->initVar('cc_modification', XOBJ_DTYPE_INT, null, false);

 $this->initVar('attachment_dl_limit', XOBJ_DTYPE_INT, 0, false);

 $this->initVar('attachment_dl_notify', XOBJ_DTYPE_INT, 0, false);

}

```

XooNIpsで使用するinitVarの引数は左から順に以下の通りです． その他の引数や動作についてはXoopsObjectクラスを参照してください．

 **表 5.2. initVarの引数**

| 引数の内容 | 備考 |
| :--- | :--- |
| カラム名 | テーブルのカラム名 |
| データ型 | XoopsObject, XooNIpsTableObjectで定義されるデータ型． XOBJ\_DTYPE\_TXTBOX， XOBJ\_DTYPE\_TXTAREA， XOBJ\_DTYPE\_INTなど． |
| 初期値 | NOT NULLのカラムには，必ずNULL以外の初期値を与える．省略時はnullとみなす． |
| 必須属性 | bool値を与える．必須ならtrue．省略時はfalseとみなす． |
| 文字数 | 最大文字数を与える．XOBJ\_DTYPE\_TXTBOX，XOBJ\_DTYPE\_BINARY以外には無効．マルチバイト文字は1文字を1と数える．省略時は文字数制限しない（データベースの処理に依存）． |

## 2. ハンドラクラスの実装

ハンドラクラスはデータクラスの登録，更新，削除などの操作を 実装するためのクラスで，XooNIpsTableObjectHandlerを継承して作成 します．

最低でもコンストラクタを必ず実装し，以下のように initHandlerメソッドでデータクラス名，テーブル名，主キー，AUTO INCREMENT属性を設定します．そのほかのメソッドの実装は不要です．

```text


function XNPDataOrmItemDetailHandler(&$db)

{

 parent::XooNIpsTableObjectHandler($db);

 $this->__initHandler('XNPDataOrmItemDetail', 'xnpdata_item_detail', 'data_id', false);

}

```

\_\_initHandlerメソッドには以下の引数を能えて使用します．その 他の引数やメソッドの詳細についてはXooNIpsTableObjectHandlerクラ スを参照してください．

 **表 5.3. \_\_initHandlerの引数**

| 引数の内容 | 備考 |
| :--- | :--- |
| データクラス名 | ハンドラクラスで扱うデータクラスの名前 |
| テーブル名 | プレフィクスを含まないテーブル名 |
| 主キーのカラム名 |  |
| AUTO INCREMENT属性 | 主キーがAUTO INCREMENTならtrue．省略時はfalseとみなす． |

  
Last updated: 2010/04/15

