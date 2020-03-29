# アプリケーション詳細設計
# 全体
- end_user, admin共にログイン機能、サインアップ機能を司るコントローラーとアクションの記述が欠落してる（adminのサインアップ機能は不要）

# public/items

# public/end_users
- 論理削除を考慮し、destroyアクションのhttpメソッドはDELETEではなく、PATCHが適切
- 上記から、destroyアクションのURLを変更する必要がある

# public/cart_items
- urlのend_users/:end_user_idは全て不要

# public/orders
- urlのend_users/:end_user_idは全て不要
- 注文履歴を一覧する一覧するindexアクションが必要
- 購入情報を確認する画面及びアクションが必要
- 購入の確定を示す画面及びアクションが必要
- 注文詳細showアクションが必要

# public/order_items
- こちらのコントローラは不要

# public/address
- コントローラー名とurlのaddressはaddressesと複数形にする
- urlのend_user/:end_user_idは全て不要

# admin/items
- newアクションのurlがindexアクションと重複しているため、/items/newなどとする
- destroyアクションは要件にないため不要

# admin/end_genres
- updateアクションが必要

# admin/end_users
 - destroyアクションが必要

# admin/order_items
- こちらorder_itemsは不要
- 代わりにorderコントローラが必要

# 注意
* マークダウン形式で記入してください。
* 全体を通しての指摘事項の場合、テーブル名の部分を「全体」「共通」などとしてください。
