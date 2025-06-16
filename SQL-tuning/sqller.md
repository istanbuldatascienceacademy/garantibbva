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

