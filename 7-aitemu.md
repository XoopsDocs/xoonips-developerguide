# 第7章 アイテム登録



![&#x30A2;&#x30A4;&#x30C6;&#x30E0;&#x767B;&#x9332;&#x753B;&#x9762;&#x4F5C;&#x6210;&#x306E;&#x6D41;&#x308C;](https://xoonips.osdn.jp/manuals/itemtype-340/images/regist-flow.gif)

**図 7.1. アイテム登録画面作成の流れ**  
![&#x753B;&#x9762;&#x9077;&#x79FB;&#x3068;&#x9001;&#x4FE1;&#x30D1;&#x30E9;&#x30E1;&#x30FC;&#x30BF;](https://xoonips.osdn.jp/manuals/itemtype-340/images/regist-trans.gif)

**図 7.2. 画面遷移と送信パラメータ**  


アイテム登録の流れは[図 7.1. 「アイテム登録画面作成の流れ」](https://xoonips.osdn.jp/manuals/itemtype-340/register.html#fig.register.workflow)のとおりです．登録は以下の流れで行ないます．

1. 登録フォームに登録内容を入力
2. 登録内容確認フォームで内容の表示とシステムによる内容チェック
3. 登録実行

### 1. 登録フォーム要求

アイテムタイプモジュールはシステムの登録要求を受けて，登録フォームを作成します．登録フォームはHTMLの形式で出力します．

アイテムタイプモジュールの以下の関数に登録フォーム作成処理を定義してください．システムは登録フォームが必要なときこの関数をコールバックします．

* function &lt;モジュール名&gt;GetRegisterBlock\( \)
  * 引数 : なし
  * 戻り値 : 登録フォームの HTML

#### 1.1. Basic Information の登録フォーム作成

共通ライブラリの機能を呼び出して，Basic Information の登録フォームを作成します． Basic Information のフィールド毎のフォームが得られるので，その中から必要なフィールドを取り出してフォームを作成します．

以下の項目も参照してください．

* xnpGetBasicInformationRegisterBlock

#### 1.2. Detail Information の登録フォーム作成

Detail Information の登録フォームを作成する方法は規定しません．出力する HTML がシステムの画面構成や動作を妨げないものであれば，どのように作成しても問題ありません．共通ライブラリに用意された機能を利用して，添付ファイルや画像の登録フォームを生成できます．

内容確認画面から編集フォームへ戻ってきた場合 \([図 7.2. 「画面遷移と送信パラメータ」](https://xoonips.osdn.jp/manuals/itemtype-340/register.html#fig.register.view-parameter)の\(3\)\) は，以前入力されたアイテム情報をフォームの初期値に設定するため，POST で与えられた情報をフォームの初期値に設定してください

以下の項目も参照してください．

* xnpGetBasicInformationRegisterBlock
* xnpGetPreviewRegisterBlock
* xnpGetAttachmentRegisterBlock
* xnpGetTextFileRegisterBlock
* xnpGetRightsRegisterBlock
* xnpGetIndexRegisterBlock
* xnpGetDownloadLimitationOptionRegisterBlock
* xnpGetDownloadNotificationOptionRegisterBlock

#### 1.3. パラメータチェック関数

出力する HTML に Web ブラウザ上でパラメータチェックを行なうチェック関数を定義してください．JavaScript で以下の関数を定義してください．パラメータチェックを行なわない場合も定義が必要です．

* function OnSubmitItemType\( form \)
  * 引数 : form \(登録フォームのオブジェクト\)
  * 戻り値 : true \(異常なし\)，false \(異常あり\)

フォームの Submit ボタンが押されると，OnSubmitItemType 関数がコールバックされます．アイテムタイプ独自の項目で，パラメータチェックが必要な場合はこの関数内にチェック処理を行ないます．エラーダイアログ表示などはこの関数内で行なってください．最後に，パラメータが正常な場合は true を，異常がある場合は false をかえしてください．パラメータチェックを行なわない場合は常に true をかえす処理を定義してください．

false を返した場合，登録内容確認画面へは進みません．

#### 1.4. 予約済みパラメータ名

システムが登録フォームで使用する \(登録フォームから POST で送信する\) パラメータの名前 \(&lt;input&gt;タグの name 属性\) は以下のとおりです．アイテムタイプモジュールが使用するパラメータが以下の名前と重複しないように注意してください．重複を避けるために Detail Information のパラメータ名にはプレフィクスとしてモジュール名を与えるとよいでしょう．

* mode
* fileID
* title
* keywords
* description
* doi
* publicationDateYear
* publicationDateMonth
* publicationDateDay
* publicationDate
* lang
* related\_to
* scrollX
* scrollY
* item\_type\_id

### 2. 登録内容確認フォーム要求

登録内容を確認するフォームを生成します．HTML で出力します．システムはアイテムタイプに対して以下の処理を行ないます．

* パラメータチェック関数のコールバック
* 登録内容確認フォームの要求

アイテムタイプモジュールの以下の関数に登録内容確認フォーム作成処理を定義してください．システムは登録内容確認フォームが必要なときこの関数をコールバックします．この関数は編集内容確認画面でも使用します．

* function &lt;モジュール名&gt;GetConfirmBlock\( $item\_id \)
  * 引数 : $item\_id \(確認したいアイテムの ID．ただし登録内容確認の場合は未指定です\)
  * 戻り値 : 内容確認画面の HTML

#### 2.1. パラメータチェック関数のコールバック

アイテムタイプは登録内容をチェックするための PHP 関数を定義します．関数の概要は以下のとおりです．

* 書式 : &lt;モジュール名&gt;CheckRegisterParameters\( &$msg \)
* 引数 : $msg \(チェックしたパラメータのエラーや警告メッセージを代入する\)
* 戻り値 : true \(異常なし\)，false \(異常あり\)

この関数内で Detail Information のパラメータチェックを行ないます．パラメータに異常があれば，その内容を示すメッセージを $msg 引数に設定し，false を返して関数を終了します．異常が無ければtrueを返します．false を返した場合，システムは登録処理実行を禁止します．$msg の内容は登録内容確認画面に出力されます．

#### 2.2. Basic Information の登録内容確認フォーム作成

共通ライブラリの機能を呼び出して，Basic Information の登録内容確認フォームを作成します． Basic Information のフィールド毎のフォームが得られるので，その中から必要なフィールドを取り出して組合せ，フォームを作成します．

以下の項目も参照してください．

* xnpGetBasicInformationConfirmBlock

#### 2.3. Detail Information の登録内容確認フォーム作成

以下の条件を満たしていれば，Detail Information の登録内容確認フォームの作成方法は規定しません．

* Detail Information の各フィールド値を次ページ，前ページへ送信するための &lt;input&gt; タグをつける
* 送信するパラメータに予約済みパラメータ名を使用しない
* 出力するHTMLがシステムの画面構成や動作を妨げない

共通ライブラリに用意された機能を利用して，添付ファイルや画像の登録内容確認フォームを生成できます．

以下の項目も参照してください．

* xnpGetBasicInformationConfirmBlock
* xnpGetPreviewConfirmBlock
* xnpGetAttachmentConfirmBlock
* xnpGetTextFileConfirmBlock
* xnpGetRightsConfirmBlock
* xnpGetIndexConfirmBlock
* xnpGetDownloadLimitationOptionConfirmBlock
* xnpGetDownloadNotificationOptionConfirmBlock
* xnpGetAttachmentFilenameConfirmBlock
* xnpGetAttachmentMimetypeConfirmBlock
* xnpGetAttachmentFiletypeConfirmBlock

#### 2.4. 予約済みパラメータ名

システムが使用する\( POST で送信する\)パラメータの名前 \(&lt;input&gt; タグの name 属性\) は以下のとおりです．アイテムタイプモジュールが使用するパラメータが以下の名前と重複しないように注意してください．重複を避けるために Detail Information のパラメータ名にはプレフィクスとしてモジュール名を与えるとよいでしょう．

* title
* keywords
* description
* doi
* publicationDateYear
* publicationDateMonth
* publicationDateDay
* publicationDate
* lang
* related\_to
* item\_type\_id

### 3. アイテム登録要求

システムからの要求を受けて，アイテム登録処理を実行します．アイテムタイプモジュールの以下の関数に登録処理を定義してください．システムは登録処理が必要なときこの関数をコールバックします．登録フォームに入力された情報は $\_POST 配列から取得します．登録したアイテムのアイテムIDを引数$item\_idに代入してください。

* function &lt;モジュール名&gt;InsertItem\( &$item\_id \)
* 引数 : アイテムIDを受け取る変数リファレンス
* 戻り値 : true \(登録成功\)，false \(登録失敗\)

#### 3.1. Basic Information の登録

共通ライブラリに Basic Information 登録関数が用意されています．その関数を呼び出してください．この関数はアイテム ID を返します．このアイテム ID は Detail Information やインデックスキーワードなどと Basic Information を関連付けるために必要となります．

以下の項目も参照してください．

* xnpInsertBasicInformation

#### 3.2. Detail Information の登録

Detail Information を DB に登録する処理を定義します．Basic Information を登録したときに得たアイテム ID に Detail Information を関連付けて記録してください．この ID は後にアイテムの情報を参照したり編集するときに使用します．関連付けが失われると Detail Information が取り出せなくなりますので注意してください．

添付ファイル，画像ファイル，テキストの登録には共通ライブラリを使用できます．

Detail Information の登録方法，DB の使用，DB の種類，処理方法は規定しませんので自由に定義してください．ID との関連付けが存在するのであれば，DB を使わずファイル \(CSV など\) で管理してもかまいません．

以下の項目も参照してください．

* xnpInsertBasicInformation
* xnpUpdateIndex
* xnpUpdateAttachment
* xnpUpdatePreview

