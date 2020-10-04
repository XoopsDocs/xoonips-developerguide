---
description: アイテムの情報は以下の様に Basic Information と Detail Information に分けられます．
---

# 第2章 アイテムの概要

### 1. Basic Information

アイテムタイプに拘らずすべてのアイテムが所有する情報\(フィールド\)を Basic Information と呼びます．これには以下の項目があります．

* タイトル
* キーワード
* コメント
* DOI
* アイテムの内容物に関する年月日\[[1](https://xoonips.osdn.jp/manuals/itemtype-340/item.html#ftn.id360007)\]
* 作成ユーザ
* 作成日
* 最終更新日
* 言語

これらのうち，作成ユーザ，作成日，最終更新日はシステムが決定します．ユーザは指定できません．

Basic Information の DB への登録や DB からの取得，パラメータチェック，フォーム作成処理の一部はシステムが担当します．アイテムタイプモジュール作成者はこれらの処理を作成する必要はありません．共通ライブラリに関数の形で提供されるので，必要に応じて呼び出して使用します．

### 2. Detail Information

Basic Information に含まれないアイテムタイプ固有の情報を指します．Detail Information の取扱いはすべてアイテムタイプモジュールが行ないます．記録方法や処理方法はアイテムタイプで自由に決定できます．

### 3. Basic Information と Detail Information の対応

前述の様に 1つのアイテムに関する情報が，Basic Information と Detail Information の二つに分かれて管理されます．両者の対応をとるためにアイテム ID が存在します．アイテムタイプモジュールは，システムから与えられるアイテム ID と Detail Information を対応付けて管理してください．システムは同じアイテム ID を持つ Basic Information と Detail Information を 1つのアイテムとして取り扱います\([図 2.1. 「アイテム ID による対応付け \(例\)」](https://xoonips.osdn.jp/manuals/itemtype-340/item.html#fig.item.basic-detail.example)\)．

![&#x30A2;&#x30A4;&#x30C6;&#x30E0; ID &#x306B;&#x3088;&#x308B;&#x5BFE;&#x5FDC;&#x4ED8;&#x3051; \(&#x4F8B;\)](https://xoonips.osdn.jp/manuals/itemtype-340/images/relation.gif)

**図 2.1. アイテム ID による対応付け \(例\)**  
  


\[[1](https://xoonips.osdn.jp/manuals/itemtype-340/item.html#id360007)\] アイテムが論文なら論文発行日，プログラムならリリース年月日などを指定します．年月日が何を意味するかはアイテムタイプによって変わります．年月日を使わないアイテムタイプもあります．

