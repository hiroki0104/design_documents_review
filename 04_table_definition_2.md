# テーブル定義書2
## 全体
- テーブル名の頭文字を大文字にする。
- enumを用いる場合、格納された値と対応した文字を備考欄に書く。

## admins
- カラム名の接頭辞admin_は不要。

## users
- カラム名の接頭辞user_は不要。
- user_l_nameのようにlを略してしまうと意味が通じにくくなる。
- member_statusをenumで管理するのであればdefaultは整数であるべき。またデータ型の/enumは不要。

## ships
- カラム名の接頭辞ship_は不要。
- codeだけだと意味が通じづらいのでzip_codeなどにする。

## products
- 商品IDの接頭辞products_は不要。
- ジャケット画像をrefileで実装するのであればデフォルト値画像準備中は不要。
- シングル名/アルバム名カラムの接頭辞cd_は無くても意味が通じる。

## discs
- カラム名の接頭辞disc_は不要。
- products_idではなくproduct_idにすべき。

## songs
- 商品IDの接頭辞song_は不要。
- songに曲名を入れるのであればnameなどにすべき。

## labels
- ラベルIDの接頭辞label_は不要。
- labelにラベル名を入れるのであればnameなどにすべき。

## artists
- アーティストIDの接頭辞artist_は不要。
- artistにアーティスト名を入れるのであればnameなどにすべき。

## cart_items
- カートアイテムIDの接頭辞Cart item_は不要。
- products_idではなくproduct_idにすべき。
- buy numだと意味が通じにくい。

## order_details
- 購入詳細IDの接頭辞order_deatils_は不要。またIdをidにすべき。
- products_idでなくproduct_idにすべき。また、FKに指定する。
- productsテーブルで税抜価格をnotax_priceと記述したのでpriceでなくnotax_priceで統一する。

## orders
- 購入IDの接頭辞order_は不要。
- payだと意味が通じづらい。
- totalだと意味が通じづらい。

# 注意
* マークダウン形式で記入してください。
* 全体を通しての指摘事項の場合、テーブル名の部分を「全体」「共通」などとしてください。

## レビュー1回目
## 全体
- PKは テーブル名_id → id が適切です(@user.user_idとなるため)

## admins
- PKにindexがありません。

## users
- member_statusだと何を表しているのかわかりづらいので、is_deletedなど意味が通るものにする(退会/有効などのbooleanのものはis_〇〇などが多い)

## ships
- PKにindexがありません。
- ship_の接頭辞が必要ありません。

## products
- 在庫数は計算結果(入荷 - 売上)のため、データとして保存するのに適していません。
- 在庫ステータスは算出できるので、不要です。

## cart items
- テーブル名をcart_itemsに変更してください。
- buy num → buy_numberなど

## order_details
- 親モデルのidをFKとして持っていません。
