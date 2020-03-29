# テーブル定義書2
## 全体
- admin_id, user_idなどとせず、単にidなどでよい
- user_tel, user_passwordなども同様

## admins
- 

## users
- user_l_nameなどと省略しないほうが良い
- user_l_nameの備考に”名前”は不適当
- member_statusだと機能がわかりにくい
- member_statusのデータ型がintegerとなっているにも関わらず、DEFAULTがFALSEはおかしい
- member_statusのデータ型にenumは違和感がある。備考に書きたい

## ships
- テーブル名がshipsだとわかりにくい
- ship_nameだと機能がわかりにくい。

## products
- products_idと複数形になってるいるが、不適切
- image_idにNOT NULL属性は不要
- image_idのDEFAULTとして"画像準備中"は不適切
- cd_titleだと機能が不明瞭
- disc_numなどと省略形を使わないほうがいい

## discs
- products_idと複数形になっているが、不適当

## songs
- カラム名songだとわかりにくい。
- created_at, updated_atカラムの説明が”曲名〜”となっているのは不適切

## labels
- カラム名がlabelだとわかりにくい。

## artists
- カラム名がartistだとわかりにくい

## genres
- カラム名はgenreだとわかりにくい

## cart_items
- カラム名がCart_item_idと大文字になっているのは不適当
- products_idと複数形になっているのは不適当
- まだ購入しているわけではないのでbuy_num、購入枚数は不適当

## order_details
- products_idと複数形になっているのは不適当
- product_idはFKに指定する
- created_at, updated_atカラムの説明が"販売登録日時"などとなっているのは不適切

## orders
- カラム名としてpayだとわかりにくい
- ship_codeだとわかりにくい
- ship_nameだとわかりにくい
- ship_costだとわかりにくい
- 単にtotalだとなんの合計かわかりにくい

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
