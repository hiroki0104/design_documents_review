# アプリケーション詳細設計
## 全体

- ログイン、サインイン、ログアウトを処理するコントローラが無い。
- 管理者画面で注文ごとのデータを扱うのであればadmin/ordersコントローラを作成すべき。
## end_users/
- 退会の確認する画面と退会後表示する画面のアクションが無い。
- 退会後表示する画面のアクションが無い。

## end_users/cart_items
- URLに/end_users/:end_user_id/を含めずにアクセスできるようにすべき。
- 注文情報確認の画面のアクションが無い。

## end_users/orders
- URLに/end_users/:end_user_id/を含めずにアクセスできるようにすべき。

## end_users/order_items
- createアクションが必要。
- indexアクションが不要。
- showアクションが不要。

## end_users/address
- URLに/end_users/:end_user_id/を含めずにアクセスできるようにすべき。
- addressだと単数形なのでaddressesにすべき。


## admin/items
- newアクションのURLはitemsではなくitems/new。

## admin/genres
- updateアクションが無い。

## admin/order_details
- indexアクションが不要。
- showアクションが不要。

# 注意
* マークダウン形式で記入してください。
* 全体を通しての指摘事項の場合、テーブル名の部分を「全体」「共通」などとしてください。
