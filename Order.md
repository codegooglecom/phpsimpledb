Ordering is very expensive but very vital to a database. I can get it working faster but I choose feature set over speed in this category. When I have more time to look this over I'll revise the sorting algorithm.

Ascending vs Descending is signified in the beginning of each **index**. Ordering cannot be performed on a non-index item.

```
$db = new Page('data');
$rows = $db
    ->limit(0, 20)
    ->filter('__id < 100 or __id > 900')
    ->order('-published, +order')
    ->query();
```

That sample queried 1003 rows in 0.16 seconds with ordering. Without ordering it queried in 0.04 seconds.