# テーブル定義書2
## 全体
- PKをテーブル名_idではなくidにする。
- テーブル名の頭文字を大文字にする。
- enumを用いる場合、格納された値と対応した文字を備考欄に書く。

## admins
- PKがindexになっていない。
- カラム名の接頭辞admin_は不要。

## users
- カラム名の接頭辞user_は不要。
- user_l_nameのようにlを略してしまうと意味が通じにくくなる。
- member_statusだと意味が通じにくいのでis_activeに修正し、boolean型に変更する。また、データ型の/enumは不要。

## ships
- PKがindexになっていない。
- カラム名の接頭辞ship_は不要。
- codeだけだと意味が通じづらいのでzip_codeなどにする。

## products
- ジャケット画像をrefileで実装するのであればデフォルト値画像準備中は不要。
- シングル名/アルバム名カラムの接頭辞cd_は無くても意味が通じる。

## discs
- PKがindexになっていない。
- カラム名の接頭辞disc_は不要。
- products_idではなくproduct_idにすべき。

## songs
- 商品IDの接頭辞song_は不要。
- songに曲名を入れるのであればnameなどにすべき。

## labels
- labelにラベル名を入れるのであればnameなどにすべき。

## artists
- artistにアーティスト名を入れるのであればnameなどにすべき。

## cart items
- テーブル名をスネークケースでcart_itemsにする。
- PKがindexになっていない。
- products_idではなくproduct_idにすべき。
- buy numだと意味が通じにくい。orderテーブルで購入枚数をconutとしてるのでcountにすべき。

## order_details
- products_idでなくproduct_idにする。
- 親テーブルをFKに指定する。
- productsテーブルで税抜価格をnotax_priceと記述したのでpriceでなくnotax_priceで統一する。

## orders
- PKがindexになっていない。
- 購入IDの接頭辞order_は不要。
- payだと意味が通じづらい。
- totalだと意味が通じづらい。

# 注意
* マークダウン形式で記入してください。
* 全体を通しての指摘事項の場合、テーブル名の部分を「全体」「共通」などとしてください。

## 研修担当レビュー
# 合格です。2点ご確認ください。
## discs
> カラム名の接頭辞disc_は不要。
  - numが省略形になっていますので、そちらも追加で指摘するとよいと思います。
  
## songs
- 商品IDの接頭辞song_は不要。
  - ？？？
