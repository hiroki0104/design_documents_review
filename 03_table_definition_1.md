# テーブル定義書1
## 全体
- 指摘事項

## テーブル名
- 指摘事項

# 注意
* マークダウン形式で記入してください。
* 全体を通しての指摘事項の場合、テーブル名の部分を「全体」「共通」などとしてください。

## 全体
- カラム名の頭にテーブル名がついているが、不要

## Admin
- 管理者IDがPKになっていない

## Users
- 名前（名）のNOT NULLにチェックが入っていない

- 名前（名カナ）のNOT NULLにチェックが入っていない

- 退会ステータスでデータ型がbooleanになっていない

## Products
- ディスクID、ジャンルID、レーベルID、アーティストIDのFKにチェックがついていない

- stock_statusのデータ型がintegerが望ましい(enumにする必要があるため)

## Discs
- 

## Songs
- PKとなるidカラムが存在しない

- songカラムがintegerだが、stringが望ましい

## Labels
- PKとなるidカラムが存在しない

## Artists
- PKとなるidカラムが存在しない

- artistカラムがintegerだが、stringが望ましい

## Genre
- PKとなるidカラムが存在しない

- genreカラムがintegerだが、stringが望ましい

## Cart item
- PKとなるidカラムが存在しない

- products_idカラムのデータ型が空だが、実際はintegerが入る

## Buy details
- 

## Buy
- PKとなるidカラムが存在しない

- payカラムがstringだが、integerが望ましい(enumにする必要があるため)
