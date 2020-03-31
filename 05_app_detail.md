# アプリケーション詳細設計
## 全体
- end_user, admin共にログイン機能、サインアップ機能を司るコントローラーとアクションの記述が欠落してる（adminのサインアップ機能は不要）
- 管理者のトップページに相当するアクションが必要
- 管理者が製作ステータスを更新するためのアクションが必要
- 使用するgemを書く必要がある

## public/items

## public/end_users
- 論理削除を考慮し、destroyアクションのhttpメソッドはDELETEではなく、PATCHが適切
- 上記から、destroyアクションのURLを変更する必要がある
- 退会確認画面に相当するアクションが必要

## public/cart_items
- urlのend_users/:end_user_idは全て不要
- editアクションは不要
- カートを空にするためのアクションが必要

## public/orders
- urlのend_users/:end_user_idは全て不要
- 注文履歴を一覧するindexアクションが必要
- 購入情報を確認する画面及びアクションが必要
- 購入の確定を示す画面及びアクションが必要
- 注文詳細showアクションが必要

## public/order_items
- こちらのコントローラは不要

## public/addresses
- コントローラー名とurlのaddressはaddressesと複数形にする
- urlのend_user/:end_user_idは全て不要

## admin/items
- newアクションのurlがindexアクションと重複しているため、/items/newなどとする
- destroyアクションは要件にないため不要

## admin/genres
- updateアクションが必要

## admin/end_users

## admin/order_items
- こちらのorder_itemsコントローラは不要
- 代わりにordesrコントローラが必要

# 注意
* マークダウン形式で記入してください。
* 全体を通しての指摘事項の場合、テーブル名の部分を「全体」「共通」などとしてください。

# レビュー（1回目）
## 全体
- 使用するgemの記載がないので追加してください。

## public
## end_users
- 退会確認画面に相当するアクションがありません。

### cart_items
- 不要なアクションeditがあります。
- "カートを空にする"に相当するアクションがありません。

### address
- 複数形になっていません。誤 address → 正 addresses

## admin
### 共通
- 管理者のトップページがありません。
- 製作ステータスの更新に相当するアクションがない。

### end_users
- destroyアクションは不要です。
