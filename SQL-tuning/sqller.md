tüm aktif SQller vealışma değerli
```
SELECT sql_id,
       parsing_schema_name,
       executions,
       elapsed_time / 1000000 AS elapsed_sec,
       cpu_time / 1000000 AS cpu_sec,
       buffer_gets,
       disk_reads,
       sql_text
FROM v$sql
ORDER BY elapsed_time DESC
FETCH FIRST 20 ROWS ONLY;
```

Özet veriler
```


SELECT sql_id,
       executions,
       buffer_gets,
       disk_reads,
       parse_calls,
       substr(sql_text, 1, 100) AS sql_snippet
FROM v$sqlarea
ORDER BY buffer_gets DESC
FETCH FIRST 20 ROWS ONLY;
```


```

SELECT name, namespace, type, sharable_mem, kept
FROM v$db_object_cache
WHERE type IN ('PROCEDURE', 'FUNCTION', 'PACKAGE')
ORDER BY sharable_mem DESC;
```

selectivity
0---1
select  *  from product where category='laptop'

product tablosunda 10.000  kayıt  var
cate=laptop 100 ürünü filtree

100/10000 =0.01

cardinality =10000 X seelectivity =100
