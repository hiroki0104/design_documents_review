# テーブル定義書1
## 全体
- テーブルの命名規則に従っていない。
- idがない。

## Admin
- PKがない。
- カラム名の前にadminがついてる。

## Users
- カラム名の前にuserがついてる。
- 住所に関するカラムが2つある。
- member_statusがstring型になっている。
- 郵便番号と電話番号がinteger型になっている。

## Products
- アーティストID、レーベルID、ジャンルIDにFKの設定がない。
- 在庫数カラムがある。
- ディスクIDを持っている。
- カラムの前にcdがついてる。

## Discs
- 外部キーはproducts_idになっている。
- track_numではディスクをディスクを特定できない。

## Songs 
- PKがない。
- 曲名カラムかintegerになっている。

## Labels
- PKがない。
- products_idがある。

## Artists
- PKがない。
- products_idがある。

## Genre
- Pkがない。
- products_idがある。
- ジャンル名カラムがinteger型になっている。
- テーブル名が単数系になっている。

## CartItem
- PKがない。
- 外部キーがproducts_idになっている。
- buy numはスペースが入っていて、カラムとして使用できない。
- テーブル名が単数系になっている。
- 小計金額カラムがある。

## Buy
- テーブル名が単数系になっている。
- 購入詳細IDを持っている。
- 支払い方法のカラムがstring型になっている。
- stockカラムが支払い合計になっている。
- 購入日カラムがある。
- 配送先住所と宛名のカラムがない。

## BuyDetails
- buy numはスペースが入っていて、カラムとして使用できない。

# 研修担当レビュー

## 全体
> テーブルの命名規則に従っていない。
 - とありますが、具体的にどんな命名規則が適切なのかも書いてください。
- AUTOINCREMENTとINDEXが抜けている箇所があります。
- created_at,updated_atがすべてユーザ登録日時、更新日時になっています。
- 配送先テーブル、入荷テーブルがない。

## Admin
- deviseでデフォルトで作られるカラム名はなんでしたでしょうか？

## Users
- user_l,user_fではなにを示しているかわかるでしょうか？
- deviseでデフォルトで作られるカラム名はなんでしたでしょうか？

## Products
- 在庫数カラムがある。在庫ステータスカラムがある。
- ジャケット画像のデータ型がtextになっています。

## Songsテーブル
- 曲順の管理が考慮されていません。

## Artists
- アーティスト名がinteger型になっている。

## Artists,Genre,Cart item,Songsテーブル(共通)
- FKにAUTOINCREMENTがついています。

## CartItem
- 購入枚数というカラム名は適切でしょうか？

## Artists,Genre,labels,songsテーブル(共通)
- テーブル名と同じカラム名が使用されています。

## Buy,Buy detailsテーブル(共通)
- 管理者視点のテーブル名に変更すべきです。

## Buy
- 支払方法、支払合計のカラム名がカラムの説明と合っていません。

## Buy detailsテーブル
- buy_idがFKとして存在していません。
