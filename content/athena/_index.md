---
title: 'Athenaでクエリを発行'
date: 2022-03-09T17:02:29+09:00
draft: false
weight: 30
---

1. どういうカラムがあるかを確認する
2. サービス別利用料金のクエリーを流す
3. ec2、rds、s3 の usagetype を確認する





example
```sql
SELECT line_item_resource_id,
	product_product_name,
	line_item_usage_type,
	line_item_line_item_type,
	floor(sum(line_item_blended_cost)) cost
FROM o11y2022_cur
WHERE year = '2022'
	and month = '3'
group by line_item_resource_id,
	product_product_name,
	line_item_usage_type,
	line_item_line_item_type
order by cost desc
limit 50
```