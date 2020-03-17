# テーブル定義書2
## 全体
- 各テーブルのPKのidの前に不要なモデル名がついている。
- 入荷テーブルがありません。

## admins
- PKにINDEXがない。
- deviseでデフォルトで作成されるカラム名と異なります。

## users
- user_l,user_fでは何を表しているのはわかりません。
- member_statusのデータ型がinteger/enum型になっている。
- deviseでデフォルトで作成されるカラム名と異なる。

## ships
- PKにINDEXがない。
- name,address,tel,codeの前のshipがついている。

## products
- 在庫数,在庫ステータスカラムがある。

## discs
- PKにINDEXがない。
- 外部キーがproducts_idになっている。
- nummの前に不要なdiscがついている。

## cart items
- テーブル名がスネークケースになっていない。
- PKにINDEXがない。
- 外部キーがproducts_idになっている。
- buy numはスペースが入っていてカラム名として使用できない。
- 購入枚数カラムはまだ購入が確定していないので不適切。

## sell_details
- 外部キーがproducts_idになっている。
- 商品IDのFKが抜けている。
- 外部キーであるsell_idがない。
- 購入時の価格を保存するカラムがない。

## sells
- PKにINDEXがない。
- 購入詳細IDは不要。
- 支払い方法、支払い合計のカラム名がカラムの意味と合っていません。

## songs,labels,artists,genres
- テーブル名と同じカラム名が使用されていますが意味的に不適切です。〜nameの方が適切です。



