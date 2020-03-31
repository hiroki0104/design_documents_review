# テーブル定義書2
## 全体
- admin_id, user_idなどとせず、単にidなどでよい
 > PKは単にidとしましょう
- user_tel, user_passwordなども同様
 > user_tel, user_passwordなどとするより、単にtel, passwordとしたほうがわかりやすいです

## admins
- admin_idにindexを付与したい
 > admin_idにindexを付与しましょう

## users
- user_l_nameなどと省略しないほうが良い
 > カラム名に略語を用いるのは不適切です
- user_l_nameの備考に”名前”は不適当
 > user_l_nameの備考を見直してみましょう
- member_statusだと機能がわかりにくい
 > member_statusだと機能がわかりにくいので、わかりやすい名称をつけましょう
- member_statusのデータ型がintegerとなっているにも関わらず、DEFAULTがFALSEはおかしい
 > member_statusのデータ型とDEFAULTを見直してみましょう
- member_statusのデータ型にenumは違和感がある。備考に書きたい
 > member_statusのデータ型にenumと書くのは違和感があります。備考欄に書きましょう
- 名前は性ではなく姓が正しい
 > nameのカラム説明を見直してみましょう
- controller名はusersではなくend_userなどとしたほうがよい
 > controller名はusersではなく、end_userなどとしたほうがわかりやすいです

## ships
- テーブル名がshipsだとわかりにくい
 > テーブル名がshipsだとわかりにくいので、わかりやすい名前をつけましょう
- ship_nameだと機能がわかりにくい
 > ship_nameだと機能がわかりにくいので、わかりやすい名前をつけましょう
- 主キーにindexを付与したい。
 > 主キーにindexを付与しましょう
- 電話番号は不要
 > 電話番号は要件にないため不要です

## products
- products_idと複数形になってるいるが、不適切
 > products_idと複数形になっているのは不適切です
- image_idにNOT NULL属性は不要
 > image_idにNOT NULL属性は不要です
- image_idのDEFAULTとして"画像準備中"は不適切
 > image_idのDEFAULTを見直してみましょう
- cd_titleだと機能が不明瞭
 > cd_titleだとわかりにくいので、わかりやすい名称をつけましょう
- 販売ステータス（販売中、販売停止中）を示すカラムがほしい
 > 販売ステータス（販売中、販売停止中）を示すカラムが必要です
- 販売日を示すカラムがほしい
 > 販売日を示すカラムが必要です

## discs
- products_idと複数形になっているが、不適当
 > products_idと複数形になっているのは不適切です

## songs
- カラム名songだとわかりにくい。
 > カラム名がsongだとわかりにくいので、わかりやすい名称をつけましょう
- created_at, updated_atカラムの説明が”曲名〜”となっているのは不適切
 > create_ad, updated_atカラムの説明を見直してみましょう

## labels
- カラム名がlabelだとわかりにくい。
 > カラム名がlabelだとわかりにくいため、わかりやすい名称をつけましょう

## artists
- カラム名がartistだとわかりにくい
 > カラム名がartistだとわかりにくいため、わかりやすい名称をつけましょう

## genres
- カラム名はgenreだとわかりにくい
 > カラム名がgenreだとわかりにくいため、わかりやすい名称をつけましょう

## cart_items
- カラム名がCart_item_idと大文字になっているのは不適当
 > 購入時価格は税込みとしましょう
- products_idと複数形になっているのは不適当
 >  products_idと複数形になっているのは不適当です
- buy numカラムに_が抜けている
 >　カラム名に空白を使うのは控えましょう

## order_details
- products_idと複数形になっているのは不適当
 >  products_idと複数形になっているのは不適当です
- product_idはFKに指定する
 > 必要なカラムをFKに指定しましょう
- created_at, updated_atカラムの説明が"販売登録日時"などとなっているのは不適切
 > created_at, updated_atカラムの説明を見直してみましょう
- 購入時価格は税込みの方がよい
 > 購入時価格は税込みとしましょう
- order_detail_Idと大文字を使うのは不適切
 > 購入時価格は税込みとしましょう

## orders
- カラム名としてpayだとわかりにくい
 > カラム名としてpayはわかりにくいので、わかりやすい名称をつけましょう
- ship_codeだとわかりにくい
 > ship_codeだとわかりにくいので、わかりやすい名称をつけましょう
- ship_nameだとわかりにくい
 > ship_nameだとわかりにくいので、わかりやすい名称をつけましょう
- ship_costだとわかりにくい
 > ship_costだとわかりにくいので、わかりやすい名称をつけましょう
- 単にtotalだとなんの合計かわかりにくい
 > totalだとわかりにくいので、わかりやすい名称をつけましょう
- 配送ステータス（配送状況）を示すカラムがない
 > 配送ステータス（配送状況）を示すカラムが必要です

# 注意
* マークダウン形式で記入してください。
* 全体を通しての指摘事項の場合、テーブル名の部分を「全体」「共通」などとしてください。

**研修担当レビュー**
<font color="Red">再提出の際はこのレビューを残しておいてください。</font>

## admins
- admin_idにindexがありません

## users
- 名前の部分で「性」と書いてありますが、「姓」が正しいです。
- コントローラ名をusersではなく,end_userやcunstomerにした方が適切です。

## ships
- 主キーにindexがありません。
- 電話番号は要件にありません。

## products
- 販売ステータスがありません
- 販売日がありません
- disc_numはproductsにありません

## cart_items
- 購入時に枚数が必要になるので、buy_numは必要になります。
- buy numにアンダーバーが抜けている指摘もお願いします。

## order_details
- 購入時価格は税込みの方が良いです。
- 「order_details_Id」と大文字が使用されている箇所があります。

## orders
- 配送ステータスが存在しません。
