---
title: 'Tips'
date: 2022-03-10T11:24:03+09:00
draft: true
---

## パーティションを意識する

athena は scan した量に応じて課金されるので、大量のデータをスキャンしないように 年月の where 句を必ず入れて実行しましょう。

```sql
WHERE year = '2020'
  AND month = '7'
```

## 数行のサンプル見る

```sql
select *
from ${table}
limit 10;
```

## よく見るカラム

[カラム説明](https://docs.aws.amazon.com/ja_jp/cur/latest/userguide/data-dictionary.html)

- line_item_blended_cost = blended_rate \* usage_amount
- [line_item_line_item_type](https://docs.aws.amazon.com/ja_jp/cur/latest/userguide/Lineitem-columns.html#l-L)
- product_product_name (description)
- line_item_product_code (code)
- [line_item_resource_id](https://docs.aws.amazon.com/ja_jp/cur/latest/userguide/Lineitem-columns.html#l-R) どのリソースに請求が紐付いているかがわかります

