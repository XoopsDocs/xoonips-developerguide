# 第23章 変更履歴

* 3.40

  * [項3. 「アイテム登録要求」](https://xoonips.osdn.jp/manuals/itemtype-340/register.html#register.query)の&lt;モジュール名&gt;InsertItem関数に引数&$item\_idを追加
  * [章 20. Import](https://xoonips.osdn.jp/manuals/itemtype-340/import.html)から古い関数の説明を削除し，インポートクラスの説明を追加
  * [章 11. アイテム詳細画面](https://xoonips.osdn.jp/manuals/itemtype-340/detail.html)の引数の間違いを訂正
  * [表 20.8. 「エラーコード一覧」](https://xoonips.osdn.jp/manuals/itemtype-340/import.html#table.import.implement.functions.seterrors.errorcodes)にE0023，E0024，E0025を追加
  * [項2. 「ダウンロードの通知の有無」](https://xoonips.osdn.jp/manuals/itemtype-340/download_confirm.html#download_confirm.notify)を追加
  * XooNIpsAttachmentクラスの削除
  * XooNIpsItemクラスの説明を削除
  * XooNIpsImportItem，XooNIpsImportItemHandlerクラスの説明を追加

  3.20

  * ダウンロード前の合意要求の章を追加．詳細画面の章でxnpGetDownloadConfirmationBlockについて言及．
  * GetDetailBlock関数に引数download\_file\_idを追加．
  * 参照項目としてxnpGetDownloadLimitationOption\(Register\|Edit\|Confirm\)Blockが挙げられている箇所に，xnpGetDownloadNotificationOption\(Register\|Edit\|Confirm\)Blockを追加

  3.20

  * Detail Informationの登録フォーム作成の参照項目に，xnpGetDownloadLimitationOptionRegisterBlock関数を追加
  * アイテム登録の予約済みパラメータに，ScrollX，ScrollY，item\_type\_idを追加
  * Detail Informationの登録内容確認フォーム作成の参照項目に，xnpGetDownloadLimitationOptionConfirmBlock，xnpGetDownloadLimitationOptionConfirmBlock，xnpGetAttachmentFilenameConfirmBlock，xnpGetAttachmentMimetypeConfirmBlock，xnpGetAttachmentFiletypeConfirmBlockを追加
  * 登録内容確認フォームの予約済みパラメータ名にitem\_type\_idを追加
  * アイテム編集フォームの予約済みパラメータ名にScrollX，ScrollY，xoonipsCheckedXID，jump\_to\_var\[\]を追加
  * Detail Informationの編集フォーム作成の参照項目に，xnpGetDownloadLimitationOptionEditBlock，xnpGetDownloadLimitationOptionConfirmBlock，xnpGetAttachmentFilenameConfirmBlock，xnpGetAttachmentMimetypeConfirmBlock，xnpGetAttachmentFiletypeConfirmBlockを追加
  * Detail Informationの編集内容確認フォーム作成の参照項目に，xnpGetDownloadLimitationOptionEditBlock関数を追加
  * GetMetaInformation関数の戻り値の詳細を追加
  * 詳細検索の検索クエリ（SQL）文作成について，xnpGetBasicInformationAdvancedSearchQueryを追加
  * 詳細検索のフォーム作成の参照項目に，xnpGetKeywordQuery，xnpGetKeywordsQueries，xnpGetBasicInformationAdvancedSearchBlockを追加
  * GetLicenseStatement関数の戻り値に追記
  * Detail InformationのExportの参照項目に，xnpExportFileを追加
  * ExportItem関数の引数変更
  * インポート処理の説明を変更
  * 

* 2.0
  * LicenseからRightsへの変更\(関数名の修正\)
  * related\_to属性の追加

