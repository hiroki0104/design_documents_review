# テーブル定義書1
## 全体
- created_atとupdated_atのカラム説明がユーザ登録日時とユーザ更新日時になっている。
- 配送先テーブルがない。
- 入荷テーブルがない。
- テーブル名は全て小文字で複数形にする。
- 商品IDのカラム名はproduct_idとする。
- テーブル名はスネークケースでかく。

## Admin
- admin_idはPKであるのにPKの欄に○がついていない。
- admin_idのAUTO INCREMENTとINDEXに○をつける。

## Users
- 名前に関する4つのカラム名についてlとfではわかりにくいため、lastとfirstにする。
- 名と名(カナ)のカラムについてNOT NULLに○をつける。
- user_l_nameの備考の「名前」はいらない。
- 電話番号と郵便番号は計算で使うわけでは無く、先頭に0が来ることもあるためstring型でおく。
- 配送先住所は配送先テーブルで管理するためそのカラムはいらない。
- member_statusはboolean型でおく。
- 退会ステータスのカラムはboolean型のためわかりやすくis_validの様に疑問文調でかく。
- 退会ステータスカラムの備考にtrueとfalseがそれぞれどの状態を表しているのかを記載する。

## Products
- productsテーブルはdiscsテーブルの親なのでdisc_idカラムはいらない。
- ジャンル・レーベル・アーティストIDはFKであるのでFKの欄に○をつける。
- ジャケット画像はinteger型の画像idで管理する。
- cd_titleのINDEXに○はいらない。
- 在庫数は入荷数と発注数から計算できるのでカラムはいらない。
- 在庫ステータスでなく販売ステータスのカラムをboolean型で用意する。

## Discs
- disc_idのINDEXに○をつける。
- 商品IDのカラム名をproduct_idにする。
- トラックNoは曲に割り当てられるものなのでカラムは必要ない。
- ディスク名のカラムを追加する。

## Songs
- PKであるsong_idがない。
- disc_idにAUTO INCREMENTは必要ない。
- 曲名のカラム名はsongよりsong_nameなどの方がわかりやすい。
- 曲名のカラムのデータ型はstring型が適切。
- 曲の順序を表すカラムを追加する。

## Labels
- PKであるlabel_idがない。
- このテーブルはproductsテーブルに対して親なので、現在のFKは必要ない。
- labelカラムはlabel_nameという名前にし、カラム説明も「レーベル名」とする

## Artists
- PKであるartist_idがない。
- このテーブルはproductsテーブルに対して親なので、現在のFKは必要ない。
- artistカラムはartist_nameという名前にし、データ型をstring型にする。

## Genre
- PKであるgenre_idがない。
- このテーブルはproductsテーブルに対して親なので、現在のFKは必要ない。
- genreカラムはgenre_nameという名前にし、データ型をstring型にする。

## Cart item
- PKであるcart_item_idがない。
- user_idにAUTO INCREMENTとINDEXは必要ない。
- 商品IDのデータ型をinteger型にする。
- 購入枚数のカラム名をスネークケースでかく。
- 小計金額は算出できるのでカラムは必要ない。

## Buy details
- 購入詳細IDのカラム名はbuy_detail_idとする。
- このテーブルはproductテーブルとbuyテーブルの子に当たるので、FKとしてproduct_idとbuy_idというカラムを持たせる。
- 購入枚数のカラム名をスネークケースでかく。
- 小計金額は算出できるのでカラムは必要ない。
- 購入時価格のカラムを持たせる。

## Buy
- このテーブルはbuy_detailsテーブルに対して親であるため、購入詳細IDのカラムは必要ない。
- 支払方法のカラム名はpayment_methodなどの方が適切。
- 支払方法はinteger型にして、enum型で管理する。
- 購入日のカラムは登録日と同じ意味なので無くてよい。
- 配送先の郵便番号と宛名を管理するカラムがない。
- 配送ステータスのカラムがない。
- 支払い合計のカラムはstockでなく、paymentなどの方が適切。

# 注意
* マークダウン形式で記入してください。
* 全体を通しての指摘事項の場合、テーブル名の部分を「全体」「共通」などとしてください。
