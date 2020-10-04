# textfile

| ![&#x524D;&#x306E;&#x30DA;&#x30FC;&#x30B8;](https://github.com/XoopsDocs/xoonips-developerguide/tree/a6a58e91b3c2fbad05284b6a55d66570e12e94d6/en/book/commonlib/textfile/images/prev.gif) |  | ![&#x6B21;&#x306E;&#x30DA;&#x30FC;&#x30B8;](https://github.com/XoopsDocs/xoonips-developerguide/tree/a6a58e91b3c2fbad05284b6a55d66570e12e94d6/en/book/commonlib/textfile/images/next.gif) |
| :--- | :---: | :--- |


## 第7章 TextFile <a id="7-textfile"></a>

Plain Text を取り扱います．主に長文入力を想定したフォームで，キー入力の代わりにテキストファイルの内容を読み込むことが出来ます．キー入力も可能です．

\($name 引数については 章 14. _補足: Attachment, TextFile 系関数の $name 引数について_ を参照\)

## 1. array xnpGetTextFileDetailBlock\( int item\_id, string name, string text \) <a id="1-array-xnpgettextfiledetailblock-int-item-id-string-name-string-text"></a>

### 1.1. 内部で参照する $\_POST 変数 <a id="1-1-post"></a>

なし

### 1.2. 画面 <a id="1-2"></a>

※ Add as Text ・Add as File どちらで登録してもこの表示になる．

※ 引数のtextを，&lt;TEXTAREA&gt; … &lt;/TEXTAREA&gt;で表示する．

> ![](https://github.com/XoopsDocs/xoonips-developerguide/tree/a6a58e91b3c2fbad05284b6a55d66570e12e94d6/en/book/commonlib/textfile/images/xnpGetTextFileDetailBlock.gif)

### 1.3. 送信データ <a id="1-3"></a>

なし

## 2. array xnpGetTextFileEditBlock\( int item\_id, string name, string text \) <a id="2-array-xnpgettextfileeditblock-int-item-id-string-name-string-text"></a>

※ Text を外から引数として与える必要があります．

### 2.1. 内部で参照する $\_POST 変数 <a id="2-1-post"></a>

* $\_POST\["${name}EncText"\]

### 2.2. 画面 <a id="2-2"></a>

画面は Readme 入力画面説明.ppt を参照

> ![](https://github.com/XoopsDocs/xoonips-developerguide/tree/a6a58e91b3c2fbad05284b6a55d66570e12e94d6/en/book/commonlib/textfile/images/xnpGetTextFileEditBlock1.gif)

ここで Edit リンクを押すと以下のウィンドウが開く

> ![](https://github.com/XoopsDocs/xoonips-developerguide/tree/a6a58e91b3c2fbad05284b6a55d66570e12e94d6/en/book/commonlib/textfile/images/xnpGetTextFileEditBlock2.gif)

ここで OK ボタンを押すとウィンドウが閉じ，TEXTAREA のデータが元のフォームに転送される．Cancel ボタンを押すと単にウィンドウが閉じるのみ．

### 2.3. 送信データ <a id="2-3"></a>

Upload ボタン →

* $\_FILES\['text'\]
* $\_POST\['name'\]

Submit ボタン → 確認画面へ

* $\_POST\["${name}EncText"\]

## 3. array xnpGetTextFileConfirmBlock\( int item\_id, string name, int maxlen=65535 \) <a id="3-array-xnpgettextfileconfirmblock-int-item-id-string-name-int-maxlen-65535"></a>

Confirm 画面用の HTML を生成する．

### 3.1. 内部で参照する $\_POST 変数 <a id="3-1-post"></a>

* $\_POST\["${name}EncText"\]

### 3.2. 画面 <a id="3-2"></a>

> ![](https://github.com/XoopsDocs/xoonips-developerguide/tree/a6a58e91b3c2fbad05284b6a55d66570e12e94d6/en/book/commonlib/textfile/images/xnpGetTextFileConfirmBlock.gif)

### 3.3. 送信データ <a id="3-3"></a>

* $\_POST\["${name}EncText"\]

### 3.4. 入力 <a id="3-4"></a>

* maxlen : DBのカラムサイズ\)

## 4. array xnpGetTextFileRegisterBlock\( string name \) <a id="4-array-xnpgettextfileregisterblock-string-name"></a>

→ 項2. 「array xnpGetTextFileEditBlock\( int item\_id, string name, string text \)」 と同じ

## 5. string xnpGetTextFile\( string name \) <a id="5-string-xnpgettextfile-string-name"></a>

Confirm 画面の Submit でロードされるページで $\_POST\["${name}EncText"\] を得るための関数である．各アイテムタイプモジュールは，この関数で得た文字列を DB に記録する．

### 5.1. 内部で参照する $\_POST 変数 <a id="5-1-post"></a>

* $\_POST\["${name}EncText"\]

### 5.2. 戻り値 <a id="5-2"></a>

array\( 'value'=&gt;入力された文字列の確認画面表示用html, 'within'=&gt;入力された文字列から頭$maxlenバイトを切り出したもの, 'without'=&gt;切り出した残り, 'html\_string'=&gt;入力された文字列のhtml \)．

| ![&#x524D;&#x306E;&#x30DA;&#x30FC;&#x30B8;](https://github.com/XoopsDocs/xoonips-developerguide/tree/a6a58e91b3c2fbad05284b6a55d66570e12e94d6/en/book/commonlib/textfile/images/prev.gif) |  | ![&#x6B21;&#x306E;&#x30DA;&#x30FC;&#x30B8;](https://github.com/XoopsDocs/xoonips-developerguide/tree/a6a58e91b3c2fbad05284b6a55d66570e12e94d6/en/book/commonlib/textfile/images/next.gif) |
| :--- | :--- | :--- |
|  | ![&#x30DB;&#x30FC;&#x30E0;](https://github.com/XoopsDocs/xoonips-developerguide/tree/a6a58e91b3c2fbad05284b6a55d66570e12e94d6/en/book/commonlib/textfile/images/home.gif) |  |

Last updated: 2010/04/15

