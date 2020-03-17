# テーブル定義書2
## 全体
- 各テーブルのPKのidの前に不要なモデル名がついている。

## admins
- PKにINDEXがない。
- emailとpasswordの前にadminがついている。

## users
- nameとkanaの前に不要なuser_〇がついている。
- emailとpasswordの前に不要なuserがついている。

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

## sell_details
- 外部キーがproducts_idになっている。
- 外部キーであるsell_idがない。
- 購入時の価格を保存するカラムがない。

## sells
- PKにINDEXがない。
- 購入詳細IDは不要。


## 研修担当レビュー
## 全体
- 入荷テーブルがありません。

## adminsテーブル
- deviseのデフォルトではメールアドレスはemail, パスワードはencrypted_passwordとなります。

## users
- user_l_name,user_f_nameではなにを示しているかわかりません。
- member_statusのデータ型がinteger/enumとなっています。
- deviseのデフォルトではメールアドレスはemail, パスワードはencrypted_passwordとなります。修正しましょう。

## cart items
- 購入枚数というカラム名になっています。

## sell_details
- 商品IDのFKがぬけています。

## sellsテーブル
- 支払方法、支払合計のカラム名がカラムの説明と合っていません。

## songs,labels,artists,genresテーブル（共通）
- テーブル名と同じカラム名が使用されています。nameというカラム名にすべき。
