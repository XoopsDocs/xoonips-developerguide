# 第7章 TextFile

Plain Text を取り扱います．主に長文入力を想定したフォームで，キー入力の代わりにテキストファイルの内容を読み込むことが出来ます．キー入力も可能です．

\($name 引数については [章 14. 補足: Attachment, TextFile 系関数の $name 引数について](https://xoonips.osdn.jp/manuals/commonlib-340/auxil.html) を参照\)

### 1. array xnpGetTextFileDetailBlock\( int item\_id, string name, string text \)

#### 1.1. 内部で参照する $\_POST 変数

なし

#### 1.2. 画面

※ Add as Text ・Add as File どちらで登録してもこの表示になる．

※ 引数のtextを，&lt;TEXTAREA&gt; … &lt;/TEXTAREA&gt;で表示する．

> ![](https://xoonips.osdn.jp/manuals/commonlib-340/images/xnpGetTextFileDetailBlock.gif)

#### 1.3. 送信データ

なし

### 2. array xnpGetTextFileEditBlock\( int item\_id, string name, string text \)

※ Text を外から引数として与える必要があります．

#### 2.1. 内部で参照する $\_POST 変数

* $\_POST\["${name}EncText"\]

#### 2.2. 画面

画面は Readme 入力画面説明.ppt を参照

> ![](https://xoonips.osdn.jp/manuals/commonlib-340/images/xnpGetTextFileEditBlock1.gif)

ここで Edit リンクを押すと以下のウィンドウが開く

> ![](https://xoonips.osdn.jp/manuals/commonlib-340/images/xnpGetTextFileEditBlock2.gif)

ここで OK ボタンを押すとウィンドウが閉じ，TEXTAREA のデータが元のフォームに転送される．Cancel ボタンを押すと単にウィンドウが閉じるのみ．

#### 2.3. 送信データ

Upload ボタン →

* $\_FILES\['text'\]
* $\_POST\['name'\]

Submit ボタン → 確認画面へ

* $\_POST\["${name}EncText"\]

### 3. array xnpGetTextFileConfirmBlock\( int item\_id, string name, int maxlen=65535 \)

Confirm 画面用の HTML を生成する．

#### 3.1. 内部で参照する $\_POST 変数

* $\_POST\["${name}EncText"\]

#### 3.2. 画面

> ![](https://xoonips.osdn.jp/manuals/commonlib-340/images/xnpGetTextFileConfirmBlock.gif)

#### 3.3. 送信データ

* $\_POST\["${name}EncText"\]

#### 3.4. 入力

* maxlen : DBのカラムサイズ\)

### 4. array xnpGetTextFileRegisterBlock\( string name \)

→ [項2. 「array xnpGetTextFileEditBlock\( int item\_id, string name, string text \)」](https://xoonips.osdn.jp/manuals/commonlib-340/textfile.html#func-xnpGetTextFileEditBlock) と同じ

### 5. string xnpGetTextFile\( string name \)

Confirm 画面の Submit でロードされるページで $\_POST\["${name}EncText"\] を得るための関数である．各アイテムタイプモジュールは，この関数で得た文字列を DB に記録する．

#### 5.1. 内部で参照する $\_POST 変数

* $\_POST\["${name}EncText"\]

#### 5.2. 戻り値

array\( 'value'=&gt;入力された文字列の確認画面表示用html, 'within'=&gt;入力された文字列から頭$maxlenバイトを切り出したもの, 'without'=&gt;切り出した残り, 'html\_string'=&gt;入力された文字列のhtml \)．

