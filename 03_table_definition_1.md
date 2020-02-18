# テーブル定義書1
## 全体
- 主キーになるカラムはidでよい。
- テーブル名はすべて小文字かつ、複数形。
- created_at,updated_atがすべてユーザ登録日時、更新日時になっている。
- Songs,Labels,Artists,Genre,Cart itemテーブルに主キーがない。
- deviseを使う場合は備考にdeviseと追記。
- AUTOINCREMENTとINDEXが抜けている箇所がある。（主キーに追記）
- テーブル名とカラム名に同じ名前を含めてはならない。

## Adminテーブル
- 管理者IDのPK漏れ
- 管理者IDのAUTOINCREMENTが抜けている。
- deviseのデフォルトではメールアドレスはemail, パスワードはencrypted_password

## Usersテーブル
- user_l,user_fではなにを示しているかわからない。
- 名前（名、名カナ）にNOT NULL がついていない。
- 郵便番号はstring型であるべき。
- 電話番号も同様。
- user_~というuser_の接頭辞は必要ない。
- member_statusのデータ型がstringになっている。
- 配送先住所について、複数の配送先があることを考慮していない。
- deviseのデフォルトではメールアドレスはemail, パスワードはencrypted_password

## Productsテーブル
- disc_idがある。
- genre_id,label_id,artist_idのFK漏れ
- products_idというように複数形になってしまっている。
- 入荷による在庫管理ができない。入荷テーブルを作るべき。
- 在庫ステータスのデータ型がstringになっている。

## Discsテーブル
- トラックNoではなく、ディスクNoにすべき。

## Songsテーブル
- 曲順の管理を考慮していない。

## Cart itemテーブル
- 小計金額は計算で求められるので、必要ない。
- 購入枚数ではなく数量にすべき。quantityなど

## Artists,Genre,Cart item,Songsテーブル(共通)
- FKにAUTOINCREMENTがついている。

## Artists,Genre,labelsテーブル(共通)
- 子要素のid(products_id)を持っている。

## Artistsテーブル
- アーティスト名がinteger型になっている。

## Genreテーブル
- ジャンル名がinteger型になっている。

## Buy,Buy detailsテーブル(共通)
- buy num -> buy_num
- 管理者視点のテーブル名にすべき。ordersなど

## Buyテーブル
- buy_details_idは必要ない。
- 支払方法、支払合計のカラム名が説明と合っていない。
- 支払方法のデータ型がstringになっている。
- 郵便番号と住所がない。

## Buy detailsテーブル
- buy_idがFKとして存在していない。



# 研修担当レビュー
- **合格になりますが以下ご確認ください。**

## 全体
> テーブル名はすべて小文字かつ、複数形。
- +スネークケースになります。
>  Songs,Labels,Artists,Genre,Cart itemテーブルに主キーがない。
- これは該当テーブルに書いてあげればいいと思います。
  - レビュー時に「全テーブルにPKを付けましょう。」とぼやかすならいいですが。
> テーブル名とカラム名に同じ名前を含めてはならない。
- user_telなど、接頭辞がついているものはこれでいいですが、例えばsongsテーブルのsongのように、テーブル名(の単数形)が入っているものについては別指摘の方が良いかなと思います。
  - 例: songではどのような値が入るかわかりません。例えばnameなどが適切になります。
    - など。(※「例えば～」以下を言う/言わないは好み)

## Products
> products_idというように複数形になってしまっている。
- FKに商品idを持つものに対しても同様になります。
  - 一つ一つに書くとくどいので、レビュー時は全体項にするのもアリです。
- 在庫数は算出できるため不要になります。
